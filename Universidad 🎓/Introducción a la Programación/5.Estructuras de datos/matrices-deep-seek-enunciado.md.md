**ENUNCIADO DEL EJERCICIO: ANÁLISIS DE MATRICES CUADRADAS**  

**Nivel:** Principiante/Intermedio  
**Objetivo:** Practicar el manejo de matrices, entrada de datos, bucles y funciones en Python.  

---

### **📝 Descripción**  
Desarrolla un programa en Python que permita analizar matrices cuadradas (N x N) con las siguientes funcionalidades:  

1. **Ingreso de datos**:  
   - El usuario debe poder elegir entre:  
   - Ingresar manualmente los valores de la matriz.  
   - Generar una matriz con valores aleatorios (definiendo rango mínimo y máximo).  

2. **Operaciones requeridas**:  
   - Mostrar la matriz completa.  
   - Identificar y mostrar la **diagonal principal**.  
   - Identificar y mostrar la **diagonal secundaria**.  
   - Calcular y mostrar la **suma de ambas diagonales**.  

3. **Validaciones**:  
   - Asegurar que el tamaño de la matriz (N) sea un entero positivo.  
   - Validar que los valores ingresados (manuales o aleatorios) sean enteros.  

4. **Interacción continua**:  
   - Preguntar al usuario si desea analizar otra matriz antes de finalizar.  

---

### **🎯 Requisitos Técnicos**  
- Usar **funciones** para modularizar el código.  
- Implementar **manejo de errores** para entradas inválidas.  
- Utilizar **listas anidadas** para representar la matriz.  
- Generar números aleatorios con el módulo `random`.  

---

### **📌 Ejemplo de Entrada/Salida**  

**Entrada (Ejemplo manual):**  
```
Tamaño de matriz (N): 3  
Valores:  
[0][0]: 5  
[0][1]: 3  
[0][2]: 8  
[1][0]: 1  
[1][1]: 7  
[1][2]: 2  
[2][0]: 4  
[2][1]: 0  
[2][2]: 6  
```  

**Salida:**  
```
Matriz ingresada:  
[5, 3, 8]  
[1, 7, 2]  
[4, 0, 6]  

Diagonal principal: [5, 7, 6] (Suma = 18)  
Diagonal secundaria: [8, 7, 4] (Suma = 19)  
```  

**Entrada (Ejemplo aleatorio):**  
```
Tamaño de matriz (N): 2  
Rango mínimo: -10  
Rango máximo: 10  
```  

**Salida posible:**  
```
Matriz generada:  
[-3, 5]  
[8, 2]  

Diagonal principal: [-3, 2] (Suma = -1)  
Diagonal secundaria: [5, 8] (Suma = 13)  
```  

---

### **💡 Consejos**  
1. Usa `try-except` para manejar errores en entradas.  
2. Para las diagonales, recuerda que:  
   - **Principal**: `matriz[i][i]`.  
   - **Secundaria**: `matriz[i][n-1-i]`.  
3. Optimiza el código reutilizando funciones (ej: `mostrar_matriz()`).  

----

### **Interfaz** o **contrato**
**Interfaz** o **contrato** que se debe respetar. Esto incluye las funciones que se deben implementar, sus nombres, parámetros y lo que deben devolver. 

>Este contrato servirá como base para la evaluación de examen más adelante.

### Contrato para el programa de matrices cuadradas:

#### 1. **`ingresar_matriz_manual(n)`**
   - **Descripción**: Permite al usuario ingresar manualmente los elementos de una matriz cuadrada de tamaño `n x n`.
   - **Parámetros**:
     - `n` (int): Tamaño de la matriz (número de filas y columnas).
   - **Retorno**:
     - Una lista de listas que representa la matriz cuadrada ingresada.

#### 2. **`diagonal_principal(matriz)`**
   - **Descripción**: Calcula y devuelve los elementos de la diagonal principal de la matriz.
   - **Parámetros**:
     - `matriz` (list[list[int]]): Matriz cuadrada.
   - **Retorno**:
     - Una lista con los elementos de la diagonal principal.

#### 3. **`diagonal_secundaria(matriz)`**
   - **Descripción**: Calcula y devuelve los elementos de la diagonal secundaria de la matriz.
   - **Parámetros**:
     - `matriz` (list[list[int]]): Matriz cuadrada.
   - **Retorno**:
     - Una lista con los elementos de la diagonal secundaria.

#### 4. **`suma_diagonales(matriz)`**
   - **Descripción**: Calcula la suma de los elementos de las diagonales principal y secundaria.
   - **Parámetros**:
     - `matriz` (list[list[int]]): Matriz cuadrada.
   - **Retorno**:
     - Una tupla `(suma_principal, suma_secundaria)`:
       - `suma_principal` (int): Suma de los elementos de la diagonal principal.
       - `suma_secundaria` (int): Suma de los elementos de la diagonal secundaria.

#### 5. **`mostrar_matriz(matriz)`**
   - **Descripción**: Muestra la matriz en formato legible.
   - **Parámetros**:
     - `matriz` (list[list[int]]): Matriz cuadrada.
   - **Retorno**:
     - Ninguno (solo imprime la matriz).

#### 6. **`analizar_matriz()`**
   - **Descripción**: Función principal que coordina la ejecución del programa.
   - **Parámetros**:
     - Ninguno.
   - **Retorno**:
     - Ninguno (solo imprime resultados).

---

### Ejemplo de contrato en formato de código:

```python
def ingresar_matriz_manual(n):
    """
    Permite al usuario ingresar manualmente los elementos de una matriz cuadrada de tamaño n x n.
    :param n: Tamaño de la matriz (número de filas y columnas).
    :return: Una lista de listas que representa la matriz cuadrada ingresada.
    """
    pass

def diagonal_principal(matriz):
    """
    Calcula y devuelve los elementos de la diagonal principal de la matriz.
    :param matriz: Matriz cuadrada.
    :return: Una lista con los elementos de la diagonal principal.
    """
    pass

def diagonal_secundaria(matriz):
    """
    Calcula y devuelve los elementos de la diagonal secundaria de la matriz.
    :param matriz: Matriz cuadrada.
    :return: Una lista con los elementos de la diagonal secundaria.
    """
    pass

def suma_diagonales(matriz):
    """
    Calcula la suma de los elementos de las diagonales principal y secundaria.
    :param matriz: Matriz cuadrada.
    :return: Una tupla (suma_principal, suma_secundaria).
    """
    pass

def mostrar_matriz(matriz):
    """
    Muestra la matriz en formato legible.
    :param matriz: Matriz cuadrada.
    :return: None
    """
    pass

def analizar_matriz():
    """
    Función principal que coordina la ejecución del programa.
    :return: None
    """
    pass
```

---

### Reglas que usted debe respetar:
1. **Nombres de funciones**:
   - Los nombres de las funciones deben coincidir exactamente con los especificados en el contrato.
2. **Parámetros y retornos**:
   - Los parámetros y los valores de retorno deben respetar los tipos y estructuras indicados.
3. **Comportamiento esperado**:
   - Cada función debe cumplir con la descripción de su propósito.




<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg5OTQ3NjQ3NV19
-->