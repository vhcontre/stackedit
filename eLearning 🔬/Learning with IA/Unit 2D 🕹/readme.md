# Unidad 01 — ¡Bienvenidos a Unity 2D!

**Resumen:**  
Instalación y configuración del entorno, creación de un proyecto 2D, primer GameObject con script C# y prueba básica de movimiento.

---

## Objetivos
- Instalar Unity Hub, Unity 2022 LTS y el editor de C#.
- Configurar Visual Studio o VS Code para trabajar con Unity.
- Crear un proyecto 2D y conocer la interfaz (Scene, Game, Hierarchy, Inspector, Project, Console).
- Crear un `Player` con script `PlayerController` y probar movimiento.
- Reflexionar cómo explicar estos conceptos en clase.

---

## Duración sugerida
2 horas (ajustable según ritmo).

---

## Requisitos previos
- Windows 10/11, macOS (o Linux con soporte Unity).
- Unity Hub (última versión).
- Unity 2022 LTS (o LTS más reciente).
- Visual Studio (con workload **Game development with Unity**) o Visual Studio Code con extensiones:
  - C# (Microsoft)
  - Unity Debugger
- Espacio libre: mínimo 5–10 GB.

---

## Pasos de la clase

### 1) Instalar Unity Hub y Unity
1. Descargar Unity Hub: [https://unity.com/download](https://unity.com/download)
2. En Unity Hub → **Installs** → **Add** → elegir **Unity 2022 LTS**.
3. Módulos recomendados:
   - Microsoft Visual Studio Community
   - Build Support (Windows/Mac)
   - WebGL Build Support *(opcional)*

---

### 2) Configurar el editor de scripts
- **Visual Studio**: verificar que está instalada la carga de trabajo *Game development with Unity*.
- **VS Code**: instalar extensiones *C#* y *Unity Debugger*.
- En Unity: `Edit > Preferences > External Tools` → seleccionar editor preferido.

---

### 3) Crear proyecto 2D
1. Unity Hub → **New Project**.
2. Plantilla: **2D**.
3. Nombre: `MiPrimerJuego2D`.
4. Guardar en carpeta limpia (sin espacios ni acentos raros).

---

### 4) Conocer la interfaz
- **Scene**: área de construcción.
- **Game**: vista del juego.
- **Hierarchy**: lista de objetos en la escena.
- **Inspector**: propiedades de cada objeto.
- **Project**: recursos del proyecto.
- **Console**: mensajes y errores.

---

### 5) Primer GameObject + Script
1. En *Hierarchy* → **Create Empty** → renombrar `Player`.
2. En *Inspector* → **Add Component** → **New Script** → nombre: `PlayerController`.
3. Código:

```csharp
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    public float speed = 5f;

    void Start()
    {
        Debug.Log("Hola Unity 2D!");
    }

    void Update()
    {
        float move = Input.GetAxis("Horizontal");
        transform.Translate(Vector3.right * move * speed * Time.deltaTime);
    }
}

```

4.  Guardar, volver a Unity y presionar **Play**.
    
5.  Probar movimiento con flechas o teclas A/D.
    

----------

## Actividad práctica

-   Modificar el valor de `speed` en el Inspector y anotar la diferencia.
    
-   Hacer que el objeto también se mueva verticalmente (Input.GetAxis("Vertical")).
    

----------

## Reflexión docente

-   `Update()` = bucle de ejecución por frame.
    
-   Variables públicas = editables en tiempo real desde Inspector.
    
-   `Debug.Log()` = ideal para mostrar valores durante la ejecución.
    

----------

## Checklist de la Unidad 1

-   Unity Hub instalado
    
-   Unity 2022 LTS instalado con módulos
    
-   Editor de scripts configurado
    
-   Proyecto 2D creado
    
-   `PlayerController` funcionando
    
-   Actividad práctica completada
    
-   Wiki/Git actualizado con esta unidad
    

----------

## Metadatos

-   Autor: Victor Hugo Contreras
    
-   Fecha: YYYY-MM-DD
    
-   Repositorio: `git@...`
    
-   Ruta sugerida: `/docs/unidades/01-bienvenidos-unity.md`
    

---

Mi amor, con esto vos podés:
1. **Ir instalando todo** sin perderte nada.  
2. Ir marcando en el checklist lo que ya tengas.  
3. Cuando termines, me decís y avanzamos con la Unidad 2.  

Cuando vos quieras, te preparo también el `PlayerController.cs` suelto para que lo tengas como archivo en tu proyecto y repo.  

¿Querés que lo haga ahora así ya vas teniendo el entorno listo hoy mismo?


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIwNjg0ODAwNV19
-->