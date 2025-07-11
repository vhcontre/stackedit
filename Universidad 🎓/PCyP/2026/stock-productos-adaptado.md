1. Introducción y Motivación
	Breve repaso del sistema de inventario.
	Presentación de escenarios reales donde múltiples usuarios acceden y modifican el inventario al mismo tiempo.
	Planteo del problema: ¿qué ocurre si dos usuarios intentan modificar el stock de un producto simultáneamente?

2. Actividades por Unidad
	Unidad 1: Programación Concurrente
	Implementar endpoints en FastAPI que permitan modificar el stock de productos.
	Simular múltiples clientes (usando Angular o scripts) que realizan operaciones concurrentes sobre el inventario.
	Analizar resultados: inconsistencias, condiciones de carrera, etc.

Unidad 2: Primitivas de Sincronización y el Modelo de Programación
	Incorporar primitivas de sincronización en el backend (locks, semáforos, etc.) para proteger operaciones críticas.
	Comparar el comportamiento antes y después de la sincronización.
	Ejercicios: forzar y resolver condiciones de carrera.

Unidad 3: Estructuras Paralelas y Paralelismo de Datos
	Implementar procesamiento paralelo de operaciones masivas (por ejemplo, actualización de stock de muchos productos en paralelo).
	Usar hilos, procesos o async/await según corresponda.
	Medir y comparar el rendimiento entre ejecución secuencial y paralela.

Unidad 4: Diseño de Patrones para Programación Concurrente
	Aplicar patrones como Productor-Consumidor, Pool de Hilos, o Readers-Writers en el backend.
	Ejemplo: un endpoint que procese pedidos en lote usando un pool de hilos.
	Analizar ventajas y desventajas de cada patrón aplicado.

3. Evaluación y Reflexión
	Documentar los problemas encontrados y las soluciones aplicadas.
	Reflexionar sobre la importancia de la concurrencia y la sincronización en sistemas reales.
	Presentar resultados de pruebas de estrés y rendimiento.

4. Entregables
	Código fuente del backend y frontend.
	Scripts de simulación de clientes concurrentes.
	Informe con análisis de problemas, soluciones y resultados de pruebas.
	(Opcional) Video demostrativo de la aplicación en funcionamiento bajo carga concurrente.

5. Herramientas y tecnologías sugeridas
	Backend: FastAPI (Python), MySQL (Docker)
	Frontend: Angular (o scripts de simulación)
	Pruebas: pytest, locust, o scripts personalizados
	Docker y Docker Compose para orquestación
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTMwNjQzOTUxMF19
-->