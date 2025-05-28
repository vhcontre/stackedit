## 🌐 **Ejemplo: Web API en .NET 6+ con Programación Asíncrona y Paralela**

### 🔹 **Escenario**

Vamos a simular una API que tiene dos endpoints:

1.  `/procesar-datos` → Procesa datos de manera asíncrona.
    
2.  `/descargar-archivos` → Simula la descarga de múltiples archivos en paralelo.
    

----------

### 1️⃣ **Crear el Proyecto Web API en .NET 6+**

Ejecuta el siguiente comando para crear el proyecto:

```sh
dotnet new webapi -n AsyncParallelApi
cd AsyncParallelApi

```

----------

### 2️⃣ **Instalar Dependencias (Opcional)**

Si necesitas `System.Threading.Tasks`, ya viene incluido en .NET 6+, pero asegúrate de que está en el `csproj`:

```xml
<ItemGroup>
    <PackageReference Include="System.Threading.Tasks.Extensions" Version="4.5.4" />
</ItemGroup>

```

----------

### 3️⃣ **Implementación en `Program.cs`**

Abre el archivo `Program.cs` y reemplázalo con el siguiente código:

```csharp
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Http;
using Microsoft.Extensions.Hosting;
using System;
using System.Diagnostics;
using System.Threading.Tasks;
using System.Collections.Generic;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "API de Ejemplo con Programación Asíncrona y Paralela");

/// 📌 Endpoint que procesa datos de manera asíncrona
app.MapGet("/procesar-datos", async () =>
{
    var stopwatch = Stopwatch.StartNew();

    Console.WriteLine("Iniciando procesamiento...");
    await Task.Delay(3000); // Simula un proceso de 3 segundos
    Console.WriteLine("Procesamiento finalizado.");

    stopwatch.Stop();
    return Results.Ok(new { Mensaje = "Datos procesados", Tiempo = stopwatch.ElapsedMilliseconds });
});

/// 📌 Endpoint que simula la descarga de archivos en paralelo
app.MapGet("/descargar-archivos", async () =>
{
    var stopwatch = Stopwatch.StartNew();

    Console.WriteLine("Iniciando descargas...");
    
    List<Task> tareas = new()
    {
        DescargarArchivoAsync("Archivo1"),
        DescargarArchivoAsync("Archivo2"),
        DescargarArchivoAsync("Archivo3")
    };

    await Task.WhenAll(tareas); // Espera que todas las descargas finalicen

    stopwatch.Stop();
    return Results.Ok(new { Mensaje = "Descargas finalizadas", Tiempo = stopwatch.ElapsedMilliseconds });
});

/// 📌 Método asíncrono que simula la descarga de un archivo
async Task DescargarArchivoAsync(string nombreArchivo)
{
    Console.WriteLine($"Descargando {nombreArchivo}...");
    await Task.Delay(2000); // Simula una espera de 2 segundos
    Console.WriteLine($"{nombreArchivo} descargado.");
}

app.Run();

```

----------

### 4️⃣ **Ejecutar la API**

Corre la API con el siguiente comando:

```sh
dotnet run

```

La API estará disponible en:

-   [http://localhost:5000](http://localhost:5000/)
    

----------

### 5️⃣ **Probar la API**

Puedes probar los endpoints con **Postman** o **cURL**:

📌 **Procesar datos (asíncrono)**

```sh
curl http://localhost:5000/procesar-datos

```

📌 **Descargar archivos (paralelo)**

```sh
curl http://localhost:5000/descargar-archivos

```

----------

### 🔥 **Explicación**

-   **`Task.Delay(3000)`**: Simula una tarea asíncrona de 3 segundos.
    
-   **`Task.Run()`**: Ejecuta código en un hilo separado.
    
-   **`await Task.WhenAll(tareas)`**: Ejecuta múltiples tareas en paralelo y espera su finalización.
    
-   **`Stopwatch`**: Mide el tiempo de ejecución.
    

----------

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2ODQzMTg2NzJdfQ==
-->