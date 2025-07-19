## Estructura de la solución AXIS

* ✅ Tipo de proyecto
* 🧱 Qué rol cumple
* 📦 NuGet recomendados
* 🧩 Contenido típico

---

### 📊 Tabla resumen: estructura de la solución AXIS

#### Aplicación eXtendible de Interfaces y Servicios

| Proyecto                  | Tipo de proyecto                             | Rol principal                                                    | NuGet recomendados                                                                                             | Contenido recomendado                                                               |
| ------------------------- | -------------------------------------------- | ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `AXIS.App.UI`             | **Blazor Server App** o **ASP.NET Core MVC** | Interfaz de usuario y front-end del sistema                      | `Syncfusion.Blazor`<br>`Microsoft.AspNetCore.Components.Web`<br>`Microsoft.Extensions.Http`                    | - Páginas (`.razor` o `.cshtml`)<br>- Layouts<br>- Startup/Program.cs<br>- Login UI |
| `AXIS.App.Application`    | **.NET Class Library**                       | Lógica de aplicación, casos de uso                               | `AutoMapper`<br>`FluentValidation`<br>`MediatR` (opcional)<br>`Microsoft.Extensions.DependencyInjection`       | - Interfaces de servicios<br>- Casos de uso (por ej. `CreateUserUseCase.cs`)        |
| `AXIS.App.Core`           | **.NET Class Library**                       | Entidades del dominio, interfaces puras                          | No NuGet externo obligatorio                                                                                   | - Entidades (por ej. `User.cs`)<br>- Interfaces (`IUserRepository.cs`)              |
| `AXIS.App.Infrastructure` | **.NET Class Library**                       | Implementación de acceso a datos y servicios externos (DB, APIs) | `Microsoft.EntityFrameworkCore`<br>`EFCore.SqlServer`<br>`EFCore.Tools`<br>`Dapper` (opcional)<br>`AutoMapper` | - Repositorios (`UserRepository.cs`)<br>- Mapeo EF<br>- DB Context                  |
| `AXIS.App.Shared`         | **.NET Class Library**                       | DTOs, helpers, enums, clases comunes                             | `FluentValidation`<br>`Newtonsoft.Json` (opcional)<br>`System.Text.Json`                                       | - DTOs (`UserDto.cs`)<br>- Validadores<br>- Constantes<br>- Enums                   |
| `AXIS.App.Tests`          | **xUnit Test Project (.NET)**                | Tests unitarios e integrales                                     | `xUnit`<br>`Moq`<br>`FluentAssertions`<br>`AutoFixture`<br>`Microsoft.NET.Test.Sdk`                            | - Tests por capa: Application, Core, Infrastructure<br>- Mockeos                    |

---

### 📝 Recomendaciones adicionales

#### 🔧 En `App.UI`:

* Si usás **Blazor Server**: asegurate de agregar el script de Syncfusion al `_Layout.cshtml` o `index.html`

```html
<script src="_content/Syncfusion.Blazor/scripts/sf-blazor.min.js"></script>
```

* Agregá el servicio de Syncfusion en `Program.cs`:

```csharp
builder.Services.AddSyncfusionBlazor();
```

#### 🧪 En `App.Tests`:

* Estructura recomendada:

```
/App.Tests
  ├── Application
  ├── Core
  └── Infrastructure
```

* Usá **Moq** para testear sin acceso real a DB o servicios externos.

---

### 🧭 Flujo de dependencias entre capas

```
[App.UI]
   └── depende de → [App.Application]
                      └── depende de → [App.Core]
                      └── depende de → [App.Shared]

[App.Infrastructure]
   └── implementa interfaces de → [App.Core]
   └── depende de → [App.Shared]

[App.Tests]
   └── testea todas las capas anteriores
```

---

### 🧰 NuGet: instalación rápida por consola

```bash
# Desde Package Manager Console
Install-Package Syncfusion.Blazor -Project AXIS.App.UI
Install-Package AutoMapper -Project AXIS.App.Application
Install-Package FluentValidation -Project AXIS.App.Application
Install-Package Microsoft.EntityFrameworkCore.SqlServer -Project AXIS.App.Infrastructure
Install-Package xunit -Project AXIS.App.Tests
Install-Package Moq -Project AXIS.App.Tests
Install-Package FluentAssertions -Project AXIS.App.Tests
```

---



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg4MjYwODg0NF19
-->