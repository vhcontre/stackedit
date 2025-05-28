
>Parcial de Programación Concurrente y Paralela – Unidad 1
>
### ✅ Fundamentos de Programación Concurrente – Unidad 1


**Instrucciones:** Elige la única opción correcta por cada pregunta.

----------

 **1. ¿Cuál de las siguientes afirmaciones describe mejor el concepto de concurrencia?**

a) Ejecutar múltiples procesos en diferentes núcleos de CPU.  
b) Ejecutar múltiples tareas en paralelo exacto sincrónicamente.  
c) Diseñar un sistema para manejar múltiples tareas de forma simultánea, aunque no necesariamente en paralelo.  
d) Ejecutar un proceso sin bloqueos ni espera.

----------

 **2. ¿Cuál de los siguientes problemas es más probable que ocurra cuando múltiples hilos acceden a una misma variable sin sincronización adecuada?**

a) Fuga de memoria.  
b) Fragmentación de pila.  
c) Condición de carrera.  
d) Pérdida de contexto.

----------

 **3. ¿Qué es un interbloqueo (deadlock) en el contexto de la programación concurrente?**

a) Una excepción generada por el sistema operativo al iniciar múltiples hilos.  
b) Una técnica para mejorar la seguridad entre procesos.  
c) Una situación en la que dos o más hilos esperan indefinidamente recursos que se bloquean mutuamente.  
d) Un mecanismo de prevención de acceso concurrente a memoria compartida.

----------

 **4. ¿Cuál de las siguientes NO es una ventaja de la concurrencia?**

a) Mejor aprovechamiento de CPU.  
b) Respuesta más ágil en aplicaciones interactivas.  
c) Simplicidad del código y menor complejidad.  
d) Mayor rendimiento en operaciones de I/O.

----------

 **5. ¿Qué diferencia clave existe entre paralelismo y concurrencia?**

a) El paralelismo se basa en interrupciones, mientras que la concurrencia usa polling.  
b) La concurrencia se refiere a múltiples tareas activas; el paralelismo implica ejecución simultánea real.  
c) Ambos conceptos son equivalentes, solo difieren en nomenclatura.  
d) El paralelismo solo aplica en sistemas operativos de tiempo real.

----------

 **6. En un sistema multihilo, ¿qué mecanismo permite que solo un hilo a la vez acceda a una sección crítica?**

a) Bucle de espera activa.  
b) Semáforo sincrónico.  
c) Sección dividida.  
d) Compilador JIT.

----------

 **7. ¿Cuál es el efecto de no liberar un recurso sincronizado como un `lock` o `semaphore` al finalizar su uso?**

a) El sistema liberará el recurso automáticamente sin consecuencias.  
b) Los hilos que lo necesiten quedarán en espera indefinida, pudiendo causar un interbloqueo.  
c) No tiene efecto si el código está bien escrito.  
d) El recurso será reasignado automáticamente al hilo con mayor prioridad.

----------

 **8. En un sistema con múltiples hilos que acceden a datos compartidos, ¿cuál de las siguientes estrategias mejora la seguridad de los datos?**

a) Desactivar la concurrencia.  
b) Usar variables globales sin control.  
c) Sincronizar el acceso mediante mutex o monitores.  
d) Aumentar el número de hilos para reducir conflictos.

----------

 **9. ¿Por qué es importante evitar condiciones de carrera en programas concurrentes?**

a) Porque reducen el uso de CPU.  
b) Porque pueden provocar resultados impredecibles y errores difíciles de reproducir.  
c) Porque hacen que el programa sea más lento pero más seguro.  
d) Porque duplican el uso de memoria.

----------

 **10. En programación concurrente, ¿cuál de los siguientes casos es un buen candidato para ser paralelizado?**

a) Cargar archivos de configuración únicos.  
b) Procesar elementos de una lista grande de manera independiente.  
c) Mostrar un mensaje de error en pantalla.  
d) Declarar variables locales dentro de una función.

----------



### ✅ Revisión Detallada de Respuestas

----------

**1. ¿Qué es concurrencia?**

✅ **Respuesta correcta:** **c)** Diseñar un sistema para manejar múltiples tareas de forma simultánea, aunque no necesariamente en paralelo.

**Justificación:** Concurrencia implica estructurar el software para que pueda gestionar múltiples tareas activas al mismo tiempo, pero no necesariamente ejecutarlas _literalmente_ al mismo tiempo (eso sería paralelismo). Por ejemplo, un solo núcleo puede alternar entre tareas.

----------

**2. ¿Qué problema ocurre sin sincronización adecuada?**

✅ **Respuesta correcta:** **c)** Condición de carrera.

**Justificación:** Una _condición de carrera_ sucede cuando dos o más hilos acceden y modifican una variable sin control, y el resultado depende del orden de ejecución. Esto puede producir errores intermitentes y difíciles de detectar.

----------

**3. ¿Qué es un interbloqueo (deadlock)?**

✅ **Respuesta correcta:** **c)** Dos o más hilos esperan recursos que el otro mantiene bloqueados.

**Justificación:** Un interbloqueo clásico es el "abrazo mortal": el Hilo A tiene el recurso 1 y espera el 2, mientras el Hilo B tiene el recurso 2 y espera el 1. Ninguno puede continuar.

----------

**4. ¿Qué NO es una ventaja de la concurrencia?**

✅ **Respuesta correcta:** **c)** Simplicidad del código y menor complejidad.

**Justificación:** Aunque la concurrencia puede mejorar rendimiento y capacidad de respuesta, **aumenta** la complejidad: hay que manejar sincronización, errores concurrentes, bloqueos, etc.

----------

**5. ¿Diferencia clave entre concurrencia y paralelismo?**

✅ **Respuesta correcta:** **b)** Concurrencia = múltiples tareas activas; Paralelismo = ejecución real simultánea.

**Justificación:** Se puede tener concurrencia sin paralelismo (ej. un solo hilo alternando tareas) y paralelismo sin concurrencia (ej. procesamiento masivo de datos sin interacción).

----------

**6. ¿Qué controla el acceso exclusivo a una sección crítica?**

✅ **Respuesta correcta:** **b)** Semáforo sincrónico (o `lock`, mutex, monitor).

**Justificación:** Un semáforo (o mecanismo similar como un monitor en C#) permite que solo un hilo entre a una sección crítica. El resto espera.

----------

**7. ¿Qué pasa si no se libera un recurso sincronizado?**

✅ **Respuesta correcta:** **b)** Se genera espera indefinida (posible interbloqueo).

**Justificación:** Si un hilo nunca libera el semáforo/mutex, otros quedan bloqueados indefinidamente esperando. Esto genera cuelgues o deadlocks.

----------

**8. ¿Cómo se asegura la integridad de datos compartidos?**

✅ **Respuesta correcta:** **c)** Usando mutex o monitores.

**Justificación:** Son mecanismos clásicos de sincronización para evitar conflictos de acceso simultáneo a recursos compartidos.

----------

**9. ¿Por qué evitar condiciones de carrera?**

✅ **Respuesta correcta:** **b)** Porque producen resultados impredecibles y errores difíciles de detectar.

**Justificación:** El orden no determinista de ejecución puede provocar valores incorrectos, incluso sin errores de compilación.

----------

**10. ¿Qué tarea es buena para paralelizar?**

✅ **Respuesta correcta:** **b)** Procesar elementos de una lista de forma independiente.

**Justificación:** Si cada elemento puede procesarse sin depender de los otros, es una situación ideal para dividir la carga entre varios hilos.



----------
>Parcial de Programación Concurrente y Paralela – Unidad 2
>
### ✅ # **Primitivas de Sincronización y el Modelo de Programación** – Unidad 2

----------

**1. ¿Cuál de las siguientes afirmaciones describe mejor la comunicación síncrona entre hilos?**  
a) Un hilo envía un mensaje sin esperar respuesta.  
b) Ambos hilos ejecutan tareas independientes y simultáneas.  
c) Un hilo se bloquea hasta que otro hilo complete su tarea.
d) Un hilo ejecuta múltiples tareas en paralelo sin compartir información.

----------

**2. ¿Qué ventaja principal ofrece el uso de `Thread.Join()` en C#?**  
a) Aumenta el rendimiento paralelizando tareas automáticamente.  
b) Libera memoria utilizada por hilos secundarios.  
c) Obliga al hilo actual a esperar la finalización de otro hilo.
d) Permite que dos hilos compartan el mismo ID de ejecución.

----------

**3. ¿Cuál es el objetivo principal de un semáforo en programación concurrente?**  
a) Ejecutar tareas en paralelo sin sincronización.  
b) Medir el rendimiento de múltiples hilos.  
c) Controlar el acceso concurrente a recursos compartidos.
d) Evitar la creación de hilos múltiples innecesarios.

----------

**4. ¿En qué se diferencia un monitor de un semáforo?**  
a) El monitor encapsula la sincronización dentro de una sección crítica protegida.  
b) El semáforo solo funciona en entornos distribuidos.  
c) El monitor permite múltiples accesos concurrentes.  
d) No existen diferencias entre ambos mecanismos.

----------

**5. ¿Qué describe mejor una región crítica?**  
a) Una parte del código donde los hilos se ejecutan sin interrupción.  
b) Una sección del programa donde se accede a un recurso compartido y debe protegerse.
c) Un espacio reservado en memoria para procesos secundarios.  
d) Un algoritmo que prioriza tareas en ejecución.

----------

**6. ¿Qué ocurre si múltiples hilos acceden simultáneamente a una región crítica sin sincronización?**  
a) Se maximiza la eficiencia.  
b) Se asegura la escalabilidad.  
c) Se pueden producir condiciones de carrera.
d) Se acelera la ejecución del código.

----------

**7. ¿Cuál es el propósito de un `AutoResetEvent` en C#?**  
a) Garantizar que un hilo termine antes que otro comience.  
b) Ejecutar varias tareas paralelas automáticamente.  
c) Permitir la comunicación entre hilos mediante señales.
d) Medir el tiempo de ejecución de múltiples tareas.

----------

**8. ¿Qué caracteriza a un modelo de programación _paralelo_ frente a uno _concurrente_?**  
a) El modelo paralelo usa menos recursos que el concurrente.  
b) El concurrente usa varios núcleos para ejecutar simultáneamente.  
c) El modelo paralelo ejecuta múltiples tareas al mismo tiempo en distintos núcleos.
d) Ambos modelos garantizan ejecución secuencial de tareas.

----------

**9. ¿Qué métrica se usa para evaluar la mejora de rendimiento al usar procesamiento paralelo?**  
a) Latencia de hilo.  
b) Speedup.
c) Volumen de transferencia.  
d) Prioridad de ejecución.

----------

**10. ¿Qué garantiza el uso de `Mutex` en una aplicación multihilo?**  
a) Que un hilo nunca sea bloqueado.  
b) Que solo un hilo acceda a la vez a una región crítica.
c) Que dos hilos compartan recursos simultáneamente.  
d) Que se distribuyan tareas en múltiples máquinas.

----------

### ✅ Respuestas Correctas y Justificaciones

**1. c) Un hilo se bloquea hasta que otro hilo complete su tarea.**

> Justificación: En la comunicación síncrona, un hilo espera (se bloquea) hasta que el otro termine, como se muestra con `Thread.Join()` en el ejemplo.

----------

**2. c) Obliga al hilo actual a esperar la finalización de otro hilo.**

> Justificación: `Thread.Join()` detiene la ejecución del hilo actual hasta que el hilo indicado finaliza. Es clave para sincronización entre tareas dependientes.

----------

**3. c) Controlar el acceso concurrente a recursos compartidos.**

> Justificación: Un semáforo restringe la cantidad de hilos que acceden simultáneamente a un recurso, evitando condiciones de carrera.

----------

**4. a) El monitor encapsula la sincronización dentro de una sección crítica protegida.**

> Justificación: El `lock` en C# es un monitor que impide el acceso simultáneo a secciones críticas. Los semáforos, en cambio, permiten control más general.

----------

**5. b) Una sección del programa donde se accede a un recurso compartido y debe protegerse.**

> Justificación: Las regiones críticas requieren protección con mecanismos como `lock`, `Mutex` o `Semaphore` para evitar inconsistencias.

----------

**6. c) Se pueden producir condiciones de carrera.**

> Justificación: Si varios hilos acceden sin protección a un recurso, los resultados pueden ser impredecibles debido a interferencias entre hilos.

----------

**7. c) Permitir la comunicación entre hilos mediante señales.**

> Justificación: `AutoResetEvent` es una señal que un hilo puede esperar (`WaitOne()`) y otro puede activar (`Set()`), habilitando coordinación.

----------

**8. c) El modelo paralelo ejecuta múltiples tareas al mismo tiempo en distintos núcleos.**

> Justificación: A diferencia de la concurrencia (que puede intercalar tareas en un solo núcleo), el paralelismo real requiere múltiples núcleos trabajando simultáneamente.

----------

**9. b) Speedup.**

> Justificación: El _speedup_ es una métrica que compara el tiempo de ejecución secuencial vs. paralelo, para medir la mejora obtenida por paralelizar.

----------

**10. b) Que solo un hilo acceda a la vez a una región crítica.**

> Justificación: `Mutex` es una herramienta de sincronización que garantiza exclusividad total en el acceso a recursos compartidos.


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg1Mzk4MzI0MV19
-->