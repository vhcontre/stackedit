### **Workflow en Scrum para el Proyecto: "Análisis de Matrices Cuadradas"**  
*(Usando Jira como herramienta de gestión)*  

---

## **1. Definición del Product Backlog (Épicas e Historias de Usuario)**  
### **Épica 1: Ingreso de Datos**  
- **Historia 1 (US-01)**: Como usuario, quiero ingresar manualmente los valores de una matriz cuadrada para analizarla.  
  - **Criterios de Aceptación**:  
    - Validar que el tamaño `N` sea un entero positivo.  
    - Asegurar que los valores ingresados sean enteros.  

- **Historia 2 (US-02)**: Como usuario, quiero generar una matriz con valores aleatorios (definiendo rango mínimo/máximo) para agilizar el proceso.  
  - **Criterios**:  
    - Usar el módulo `random` de Python.  
    - Validar que los rangos sean enteros.  

### **Épica 2: Operaciones sobre Matrices**  
- **Historia 3 (US-03)**: Como usuario, quiero visualizar la matriz completa en formato legible.  
- **Historia 4 (US-04)**: Como usuario, quiero identificar y mostrar la diagonal principal y secundaria.  
- **Historia 5 (US-05)**: Como usuario, quiero calcular la suma de ambas diagonales.  

### **Épica 3: Validaciones y Robustez**  
- **Historia 6 (US-06)**: Como usuario, quiero recibir mensajes claros si ingreso datos inválidos.  
  - **Criterios**:  
    - Manejar errores con `try-except`.  

### **Épica 4: Interacción Continua**  
- **Historia 7 (US-07)**: Como usuario, quiero elegir si analizar otra matriz o salir del programa.  

---

## **2. Sprint Planning (Ejemplo para 1 Sprint de 2 Semanas)**  
### **Objetivo del Sprint**:  
*"Implementar el ingreso manual/aleatorio de matrices y mostrar diagonales con sus sumas"*  

### **Tareas Técnicas (Breakdown de US-01 a US-05)**  
1. **Tarea 1 (T-01)**: Crear función para validar tamaño `N` de la matriz.  
2. **Tarea 2 (T-02)**: Implementar input manual de valores (lista anidada).  
3. **Tarea 3 (T-03)**: Programar generación aleatoria de matrices con `random.randint()`.  
4. **Tarea 4 (T-04)**: Función para imprimir matriz formateada.  
5. **Tarea 5 (T-05)**: Lógica para extraer diagonales principal/secundaria.  
6. **Tarea 6 (T-06)**: Calcular suma de diagonales.  

---

## **3. Tablero Scrum en Jira**  
| **Tipo**  | **ID** | **Título**                          | **Estado**    | **Asignado** | **Sprint** |  
|-----------|--------|-------------------------------------|---------------|--------------|------------|  
| Épica     | EP-01  | Ingreso de Datos                    | To Do         | -            | Sprint 1   |  
| Historia  | US-01  | Input manual de matriz              | In Progress   | Dev A        | Sprint 1   |  
| Tarea     | T-01   | Validar tamaño N                    | Done          | Dev A        | Sprint 1   |  
| Tarea     | T-02   | Leer valores y guardar en lista     | To Do         | Dev B        | Sprint 1   |  

---

## **4. Ceremonias Scrum**  
- **Daily Standup**:  
  > *"Ayer: Terminé T-01 (validación de N). Hoy: Trabajaré en T-02. Bloqueos: Ninguno."*  

- **Sprint Review**:  
  - Demo: Mostrar matriz generada aleatoriamente + cálculo de diagonales.  

- **Retrospectiva**:  
  > *"¿Qué salió bien? Modularización en funciones. ¿Qué mejorar? Mejorar mensajes de error."*  

---

## **5. Estructura de Código (Ejemplo Modular)**  
```python  
# Módulo 1: Validaciones  
def validar_entero(mensaje):  
    while True:  
        try:  
            return int(input(mensaje))  
        except ValueError:  
            print("¡Error! Ingresa un número entero.")  

# Módulo 2: Operaciones  
def suma_diagonales(matriz):  
    suma_principal = sum(matriz[i][i] for i in range(len(matriz)))  
    suma_secundaria = sum(matriz[i][-i-1] for i in range(len(matriz)))  
    return suma_principal, suma_secundaria  
```  

---

### **6. Definición de "Done"**  
- Código implementado y probado.  
- Cumple criterios de aceptación.  
- Documentado (comentarios + README).  

--- 

¿Quieres que profundice en algún área (ej: estimación con *Story Points*, configurar Jira paso a paso)? 😊
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQwNzU3MTI3OF19
-->