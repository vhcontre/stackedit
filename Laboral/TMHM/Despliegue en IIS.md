Configurar un **despliegue automatizado con GitHub Actions** desde tu repositorio privado hacia un **servidor remoto Windows con IIS**.

## ✅ Requisitos previos

Antes de crear el flujo de trabajo, necesitas:

### En el servidor remoto (IIS):

1. **Acceso a Internet** en el servidor.
2. Instalar el **Web Deploy 3.6 o superior**:

   * Puedes descargarlo desde: [https://www.iis.net/downloads/microsoft/web-deploy](https://www.iis.net/downloads/microsoft/web-deploy)
3. Crear un **sitio en IIS** para tu aplicación, por ejemplo: `MiSitio`.
4. Configurar **Web Management Service** y abrir el puerto 8172 (por defecto) en el firewall.
5. Crear un usuario local o usar uno con permisos de despliegue en IIS.

### En GitHub:

1. Tener el proyecto .NET Framework 4.5 subido a un repositorio.
2. Acceder a **Settings > Secrets and variables > Actions > Secrets**, y crear estos:

| Nombre del secreto | Valor                                               |
| ------------------ | --------------------------------------------------- |
| `IIS_SERVER`       | `mi-servidor.dominio.com` o IP del servidor         |
| `IIS_USERNAME`     | Usuario con permisos de despliegue en el servidor   |
| `IIS_PASSWORD`     | Contraseña de ese usuario                           |
| `IIS_SITE_NAME`    | El nombre del sitio en IIS (por ejemplo: `MiSitio`) |

---

## 🛠️ Paso 1: Crear el archivo de workflow

En tu proyecto, crea este archivo:

```
.github/workflows/deploy.yml
```

Y pega esto:

```yaml
name: Deploy to IIS

on:
  push:
    branches:
      - main  # O la rama que uses para producción

jobs:
  build-and-deploy:
    runs-on: windows-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Setup MSBuild
      uses: microsoft/setup-msbuild@v1.1

    - name: Restore NuGet packages
      run: nuget restore YourSolution.sln

    - name: Build the project
      run: msbuild YourSolution.sln /p:Configuration=Release

    - name: Publish with MSBuild
      run: msbuild YourProject.csproj /p:DeployOnBuild=true /p:PublishProfile=FolderProfile /p:Configuration=Release

    - name: Deploy to IIS via Web Deploy
      run: |
        msdeploy.exe ^
          -source:package="path\to\output\package.zip" ^
          -dest:auto,computerName="https://${{ secrets.IIS_SERVER }}:8172/msdeploy.axd?site=${{ secrets.IIS_SITE_NAME }}",userName="${{ secrets.IIS_USERNAME }}",password="${{ secrets.IIS_PASSWORD }}",authType="Basic" ^
          -allowUntrusted
```

> 🔧 **Nota**: reemplaza `YourSolution.sln`, `YourProject.csproj`, y `path\to\output\package.zip` según tu estructura real.

---

## 🧪 ¿Cómo pruebo que funciona?

1. Haz un **commit en `main`**.
2. Ve a la pestaña **Actions** del repositorio.
3. Verifica que el workflow se ejecute y despliegue tu app al IIS.

---

## ✅ ¿Qué más podrías agregar?

* Verificación post-despliegue (ping al sitio).
* Notificaciones por correo o Teams.
* Deploy manual (solo cuando hagas clic).
* Multientorno (producción, staging, etc.).

---



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYyODc4OTM0NCwxOTkxMjYyMDU1XX0=
-->