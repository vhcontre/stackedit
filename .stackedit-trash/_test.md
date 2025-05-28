¡Perfecto! Vamos a convertir **todas las secciones** anteriores en un formato **100% limpio, profesional y compatible con GitHub Wiki**.

----------

## 🧠 Simulación: Cajeros y clientes en un banco

Este programa simula una situación en la que varios clientes (hilos) intentan acceder a un recurso limitado (cajeros). Se utilizan semáforos para controlar la concurrencia, con mejoras modernas y métricas.

----------

## 🔧 Comportamiento básico

Elemento del mundo real

Representación en código

Descripción

Cajeros

`Semaphore(3, 3)`

Controla la cantidad de clientes que pueden ser atendidos simultáneamente.

Clientes

`Task.Run()`

Cada cliente se representa como una tarea concurrente.

Atención al cliente

`Task.Delay()`

Simula el tiempo que tarda un cajero en atender al cliente.

Cola de espera

`WaitAsync(TimeSpan)`

Si todos los cajeros están ocupados, el cliente espera hasta cierto tiempo.

Fin de atención

`semaforo.Release()`

El cliente libera el cajero una vez finalizada su atención.

----------

## 🚀 Mejoras implementadas

Mejora

Implementación

Uso moderno de hilos

Se utiliza `Task.Run()` en lugar de `Thread`, lo cual es más eficiente y escalable.

Tiempo máximo de espera

Se utiliza `WaitAsync(TimeSpan)` para permitir que un cliente abandone si espera demasiado.

Contadores seguros

`Interlocked.Increment()` asegura que las estadísticas sean correctas en concurrencia.

Liberación garantizada

Uso de `try/finally` para asegurar que el semáforo se libere aunque haya errores.

Métricas de ejecución

Se contabilizan clientes atendidos y los que se van sin atención.

----------

## 💻 Código de ejemplo

```csharp
using System;
using System.Threading;
using System.Threading.Tasks;

class Program
{
    static SemaphoreSlim cajeros = new SemaphoreSlim(3, 3);
    static int clientesAtendidos = 0;
    static int clientesQueSeFueron = 0;

    static async Task Main()
    {
        var tareas = new Task[10];

        for (int i = 0; i < 10; i++)
        {
            int idCliente = i + 1;
            tareas[i] = Task.Run(() => AtenderCliente(idCliente));
        }

        await Task.WhenAll(tareas);

        Console.WriteLine($"\nResumen final:");
        Console.WriteLine($"Clientes atendidos: {clientesAtendidos}");
        Console.WriteLine($"Clientes que se fueron sin ser atendidos: {clientesQueSeFueron}");
    }

    static async Task AtenderCliente(int id)
    {
        Console.WriteLine($"Cliente {id} está esperando un cajero...");

        if (await cajeros.WaitAsync(TimeSpan.FromSeconds(2)))
        {
            try
            {
                Console.WriteLine($"Cliente {id} está siendo atendido...");
                Interlocked.Increment(ref clientesAtendidos);
                await Task.Delay(new Random().Next(1000, 3000));
                Console.WriteLine($"Cliente {id} terminó y deja el cajero.");
            }
            finally
            {
                cajeros.Release();
            }
        }
        else
        {
            Console.WriteLine($"Cliente {id} se cansó de esperar y se fue.");
            Interlocked.Increment(ref clientesQueSeFueron);
        }
    }
}

```

----------

## 📈 Resultado esperado

La salida varía según los tiempos de espera y atención. Un ejemplo podría ser:

```
Cliente 1 está esperando un cajero...
Cliente 2 está esperando un cajero...
Cliente 3 está esperando un cajero...
Cliente 1 está siendo atendido...
Cliente 2 está siendo atendido...
Cliente 3 está siendo atendido...
Cliente 4 está esperando un cajero...
Cliente 4 se cansó de esperar y se fue.
...
Resumen final:
Clientes atendidos: 7
Clientes que se fueron sin ser atendidos: 3

```

----------

¿Querés que te lo pase en archivo `.md` listo para subir? También puedo ayudarte con la organización general de tu wiki si querés secciones tipo índice, navegación, etc.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNjIxNTcyNDZdfQ==
-->