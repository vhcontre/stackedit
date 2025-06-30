## 📄 Examen Integrador

📚 Contenido: Registro, modificación, eliminación, listado y estadísticas
📘 Asignatura: Introducción a la Programación
🎯 Contexto: **Sistema de Gestión de Turnos de Consultorio Odontológico**
-------------------------------------------------------------------------

### 🧱 Estructura de un Turno:

* Paciente (str): nombre y apellido del paciente.
* DNI (str)
* Día (int): número del día del mes (entre 1 y 31).
* Hora (int): franja horaria en formato 24h (entre 8 y 20).
* Estado (str): "pendiente", "atendido", "cancelado"

---

### 📌 Funcionalidades:

#### Helper: `turno_duplicado(dni, dia, hora)`

* Verifica si un paciente ya tiene un turno asignado en ese día y hora.
* Devuelve `True` si el turno ya existe, `False` en caso contrario.

#### Helper: `buscar_turno_por_dni(dni)`

* Devuelve el índice del turno si lo encuentra, o `-1` si no existe.

---

### Funciones principales

1. `agendar_turno()`

   * Solicita nombre completo, DNI, día y hora del turno.
   * Valida que los datos no estén vacíos.
   * Valida que el día esté entre 1 y 31 y la hora entre 8 y 20.
   * Verifica que no exista un turno duplicado para ese paciente en esa fecha/hora.
   * El estado se inicializa como `"pendiente"`.

2. `modificar_estado_turno()`

   * Solicita DNI.
   * Permite cambiar el estado a "atendido" o "cancelado".
   * Valida que el turno exista.

3. `eliminar_turno()`

   * Permite eliminar un turno **solo si está en estado "pendiente"**.
   * Valida existencia y estado.

4. `listar_turnos()`

   * Muestra todos los turnos con nombre del paciente, DNI, día, hora y estado.
   * Informa si no hay turnos cargados.

5. `mostrar_estadisticas()`

   * Muestra:

     * Cantidad de turnos "pendientes"
     * Cantidad de turnos "atendidos"
     * Cantidad de turnos "cancelados"

---

### ✔️ Restricciones:

* No se deben usar funciones predefinidas como `max()` ni estructuras avanzadas.
* Solo listas (arrays).
* No se permite el uso de librerías externas.



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYxOTY5MTI0OF19
-->