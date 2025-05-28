### 🎯 Objetivos de la adaptación

1.  **Permitir el uso de herramientas como GitHub Copilot.**
    
2.  **Evitar que simplemente copien código sin entenderlo.**
    
3.  **Detectar razonamiento, comprensión y corrección de errores.**
    
4.  **Fomentar depuración, análisis y pensamiento crítico.**
    

----------

## ✅ Versión adaptada del examen

```python
"""
Este programa permite gestionar una lista de estudiantes. Algunas funciones están incompletas o tienen errores.

Tu tarea es analizar, completar y corregir el código según lo indicado en cada sección.

Funciones principales a implementar o corregir:
- Verificación de DNI duplicado.
- Búsqueda por DNI.
- Agregar estudiante con validación.
- Modificar nota (con errores de lógica que debes encontrar).
- Eliminar estudiante (con errores de validación).
- Mostrar estadísticas (tiene errores lógicos).
- Listar estudiantes.
"""

estudiantes = []

def dni_duplicado(dni):
    # Código con error lógico: ¿qué devuelve realmente?
    for e in estudiantes:
        if e[2] == dni:
            return False
    return True  # <-- Esto es incorrecto. ¿Por qué?

def buscar_por_dni(dni):
    # TODO: Implementar búsqueda que devuelva el índice del estudiante o -1 si no existe
    return -1

def agregar_estudiante():
    nombre = input("Nombre: ")
    apellido = input("Apellido: ")
    dni = input("DNI: ")
    
    if not nombre or not apellido or not dni:
        print("Todos los campos son obligatorios.")
        return
    
    if not dni.isdigit():
        print("El DNI debe ser numérico.")
        return
    
    if not dni_duplicado(dni):  # <-- Revisa si esta validación es correcta
        print("DNI duplicado.")
        return
    
    estudiante = [nombre, apellido, dni, -1, "ausente"]
    estudiantes.append(estudiante)
    print("Estudiante agregado correctamente.")

def modificar_nota():
    dni = input("DNI del estudiante a modificar: ")
    indice = buscar_por_dni(dni)

    if indice == -1:
        print("Estudiante no encontrado.")
        return

    try:
        nota = int(input("Ingrese la nueva nota: "))
        if nota < 0 or nota > 10:
            print("Nota fuera de rango.")
            return
    except:
        print("Error: nota inválida.")
        return

    estudiantes[indice][3] = nota
    if nota == 0:
        estudiantes[indice][4] = "ausente"
    elif nota >= 6:
        estudiantes[indice][4] = "reprobado"  # <-- Error intencional: ¿es correcto?
    else:
        estudiantes[indice][4] = "aprobado"   # <-- ¿Qué pasa aquí?

def eliminar_estudiante():
    dni = input("DNI del estudiante a eliminar: ")
    indice = buscar_por_dni(dni)

    if indice == -1:
        print("Estudiante no encontrado.")
        return

    if estudiantes[indice][3] != 0:  # <-- Error: ¿cuándo debe eliminarse?
        print("No se puede eliminar un estudiante con nota asignada.")
        return

    del estudiantes[indice]
    print("Estudiante eliminado.")

def listar_estudiantes():
    if not estudiantes:
        print("No hay estudiantes registrados.")
        return

    for e in estudiantes:
        print(f"{e[0]} {e[1]} - DNI: {e[2]} - Nota: {e[3]} - Condición: {e[4]}")

def mostrar_estadisticas():
    aprobados = 0
    reprobados = 0
    ausentes = 0

    for e in estudiantes:
        if e[4] == "aprobado":
            reprobados += 1  # <-- Error: ¿por qué se suma acá?
        elif e[4] == "reprobado":
            aprobados += 1
        else:
            ausentes += 1

    print(f"Aprobados: {aprobados}")
    print(f"Reprobados: {reprobados}")
    print(f"Ausentes: {ausentes}")

def menu():
    while True:
        print("\n--- Menú de opciones ---")
        print("1. Agregar estudiante")
        print("2. Modificar nota")
        print("3. Eliminar estudiante")
        print("4. Listar estudiantes")
        print("5. Mostrar estadísticas")
        print("6. Salir")

        opcion = input("Seleccione una opción: ")
        if opcion == "1":
            agregar_estudiante()
        elif opcion == "2":
            modificar_nota()
        elif opcion == "3":
            eliminar_estudiante()
        elif opcion == "4":
            listar_estudiantes()
        elif opcion == "5":
            mostrar_estadisticas()
        elif opcion == "6":
            print("¡Hasta luego!")
            break
        else:
            print("Opción inválida.")

if __name__ == "__main__":
    menu()

```

----------

## 🔍 ¿Qué evalúas realmente con esta versión?

-   Comprensión del código generado por IA.
    
-   Capacidad de identificar errores lógicos.
    
-   Razonamiento sobre flujos y validaciones.
    
-   Uso correcto de listas, estructuras, condicionales, e input/output.
    

----------

## 💡 Estrategia para aplicarlo

1.  **Permite Copilot**: y explícitamente diles que pueden usarlo.
    
2.  **Haz foco en razonamiento**: Pídeles explicar por escrito los errores corregidos y por qué.
    
3.  **Haz preguntas reflexivas orales o escritas**:
    
    -   ¿Por qué cambiaste esa condición?
        
    -   ¿Qué hacía mal esta función?
        
    -   ¿Qué pasa si la lista está vacía?
        

----------
**Rúbrica de evaluación** diseñada para un examen donde se permite el uso de IA como GitHub Copilot, pero se evalúa principalmente la **comprensión, análisis, corrección y razonamiento** del estudiante:

---

## ✅ RÚBRICA DE EVALUACIÓN PARA EXAMEN CON IA (Python – Gestión de Estudiantes)

| Criterio                                          | Excelente (10)                                                                                | Bueno (7-9)                                                                                | Regular (4-6)                                                                    | Insuficiente (0-3)                                                        |
| ------------------------------------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| **Comprensión del código con errores**            | Detecta y explica claramente **todos** los errores lógicos del código proporcionado.          | Detecta y explica la mayoría de los errores. Algunos no completamente entendidos.          | Detecta parcialmente los errores. Omite o malinterpreta algunos.                 | No detecta errores o los interpreta incorrectamente.                      |
| **Corrección de errores**                         | Corrige de forma **precisa y justificada** todos los errores. El programa queda funcional.    | Corrige casi todos los errores, pero deja detalles menores o con advertencias.             | Corrige parcialmente. Algunas correcciones son incompletas o con nuevos errores. | No realiza correcciones efectivas. El programa no funciona correctamente. |
| **Implementación de funciones vacías**            | Implementa todas las funciones requeridas correctamente, con buena estructura y validaciones. | Implementa la mayoría correctamente. Algunos detalles menores faltan o están incorrectos.  | Implementa algunas funciones. Faltan validaciones importantes.                   | Deja varias funciones sin implementar o con errores graves.               |
| **Razonamiento y justificación (escrita u oral)** | Justifica claramente cada cambio, con lenguaje propio. Muestra comprensión profunda.          | Justifica la mayoría de las decisiones con claridad. Usa algo de lenguaje técnico copiado. | Justifica algunas decisiones de forma vaga o superficial.                        | No justifica o da respuestas copiadas sin comprensión.                    |
| **Manejo de la herramienta IA**                   | Usa Copilot como apoyo para probar ideas, pero con criterio propio. Refactoriza y adapta.     | Usa Copilot adecuadamente, pero sigue demasiado sus sugerencias textuales.                 | Depende excesivamente de Copilot. Aporta poco de elaboración propia.             | Copia sin analizar o ni siquiera utiliza la herramienta.                  |
| **Funcionamiento final del programa**             | El programa funciona perfectamente con todos los flujos esperados y validaciones.             | Funciona bien, con pequeñas fallas que no afectan gravemente.                              | Funciona parcialmente. Falla en casos importantes o se rompe fácilmente.         | No funciona o tiene errores de ejecución severos.                         |
| **Estilo de código y buenas prácticas**           | Código limpio, legible, con nombres claros, comentarios si es necesario.                      | Código en su mayoría legible, pero puede mejorar en claridad o consistencia.               | Código desordenado o repetitivo. Uso inadecuado de nombres o sin estructura.     | Código confuso, ilegible o sin estructura alguna.                         |

---

## 🎯 Ponderación sugerida (si querés cuantificar en 100 puntos)

| Criterio                           | Puntos |
| ---------------------------------- | ------ |
| Comprensión y análisis de errores  | 25     |
| Corrección de errores              | 20     |
| Implementación de funciones vacías | 15     |
| Razonamiento y justificación       | 15     |
| Uso responsable de IA              | 10     |
| Funcionamiento final del programa  | 10     |
| Estilo de código                   | 5      |

---

## ✍️ Consejos para la entrega

* **Incluí una hoja o sección de justificación**: donde expliquen qué errores encontraron y qué decisiones tomaron.
* **Permití que presenten oralmente parte de sus decisiones** si lo hacés presencial.
* **Usá versiones individuales del examen con errores distintos** si tenés tiempo (opcional pero poderoso).

-----
Perfecto, aquí tienes un análisis detallado de los errores presentes en el código que me pasaste, junto con las correcciones y explicaciones. Esto te puede servir para corregir el examen o para que los estudiantes reflexionen sobre los errores al usar IA como Copilot.

----------

# Análisis y solución comentada del código

```python
estudiantes = []

def dni_duplicado(dni):
    # ERROR: Esta función devuelve False si encuentra el DNI,
    #        pero debería devolver True porque sí está duplicado.
    #        Y devuelve True cuando NO lo encontró, lo cual es al revés.
    for e in estudiantes:
        if e[2] == dni:
            return False  # <-- ERROR: debe ser True aquí
    return True  # <-- ERROR: debe ser False aquí

# SOLUCIÓN CORRECTA:
def dni_duplicado(dni):
    for e in estudiantes:
        if e[2] == dni:
            return True
    return False


def buscar_por_dni(dni):
    # Se busca el índice del estudiante con el DNI dado.
    for i, e in enumerate(estudiantes):
        if e[2] == dni:
            return i
    return -1


def agregar_estudiante():
    nombre = input("Nombre: ")
    apellido = input("Apellido: ")
    dni = input("DNI: ")
    
    if not nombre or not apellido or not dni:
        print("Todos los campos son obligatorios.")
        return
    
    if not dni.isdigit():
        print("El DNI debe ser numérico.")
        return
    
    # ERROR: Se usa dni_duplicado que estaba mal antes
    #        ahora que la corregimos funciona bien
    if dni_duplicado(dni):
        print("DNI duplicado.")
        return
    
    estudiante = [nombre, apellido, dni, -1, "ausente"]
    estudiantes.append(estudiante)
    print("Estudiante agregado correctamente.")


def modificar_nota():
    dni = input("DNI del estudiante a modificar: ")
    indice = buscar_por_dni(dni)

    if indice == -1:
        print("Estudiante no encontrado.")
        return

    try:
        nota = int(input("Ingrese la nueva nota: "))
        if nota < 0 or nota > 10:
            print("Nota fuera de rango.")
            return
    except:
        print("Error: nota inválida.")
        return

    estudiantes[indice][3] = nota
    # ERROR: la asignación de condición está invertida
    # Si nota >= 6 => debe ser "aprobado"
    # Si nota < 6 y > 0 => "reprobado"
    # Nota 0 => "ausente"
    if nota == 0:
        estudiantes[indice][4] = "ausente"
    elif nota >= 6:
        estudiantes[indice][4] = "aprobado"  # CORRECTO
    else:
        estudiantes[indice][4] = "reprobado"  # CORRECTO


def eliminar_estudiante():
    dni = input("DNI del estudiante a eliminar: ")
    indice = buscar_por_dni(dni)

    if indice == -1:
        print("Estudiante no encontrado.")
        return

    # ERROR: Solo debería eliminar si NO tiene nota asignada (-1)
    #        El código actual verifica si la nota es diferente de 0, lo cual está mal
    if estudiantes[indice][3] != -1:
        print("No se puede eliminar un estudiante con nota asignada.")
        return

    del estudiantes[indice]
    print("Estudiante eliminado.")


def listar_estudiantes():
    if not estudiantes:
        print("No hay estudiantes registrados.")
        return

    for e in estudiantes:
        print(f"{e[0]} {e[1]} - DNI: {e[2]} - Nota: {e[3]} - Condición: {e[4]}")


def mostrar_estadisticas():
    aprobados = 0
    reprobados = 0
    ausentes = 0

    for e in estudiantes:
        # ERROR: Los contadores están intercambiados
        if e[4] == "aprobado":
            aprobados += 1
        elif e[4] == "reprobado":
            reprobados += 1
        else:
            ausentes += 1

    print(f"Aprobados: {aprobados}")
    print(f"Reprobados: {reprobados}")
    print(f"Ausentes: {ausentes}")


def menu():
    while True:
        print("\n--- Menú de opciones ---")
        print("1. Agregar estudiante")
        print("2. Modificar nota")
        print("3. Eliminar estudiante")
        print("4. Listar estudiantes")
        print("5. Mostrar estadísticas")
        print("6. Salir")

        opcion = input("Seleccione una opción: ")
        if opcion == "1":
            agregar_estudiante()
        elif opcion == "2":
            modificar_nota()
        elif opcion == "3":
            eliminar_estudiante()
        elif opcion == "4":
            listar_estudiantes()
        elif opcion == "5":
            mostrar_estadisticas()
        elif opcion == "6":
            print("¡Hasta luego!")
            break
        else:
            print("Opción inválida.")

if __name__ == "__main__":
    menu()

```

----------

# Resumen de problemas detectados y cómo explicarlos a los estudiantes

Función

Error detectado

Explicación para estudiantes

Corrección clave

`dni_duplicado`

Retorna `False` si encuentra DNI, debería ser `True`

La función debe indicar si el DNI ya existe para evitar duplicados

Cambiar `return False` por `return True` cuando DNI encontrado

`modificar_nota`

Asignación errónea de condición: invierte aprobado/reprobado

La lógica para definir condición debe seguir criterios claros: nota ≥ 6 = aprobado, <6 = reprobado

Corregir asignación en `if-elif-else`

`eliminar_estudiante`

Solo se debe eliminar si no tiene nota asignada, se validó mal (con 0 en lugar de -1)

La nota -1 indica sin asignar, eliminar permitido solo en ese caso

Cambiar chequeo de nota a `!= -1`

`mostrar_estadisticas`

Contadores de aprobados y reprobados intercambiados

Contar correctamente estudiantes según condición real

Ajustar suma de contadores

----------

# ¿Por qué es importante este tipo de ejercicio?

-   Permite evaluar la comprensión del estudiante para detectar errores lógicos, no solo sintaxis.
    
-   Favorece el pensamiento crítico al leer y analizar código que aparentemente "funciona".
    
-   En un contexto donde se permite el uso de IA, obliga a que el alumno valide y entienda lo generado por herramientas como Copilot.
    

----------

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwOTgyNDAzNzhdfQ==
-->