# Planificación Detallada: Simulador de Ecosistema con Comportamiento Emergente

  

## Introducción

Este documento describe la planificación y desarrollo de un proyecto integrador para la asignatura Programación Concurrente y Paralela. El objetivo es simular un ecosistema donde múltiples entidades (depredadores, presas, recursos, clima) interactúan en un entorno dinámico, aplicando los conceptos de concurrencia, sincronización, paralelismo y patrones de diseño concurrente en Python.

  

---

  

## Unidad 1: Programación Concurrente

  

### Objetivos

- Comprender la concurrencia y su importancia en sistemas reales.

- Modelar entidades autónomas que interactúan en paralelo.

  

### Actividades

1.  **Modelado de entidades:**

- Crear clases para Depredador, Presa, Recurso y Clima.

- Ejemplo:

```python

class Depredador:

def __init__(self, id, posicion):

self.id = id

self.posicion = posicion

def mover(self):

# Lógica de movimiento

pass

```

2.  **Simulación concurrente básica:**

- Usar hilos (`threading.Thread`) para que cada entidad actúe de forma autónoma.

- Ejemplo:

```python

import threading

def ciclo_vida(entidad):

while  True:

entidad.mover()

# ... otras acciones

depredador = Depredador(1, (0,0))

t = threading.Thread(target=ciclo_vida, args=(depredador,))

t.start()

```

3.  **Visualización simple:**

- Mostrar el estado del ecosistema en consola (matriz, logs de acciones).

  

4.  **Discusión:**

- ¿Qué problemas aparecen cuando varias entidades acceden/modifican recursos al mismo tiempo?

  

---

  

## Unidad 2: Primitivas de Sincronización y el Modelo de Programación

  

### Objetivos

- Aplicar mecanismos de sincronización para coordinar entidades.

- Prevenir condiciones de carrera y deadlocks.

  

### Actividades

1.  **Uso de locks y semáforos:**

- Proteger acceso a recursos compartidos (por ejemplo, comida).

- Ejemplo:

```python

import threading

recurso_lock = threading.Lock()

def consumir_recurso():

with recurso_lock:

# Acceso seguro al recurso

pass

```

2.  **Modelar interacciones coordinadas:**

- Ejemplo: varias presas compiten por el mismo recurso.

- Usar semáforos para limitar el acceso concurrente.

```python

semaforo_comida = threading.Semaphore(3) # Solo 3 pueden comer a la vez

def comer():

with semaforo_comida:

# Comer

pass

```

3.  **Deadlocks y su resolución:**

- Forzar un deadlock y luego resolverlo (por ejemplo, dos entidades esperando recursos mutuamente).

- Ejemplo:

```python

# Ejemplo de deadlock clásico

lock_a = threading.Lock()

lock_b = threading.Lock()

def entidad1():

with lock_a:

with lock_b:

pass

def entidad2():

with lock_b:

with lock_a:

pass

```

  

---

  

## Unidad 3: Estructuras Paralelas y Paralelismo de Datos

  

### Objetivos

- Escalar la simulación y procesar grandes volúmenes de datos en paralelo.

- Medir y comparar el rendimiento.

  

### Actividades

1.  **Multiprocessing y pools:**

- Usar `multiprocessing.Pool` para procesar regiones del ecosistema en paralelo.

- Ejemplo:

```python

from multiprocessing import Pool

def procesar_region(region):

# Lógica de simulación para una región

pass

regiones = [r1, r2, r3, r4]

with Pool(4) as pool:

pool.map(procesar_region, regiones)

```

2.  **Asyncio para tareas asíncronas:**

- Usar `asyncio` para simular eventos concurrentes (por ejemplo, clima que afecta a todos).

- Ejemplo:

```python

import asyncio

async  def evento_climatico():

while  True:

# Cambia el clima

await asyncio.sleep(5)

asyncio.run(evento_climatico())

```

3.  **Medición de rendimiento:**

- Comparar tiempos de ejecución entre versiones secuenciales, concurrentes y paralelas.

- Graficar resultados (opcional).

  

---

  

## Unidad 4: Diseño de Patrones para Programación Concurrente

  

### Objetivos

- Aplicar patrones de diseño concurrente en la simulación.

- Analizar el impacto de los patrones en el comportamiento emergente.

  

### Actividades

1.  **Productor-Consumidor:**

- Recursos se generan (productores) y entidades los consumen (consumidores).

- Ejemplo:

```python

import queue

import threading

recursos = queue.Queue()

def productor():

while  True:

recursos.put('comida')

def consumidor():

while  True:

item = recursos.get()

# Consumir

```

2.  **Readers-Writers:**

- Varias entidades leen el estado del ecosistema, pocas lo modifican.

- Implementar control de acceso para evitar bloqueos innecesarios.

3.  **Pool de Hilos:**

- Usar un pool para manejar tareas concurrentes (por ejemplo, migraciones masivas).

4.  **Barrera de sincronización:**

- Sincronizar fases de la simulación (todos los hilos esperan antes de avanzar).

- Ejemplo:

```python

barrier = threading.Barrier(5)

def ciclo():

# ... acciones

barrier.wait() # Espera a que todos lleguen

```

  

---

  

## Evaluación y Entregables

- Código fuente documentado y modular.

- Informe con análisis de problemas, soluciones y resultados de pruebas.

- Presentación de la simulación y discusión de comportamiento emergente.

  

---

  

## Recursos Sugeridos

- Documentación oficial de Python: threading, multiprocessing, asyncio, queue.

- Tutoriales de visualización en consola y matplotlib.

- Ejemplos de patrones concurrentes en Python.

  

---

  

¿Dudas o sugerencias? ¡Consulta con tu profesor o revisa la documentación oficial de Python para profundizar en cada tema!
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM3NzUwOTgzMl19
-->