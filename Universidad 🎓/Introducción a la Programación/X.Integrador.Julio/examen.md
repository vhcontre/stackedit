Perfectamente claro. Vamos a redactar el **enunciado completo del examen integrador**, en **formato profesional de evaluación**, especificando:

* **Contexto realista**
* **Reglas de negocio bien definidas**
* **Funciones principales obligatorias con nombres fijos**
* **Validaciones obligatorias**, pero permitiendo que los estudiantes las implementen con los nombres que deseen
* Restricción clara: **separar entrada de datos (inputs) de la lógica de negocio**

---

## Examen Integrador – Introducción a la Programación

Contenido: Listas, estructuras de repetición, validación de datos y modularidad
Modalidad: Resolución individual – Duración 90 minutos



### 🦷 Contexto General

El consultorio odontológico “Sonrisa Feliz” necesita un pequeño sistema que le permita **gestionar los turnos de atención de los pacientes**.

El sistema debe ser capaz de registrar turnos, modificar su estado, cancelar turnos y mostrar la lista de todos los turnos cargados.


### Reglas de negocio (a respetar estrictamente)

#### Estructura de un turno (almacenar en una lista):

Cada turno debe guardar los siguientes campos:

* **Paciente**: nombre y apellido (texto, no vacío)
* **DNI**: cadena de números (no vacío, debe ser numérico)
* **Día del turno**: número entero entre 1 y 31
* **Hora del turno**: número entero entre 8 y 20 (formato 24h)
* **Estado del turno**: puede ser "pendiente", "atendido" o "cancelado"


###  Funciones principales del sistema (obligatorias)

Estas funciones deben **recibir los datos validados por parámetro**. No deben utilizar `input()` ni realizar validaciones.

1. `agendar_turno(paciente, dni, dia, hora)`

   * Agrega un nuevo turno con estado `"pendiente"`
   * Antes de agendar, verificar si **ya existe un turno para ese DNI, día y hora**
   * En caso de duplicado, no se debe agregar

2. `modificar_estado_turno(dni, nuevo_estado)`

   * Cambia el estado del turno de un paciente al valor indicado (`"atendido"` o `"cancelado"`)
   * Si no existe el turno, informar al usuario

3. `eliminar_turno(dni)`

   * Permite eliminar un turno únicamente si su estado es `"pendiente"`
   * Si no existe el turno o su estado no es `"pendiente"`, mostrar mensaje correspondiente

4. `listar_turnos()`

   * Muestra todos los turnos registrados con todos sus datos
   * Si no hay turnos, debe informarse al usuario



### Validaciones obligatorias (deben realizarse antes de invocar a las funciones anteriores)

Deberás crear funciones auxiliares (helpers) para realizar las siguientes validaciones:

* Validar que el **DNI** sea numérico y no esté vacío
* Validar que el **nombre completo** del paciente no esté vacío
* Validar que el **día del turno** esté entre 1 y 31
* Validar que la **hora del turno** esté entre 8 y 20
* Validar que el **estado ingresado** para modificar esté entre `"atendido"` o `"cancelado"`

Los nombres de estas funciones auxiliares pueden ser definidos libremente, pero deben estar separadas y cumplir con su función específica.

---

### 🧭 Estructura del menú principal

El menú debe ofrecer estas opciones:

1. Agendar turno
2. Modificar estado de un turno
3. Eliminar turno
4. Listar todos los turnos
5. Salir

---

### 🔒 Restricciones

* No utilizar funciones predefinidas como `max()`, `min()`, `filter()`, `lambda`, etc.
* No usar estructuras como diccionarios ni clases
* Solo se permite usar **listas (arrays)**
* El código debe estar dividido en funciones
* No se permite que las funciones principales tengan `input()`
* Se deben validar todos los datos antes de pasar a las funciones principales

---

### 📢 Recomendaciones finales

* Pensá bien la estructura de tu solución antes de comenzar
* Dividí tu código en funciones pequeñas y claras
* Revisá los nombres de tus variables para que representen lo que hacen
* Prestá atención a los límites y validaciones requeridas

---

¿Querés que te lo arme ahora como un **PDF formateado** o como un documento `.docx` para compartir con tus estudiantes? También puedo agregar una **rúbrica de evaluación** si te parece útil.

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3NzAxMDU5NjgsMTYxOTY5MTI0OF19
-->