## 🧾 Trabajo Práctico - Inventario y Ventas


### 🧠 Tema: Listas de listas (matrices), validaciones, funciones, lógica

----------

### 🎯 **Objetivo general**

Desarrollar un sistema de consola que permita gestionar un inventario de productos con soporte para registrar ventas y generar estadísticas.  
Todos los datos se almacenan en **una única matriz (lista de listas)**, y cada producto tendrá su información de ventas acumulada.

----------

## 🧱 Estructura de cada producto (una lista dentro de la matriz):

```python
[código, nombre, stock, precio, estado, cantidad_vendida]

```

### Descripción de los campos:

1.  **Código** (`str`): identificador único del producto    
2.  **Nombre** (`str`): nombre del producto    
3.  **Stock** (`int`): cantidad en inventario (≥ 0)    
4.  **Precio** (`float`): precio unitario (> 0)    
5.  **Estado** (`str`): se calcula automáticamente según el stock:
    
    -   `"sin stock"` si stock = 0        
    -   `"stock bajo"` si 1 ≤ stock < 10        
    -   `"stock suficiente"` si stock ≥ 10
        
6.  **Cantidad vendida** (`int`): se inicializa en 0 y se incrementa con cada venta
    

----------

## 🛠️ Funcionalidades que deben implementarse

### 1. `agregar_producto()`

-   Permite registrar un nuevo producto.
    
-   Valida:
    
    -   Que el código no exista previamente.        
    -   Que el stock sea entero ≥ 0.        
    -   Que el precio sea un número > 0.        
-   Inicializa `cantidad_vendida` en 0.
    
-   Calcula automáticamente el estado según el stock.
    

----------

### 2. `modificar_stock()`

-   Permite actualizar el stock de un producto dado su código.    
-   Recalcula automáticamente el estado.
    

----------

### 3. `eliminar_producto()`

-   Permite eliminar un producto solo si su stock es 0 y no ha sido vendido (`cantidad_vendida` == 0).
    

----------

### 4. `listar_productos()`

-   Muestra todos los productos registrados con todos sus datos.
    

----------

### 5. `registrar_venta()`

-   Permite registrar la venta de un producto.
    
-   Solicita:
    
    -   Código del producto        
    -   Cantidad a vender
        
-   Valida:    
    -   Que el producto exista.        
    -   Que haya stock suficiente.
        
-   Resta la cantidad al stock.
    
-   Suma esa cantidad al campo `cantidad_vendida`.    
-   Actualiza el estado del producto.
    

----------

### 6. `estadisticas_inventario()`

-   Muestra:
    
    -   Total de productos registrados        
    -   Cantidad de productos "sin stock"        
    -   Cantidad de productos con "stock bajo"        
    -   Cantidad de productos con "stock suficiente"
        

----------

### 7. `estadisticas_ventas()`

-   Muestra:
    
    -   Total de unidades vendidas (suma de todos los `cantidad_vendida`)        
    -   Producto más vendido (por cantidad)        
    -   Producto menos vendido (por cantidad > 0)
        

----------

## 📌 Requisitos técnicos

-   Usar **una única matriz** para almacenar todos los productos.    
-   Modularizar el código con funciones.    
-   Validar entradas: el usuario no debe poder continuar hasta ingresar datos correctos.    
-   Implementar un **menú principal** que se repita hasta que el usuario decida salir.
    

----------

## 🧠 Sugerencias 

Se recomienda a los estudiantes:

-   Analizar bien la estructura de la lista antes de comenzar.    
-   Trabajar paso a paso, probando cada función.    
-   Usar funciones auxiliares como `buscar_por_codigo()` para facilitar búsquedas en la matriz.
    

    


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY0MjM2MjE0MV19
-->