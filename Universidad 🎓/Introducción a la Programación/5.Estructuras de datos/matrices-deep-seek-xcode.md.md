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

---

### **📚 Evaluación**  
- **Funcionalidad (60%)**: Cumple con todas las operaciones requeridas.  
- **Legibilidad (20%)**: Código bien estructurado y comentado.  
- **Robustez (20%)**: Manejo correcto de errores y edge cases.  

## **Código **
```python
import random

def ingresar_matriz_manual(n):
    matriz = []
    print(f"\nIngrese los elementos de la matriz {n}x{n} (fila por fila):")
    for i in range(n):
        fila = []
        for j in range(n):
            while True:
                try:
                    num = int(input(f"Posición [{i}][{j}]: "))
                    fila.append(num)
                    break
                except ValueError:
                    print("Error: Ingrese un número entero válido.")
        matriz.append(fila)
    return matriz

def generar_matriz_aleatoria(n):
    while True:
        try:
            rango_min = int(input("Ingrese el valor mínimo para los números aleatorios: "))
            rango_max = int(input("Ingrese el valor máximo para los números aleatorios: "))
            if rango_min > rango_max:
                print("Error: El valor mínimo debe ser menor o igual al máximo.")
                continue
            break
        except ValueError:
            print("Error: Ingrese números enteros válidos.")
    
    matriz = []
    for i in range(n):          # Para cada fila (i de 0 a n-1)
        fila = []
        for j in range(n):      # Para cada columna (j de 0 a n-1)
            num = random.randint(rango_min, rango_max)
            fila.append(num)
        matriz.append(fila)
    return matriz
    # return [[random.randint(rango_min, rango_max) for _ in range(n)] for _ in range(n)]

def mostrar_matriz(matriz):
    print("\nMatriz ingresada:")
    for fila in matriz:
        print(fila)

def diagonal_principal(matriz):
    return [matriz[i][i] for i in range(len(matriz))]

def diagonal_secundaria(matriz):
    n = len(matriz)
    return [matriz[i][n - 1 - i] for i in range(n)]

def suma_diagonales(matriz):
    suma_principal = sum(diagonal_principal(matriz))
    suma_secundaria = sum(diagonal_secundaria(matriz))
    return suma_principal, suma_secundaria

def main():
    while True:
        print("\n--- Análisis de Matriz Cuadrada ---")
        print("1. Ingresar matriz manualmente")
        print("2. Generar matriz aleatoria")
        opcion = input("Seleccione una opción (1/2): ")

        if opcion not in ['1', '2']:
            print("Opción no válida. Intente de nuevo.")
            continue

        while True:
            try:
                n = int(input("\nIngrese el tamaño de la matriz cuadrada (N): "))
                if n <= 0:
                    print("Error: Ingrese un número mayor que 0.")
                    continue
                break
            except ValueError:
                print("Error: Debe ingresar un número entero válido.")

        if opcion == '1':
            matriz = ingresar_matriz_manual(n)
        else:
            matriz = generar_matriz_aleatoria(n)
            print("\nMatriz generada aleatoriamente:")
            mostrar_matriz(matriz)

        dp = diagonal_principal(matriz)
        ds = diagonal_secundaria(matriz)
        suma_p, suma_s = suma_diagonales(matriz)

        print("\nDiagonal principal:", dp, f"(Suma = {suma_p})")
        print("Diagonal secundaria:", ds, f"(Suma = {suma_s})")

        repetir = input("\n¿Desea analizar otra matriz? (s/n): ").lower()
        if repetir != 's':
            print("\n¡Programa terminado!")
            break

if __name__ == "__main__":
    main()

```


## 📌 **Comprensión de listas anidadas**


### **🧩 Explicación Detallada de: **
```python
[[random.randint(rango_min, rango_max) for _ in range(n)] for _ in range(n)]
```

#### **1. Parte Interna: `random.randint(rango_min, rango_max) for _ in range(n)`**
- **`random.randint(a, b)`**:  
  Genera un número entero aleatorio entre `a` (incluido) y `b` (incluido).  
  Ejemplo: Si `rango_min = 1` y `rango_max = 10`, podría generar `7`.

- **`for _ in range(n)`**:  
  - El bucle se ejecuta `n` veces (para crear `n` columnas en una fila).  
  - El guion bajo `_` es una convención para indicar que la variable de iteración no se usa dentro del bucle.  

- **Resultado**:  
  Crea una **fila** de la matriz con `n` números aleatorios.  
  Ejemplo para `n=3`: `[5, 2, 9]`.

#### **2. Parte Externa: `[ ... for _ in range(n)]`**
- Repite el proceso anterior `n` veces (para crear `n` filas).  
- **Resultado final**:  
  Una **lista de listas** (matriz `n x n`).  
  Ejemplo para `n=2`: `[[3, 7], [1, 4]]`.

---

### **⚡ Equivalente con Bucles Tradicionales**
```python
matriz = []
for i in range(n):          # Para cada fila (i de 0 a n-1)
    fila = []
    for j in range(n):      # Para cada columna (j de 0 a n-1)
        num = random.randint(rango_min, rango_max)
        fila.append(num)
    matriz.append(fila)
return matriz
```

---

### **📌 Ejemplo Práctico**
Si el usuario ingresa:
- `n = 2`
- `rango_min = 10`
- `rango_max = 20`

**Posible matriz generada:**  
```python
[[15, 12],  # Fila 0
 [18, 11]]  # Fila 1
```

---

### **💡 ¿Por qué usar comprensión de listas?**
- **Menos código**: Más compacto y legible (una vez que se entiende la sintaxis).  
- **Eficiencia**: En Python, suele ser más rápido que bucles tradicionales.  

<br />


## **📌 Función `diagonal_principal(matriz)`**
```python
def diagonal_principal(matriz):
    return [matriz[i][i] for i in range(len(matriz))]
```

#### **¿Qué hace?**
- **Extrae los elementos de la diagonal principal** de una matriz cuadrada (donde el índice de fila y columna son iguales: `[0][0]`, `[1][1]`, `[2][2]`, etc.).  
- **Devuelve una lista** con estos elementos.

---

### **🧩 Explicación Detallada**

#### **1. `len(matriz)`**
- **Propósito**: Obtiene el tamaño `n` de la matriz (número de filas, que es igual al número de columnas porque es cuadrada).  
- **Ejemplo**:  
  Si `matriz = [[5, 3, 8], [1, 7, 2], [4, 0, 6]]`, entonces `len(matriz)` es `3`.

#### **2. `range(len(matriz))`**
- **Propósito**: Genera una secuencia de índices desde `0` hasta `n-1` (para recorrer filas y columnas).  
- **Ejemplo**:  
  Para `n=3`, `range(3)` produce `0, 1, 2`.

#### **3. `matriz[i][i]`**
- **Propósito**: Accede al elemento donde la **fila** y la **columna** tienen el mismo índice (`i`).  
  - **Fila `i`**: Primera dimensión de la lista anidada.  
  - **Columna `i`**: Segunda dimensión.  
- **Ejemplo**:  
  - Si `i=0`: `matriz[0][0] = 5` (esquina superior izquierda).  
  - Si `i=1`: `matriz[1][1] = 7` (centro).  
  - Si `i=2`: `matriz[2][2] = 6` (esquina inferior derecha).

#### **4. Comprensión de lista `[matriz[i][i] for i in range(len(matriz))]`**
- **Propósito**: Crea una lista iterando sobre cada índice `i` y agregando `matriz[i][i]`.  
- **Equivalente con bucle `for`**:
  ```python
  diagonal = []
  for i in range(len(matriz)):
      diagonal.append(matriz[i][i])
  return diagonal
  ```
- **Resultado**:  
  Para la matriz `[[5, 3, 8], [1, 7, 2], [4, 0, 6]]`, devuelve `[5, 7, 6]`.

---

### **📋 Ejemplo Visual**
**Matriz de 3x3:**
```
Fila 0: [5, 3, 8]    # matriz[0]
Fila 1: [1, 7, 2]    # matriz[1]
Fila 2: [4, 0, 6]    # matriz[2]
```
**Diagonal principal**:  
- `matriz[0][0] = 5`  
- `matriz[1][1] = 7`  
- `matriz[2][2] = 6`  
→ **Output**: `[5, 7, 6]`.

---

### **⚡ ¿Por qué funciona así?**
- En matrices cuadradas, la diagonal principal siempre tiene índices iguales (`[i][i]`).  
- La comprensión de lista es una forma **concisa y eficiente** de generar esta lista sin escribir bucles explícitos.

---

### **💡 Preguntas frecuentes**
1. **¿Qué pasa si la matriz no es cuadrada?**  
   - Esta función asume que la matriz es cuadrada. Si no lo es, podría generar un error (ej: si hay más filas que columnas, `matriz[i][i]` fallaría cuando `i` excede el tamaño de las columnas).  

2. **¿Cómo se usa en el programa principal?**  
   - Se llama así:
     ```python
     dp = diagonal_principal(matriz)
     print("Diagonal principal:", dp)
     ```


<br />

## **📌 Función `diagonal_secundaria(matriz)`**
```python
def diagonal_secundaria(matriz):
    n = len(matriz)  # Tamaño de la matriz (n x n)
    return [matriz[i][n - 1 - i] for i in range(n)]
```

#### **¿Qué hace?**
- **Extrae los elementos de la diagonal secundaria** de una matriz cuadrada (de la esquina superior derecha a la inferior izquierda).  
- **Devuelve una lista** con estos elementos.

---

### **🧩 Explicación Paso a Paso**

#### **1. `n = len(matriz)`**
- **Propósito**: Obtiene el tamaño `n` de la matriz (número de filas = número de columnas, porque es cuadrada).  
- **Ejemplo**:  
  Si la matriz es:  
  ```python
  [
    [5, 3, 8],
    [1, 7, 2],
    [4, 0, 6]
  ]
  ```
  Entonces `n = 3`.

#### **2. `range(n)`**
- Genera índices desde `0` hasta `n-1` (para recorrer todas las filas/columnas).  
- **Ejemplo**: Para `n=3`, `range(3)` produce `0, 1, 2`.

#### **3. `matriz[i][n - 1 - i]`**
- **Lógica clave**:  
  - **`i`**: Índice de la fila actual (desde `0` hasta `n-1`).  
  - **`n - 1 - i`**: Índice de la columna en la diagonal secundaria.  
    - Cuando `i=0` → `n-1 - 0 = 2` (última columna).  
    - Cuando `i=1` → `n-1 - 1 = 1` (columna central).  
    - Cuando `i=2` → `n-1 - 2 = 0` (primera columna).  
- **Acceso al elemento**: `matriz[fila][columna]`.  

#### **4. Ejemplo con Matriz 3x3**
Para la matriz:  
```python
[
  [5, 3, 8],  # Fila 0
  [1, 7, 2],  # Fila 1
  [4, 0, 6]   # Fila 2
]
```
- **Paso a paso**:  
  1. **`i=0`**: `matriz[0][3-1-0] = matriz[0][2] = 8` (esquina superior derecha).  
  2. **`i=1`**: `matriz[1][3-1-1] = matriz[1][1] = 7` (centro).  
  3. **`i=2`**: `matriz[2][3-1-2] = matriz[2][0] = 4` (esquina inferior izquierda).  
- **Resultado**: `[8, 7, 4]`.

---

### **📋 Diagrama Visual**
```
Diagonal Secundaria (de derecha a izquierda):

      0   1   2  → Columnas
    -----------
0 | 5   3   8 | 
1 | 1   7   2 |   → Elementos: 8 (0,2), 7 (1,1), 4 (2,0)
2 | 4   0   6 |
```

---

### **⚡ Equivalente con Bucle Tradicional**
```python
diagonal = []
n = len(matriz)
for i in range(n):
    elemento = matriz[i][n - 1 - i]  # Fórmula mágica
    diagonal.append(elemento)
return diagonal
```

---

### **💡 Preguntas Frecuentes**
1. **¿Por qué `n - 1 - i`?**  
   - `n - 1` es el último índice válido (ej: en una matriz 3x3, es `2`).  
   - Al restar `i`, invertimos el orden de las columnas:  
     - `i=0` → última columna, `i=1` → penúltima, etc.  

2. **¿Funciona para cualquier matriz cuadrada?**  
   - **Sí**, siempre que sea cuadrada (mismo número de filas y columnas).  

3. **¿Qué pasa si la matriz no es cuadrada?**  
   - **Error**: Si la matriz no es cuadrada, `n - 1 - i` podría apuntar a una columna inexistente.  

---

### **🔍 Ejemplo Adicional (Matriz 2x2)**
```python
matriz = [
    [10, 20],
    [30, 40]
]
```
- **Diagonal secundaria**: `[20, 30]` (porque `matriz[0][1] = 20` y `matriz[1][0] = 30`).  

---

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMzQyOTY0ODVdfQ==
-->