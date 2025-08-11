# Instalación y configuración del entorno - Unity 2D

**Resumen:**  
Instalación y configuración del entorno, creación de un proyecto 2D, primer GameObject con script C# y prueba básica de movimiento. Ideal para arrancar desde cero.

**Objetivos**
- Instalar Unity Hub, Unity y el editor de C#.
- Configurar Visual Studio o VS Code para trabajar con Unity.
- Crear un proyecto 2D y conocer la interfaz (Scene, Game, Hierarchy, Inspector, Project, Console).
- Crear un `Player` con script `PlayerController` y probar movimiento.
- Reflexionar cómo explicar estos conceptos en clase.

**Duración sugerida:** 2 horas (ajustable)

---

## Requisitos previos
- Sistema operativo: Windows 10/11, macOS (o Linux con soporte Unity).
- Unity Hub (última versión estable).
- Versión recomendada de Unity: **Unity 2022 LTS** (o la LTS disponible en la fecha).
- Visual Studio (con workload *Game development with Unity*) **o** Visual Studio Code con extensiones:
  - C# (Microsoft)
  - Unity Debugger
- Espacio en disco: mínimo 5–10 GB libre.

---

## Pasos de la clase (guía rápida)

### 1) Instalar Unity Hub y Unity
- Descargar Unity Hub desde la web oficial.
- En Unity Hub → **Installs** → **Add** → elegir Unity 2022 LTS (o LTS disponible).
- Seleccionar módulos: **Visual Studio**, **Build Support** (Windows/Mac según necesites).

### 2) Configurar el editor de scripts
- **Visual Studio**: asegurarse de la carga *Game development with Unity*.
- **VS Code**: instalar extensiones *C#* y *Unity Debugger*.  
- En Unity → `Edit > Preferences > External Tools` → seleccionar el editor preferido.

### 3) Crear proyecto 2D
- Unity Hub → **New Project** → plantilla **2D** → nombre `MiPrimerJuego2D` → Create.

### 4) Conocer la interfaz (tour rápido)
- Scene / Game / Hierarchy / Inspector / Project / Console.
- Mostrar cómo arrastrar assets a la escena y cómo duplicar objetos.

### 5) Primer GameObject + Script
1. En *Hierarchy* → Create Empty → renombrar `Player`.
2. *Inspector* → Add Component → New Script: `PlayerController`.
3. Código de ejemplo (PlayerController.cs):

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

4.  Guardar y presionar **Play**. Verificar movimiento con flechas o A/D.
    

----------

## Actividades prácticas (entregable de la clase)

-   Subir al repo la carpeta del proyecto (o un zip) con:
    
    -   Escena inicial (`SampleScene`).
        
    -   Script `PlayerController.cs`.
        
    -   Un screenshot del juego en ejecución.
        
-   Tarea corta: modificar `speed` desde Inspector y explicar en 2 líneas qué hace `Time.deltaTime`.
    

----------

## Notas docentes / Reflexión

-   Explicar `Update()` como bucle por frame; usar analogías (ej.: reloj/latido).
    
-   Mostrar cómo las variables públicas facilitan pruebas en clase.
    
-   Sugerir una mini-demostración en vivo para ver `Debug.Log()`.
    

----------

## Checklist rápido (para correr la clase)

-   Unity Hub instalado
    
-   Unity 2022 LTS instalado con VS
    
-   Editor de scripts configurado
    
-   Proyecto 2D creado
    
-   `PlayerController` agregado y probado
    
-   Repo / Wiki actualizado con la unidad
    

----------

## Metadatos para la Wiki

-   Autor: Victor Hugo Contreras
    
-   Fecha: YYYY-MM-DD
    
-   Repositorio: `git@tu-git:org/proyecto-unity2d.git`
    
-   Ruta sugerida: `/docs/unidades/01-bienvenidos-unity.md`
    

## Ejemplo commit

`git add docs/unidades/01-bienvenidos-unity.md && git commit -m "Unidad 01: guía de instalación y primer script"`



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1MzE5NDE4NjJdfQ==
-->