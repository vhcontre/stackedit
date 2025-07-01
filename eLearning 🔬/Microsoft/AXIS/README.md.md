# AXIS - Arquitectura Base en .NET 8 con Syncfusion

  

Este proyecto es una plantilla base para desarrollar aplicaciones modulares y escalables en .NET 8, utilizando componentes Syncfusion para la interfaz y una arquitectura limpia basada en capas.

  

---

  

## 🧱 Estructura del Proyecto

  

| Proyecto | Tipo de Proyecto | Descripción breve |

|---------------------------|----------------------------|----------------------------------------------------------|

| `AXIS.App.UI` | Blazor Server / ASP.NET MVC| Interfaz de usuario, Syncfusion UI |

| `AXIS.App.Application` | Class Library (.NET) | Casos de uso, servicios de aplicación |

| `AXIS.App.Core` | Class Library (.NET) | Entidades y lógica de dominio |

| `AXIS.App.Infrastructure` | Class Library (.NET) | Acceso a datos, servicios externos, EF Core |

| `AXIS.App.Shared` | Class Library (.NET) | DTOs, constantes, helpers, validaciones |

| `AXIS.App.Tests` | xUnit Test Project | Tests unitarios e integrales |

  

---

  

## 📦 NuGet Recomendados

  

- Syncfusion.Blazor (UI)

- AutoMapper (mapeos)

- FluentValidation (validación)

- Microsoft.EntityFrameworkCore.SqlServer (acceso a DB)

- xUnit, Moq, FluentAssertions (tests)

  

---

  

## 🧪 Instalación rápida (Package Manager Console)

  

```powershell

Install-Package Syncfusion.Blazor -Project AXIS.App.UI

Install-Package AutoMapper -Project AXIS.App.Application

Install-Package FluentValidation -Project AXIS.App.Application

Install-Package Microsoft.EntityFrameworkCore.SqlServer -Project AXIS.App.Infrastructure

Install-Package xunit -Project AXIS.App.Tests

Install-Package Moq -Project AXIS.App.Tests

Install-Package FluentAssertions -Project AXIS.App.Tests

```

  

---

  

## ⚙️ Dependencias entre proyectos

  

```plaintext

[App.UI]

└── App.Application

└── App.Core

└── App.Shared

  

[App.Infrastructure]

└── App.Core

└── App.Shared

  

[App.Tests]

└── testea todas las capas anteriores

```

  

---

  

## 🚀 Primeros pasos

  

1. Clonar el proyecto o usar la estructura ZIP.

2. Crear los `.csproj` de cada proyecto.

3. Instalar los NuGet recomendados.

4. Agregar páginas y servicios de prueba.

5. ¡Listo para desarrollar!

  

---

  

© Proyecto AXIS - Base para aplicaciones .NET 8
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAxMTY1MDYzOV19
-->