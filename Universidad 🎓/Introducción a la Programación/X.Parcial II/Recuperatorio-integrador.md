**Enunciado para Examen de Programación en Python**  

**Título:** *"El Problema del Ajedrez y los Granos de Arroz"*  

**Contexto:**  
Según una antigua leyenda, un rey ofreció a un sabio recompensarlo con arroz. El sabio pidió:  
*"1 grano en la primera casilla del tablero de ajedrez, 2 en la segunda, 4 en la tercera, y así sucesivamente (duplicando la cantidad en cada casilla)"*.  

**Consigna:**  
Implementa en Python la función `proyeccion_geometrica()` que:  
1. Genere una matriz 8x8 representando el tablero de ajedrez.  
2. Cada casilla debe contener el valor correspondiente a la secuencia geométrica (1, 2, 4, 8, ..., 2⁶³).  
3. **Formateo de salida**:  
   - Los números deben imprimirse alineados, con separador de miles (puntos).  
   - Las casillas pares e impares deben mostrar colores distintos (azul/verde).  
4. **Requisitos técnicos**:  
   - Usa `os.system` para limpiar la pantalla al inicio.  
   - Calcula dinámicamente el ancho de columna basado en el número más grande.  

**Ejemplo de salida:**  
```
Proyección geométrica del tablero de ajedrez

   1       2       4       8      16      32      64     128  
 256     512   1.024   2.048   4.096   8.192  16.384  32.768  
65.536 131.072 262.144 524.288 1.048.576 ... 
```  

**Puntos evaluables:**  
- Correcta implementación de la lógica geométrica (20%).  
- Formateo alineado con separadores de miles (30%).  
- Uso de colores alternados (20%).  
- Limpieza de pantalla y estructura de código (10%).  
- Documentación y comentarios (20%).  

**Bonus:**  
- Modifica la función para recibir el tamaño del tablero (NxN) como parámetro.  

---  
**Nota para el profesor:**  
Este examen evalúa:  
- Manipulación de matrices.  
- Formateo de strings.  
- Secuencias matemáticas.  
- Buenas prácticas (legibilidad, documentación).  

-----

**¡Sí, totalmente!** Aquí tienes una versión descompuesta en funciones puras y reutilizables, siguiendo buenas prácticas de Python:

```python
import os
from typing import List

def generar_matriz_geometrica(filas: int = 8, columnas: int = 8) -> List[List[int]]:
    """Genera matriz geométrica empezando en 1 y duplicando valores"""
    matriz = []
    valor = 1
    for _ in range(filas):
        fila = []
        for _ in range(columnas):
            fila.append(valor)
            valor *= 2
        matriz.append(fila)
    return matriz

def formatear_numero(num: int) -> str:
    """Formatea número con separador de miles y alineación"""
    return f"{num:,}".replace(",", ".")

def calcular_ancho_columnas(matriz: List[List[int]]) -> int:
    """Calcula el ancho necesario para la columna más grande"""
    max_num = matriz[-1][-1]
    return len(formatear_numero(max_num))

def imprimir_matriz(matriz: List[List[int]], colores: List[str] = ["\033[94m", "\033[92m"]):
    """Imprime matriz con colores alternados y formato alineado"""
    ancho = calcular_ancho_columnas(matriz)
    reset = "\033[0m"
    
    for fila in matriz:
        linea = []
        for idx, num in enumerate(fila):
            color = colores[idx % 2]
            texto = formatear_numero(num).rjust(ancho)
            linea.append(f"{color}{texto}{reset}")
        print(" ".join(linea))

def proyeccion_geometrica():
    """Función principal que coordina el proceso completo"""
    os.system('cls' if os.name == 'nt' else 'clear')
    print("\nProyección geométrica del tablero de ajedrez\n")
    
    matriz = generar_matriz_geometrica()
    imprimir_matriz(matriz)
    
    print("\nFin de la proyección geométrica.\n")

# Ejecución
if __name__ == "__main__":
    proyeccion_geometrica()
```

### Ventajas de esta descomposición:

1. **Funciones especializadas**:
   - Cada función hace una sola cosa (principio SRP)
   - Nombres descriptivos que documentan el comportamiento

2. **Mayor testabilidad**:
   ```python
   def test_generar_matriz():
       assert generar_matriz_geometrica(2, 2) == [[1, 2], [4, 8]]
   ```

3. **Reutilización**:
   - `formatear_numero()` y `calcular_ancho_columnas()` pueden usarse en otros proyectos

4. **Flexibilidad**:
   - Fácil modificar colores o tamaño del tablero
   - Ejemplo con tablero 5x5:
   ```python
   imprimir_matriz(generar_matriz_geometrica(5, 5))
   ```

5. **Mantenimiento**:
   - Cambiar el formateo solo requiere modificar `formatear_numero()`
   - Los colores se centralizan en `imprimir_matriz()`

¿Quieres que agregue más funcionalidades como:
- Validación de parámetros?
- Manejo de errores?
- Versión con generadores?
<!--stackedit_data:
eyJoaXN0b3J5IjpbODIyMTgxNjM1XX0=
-->