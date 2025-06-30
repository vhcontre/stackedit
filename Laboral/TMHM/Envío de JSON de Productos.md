# Guía para la Generación y Envío de JSON de Productos (Carga Masiva)

### Descripción

Este módulo permite actualizar o insertar productos en la base de datos de forma masiva, procesando los datos en lotes para optimizar el rendimiento. El operador debe generar un archivo JSON con la estructura adecuada y enviarlo al sistema.

---

### Estructura del JSON Esperado

El archivo JSON debe ser un arreglo de objetos, donde cada objeto representa un producto a actualizar o insertar.

#### Ejemplo de estructura
```json
[
	{
	    "PartNumber": "ROD-30306",
	    "Price": 120.50,
	    "Stock": 3,
	    "IsDeleted": false,
	    "Name": "ROD-30306-RODAMIENTO",
	    "Description": "Actualización de producto existente"	   
	  },
	  {
	    "PartNumber": "676101542071",
	    "Price": 89.99,
	    "Stock": 2,
	    "IsDeleted": false,
	    "Name": "676101542071-VALVULA",
	    "Description": "Actualización de producto existente"
	  }
]
```


---

## Campos requeridos por producto

| Campo         | Tipo     | Descripción                                 | Ejemplo           |
|---------------|----------|---------------------------------------------|-------------------|
| PartNumber    | string   | Identificador único del producto            | "ABC123"          |
| Price         | decimal  | Precio del producto                         | 100.50            |
| Stock         | int      | Cantidad en inventario                      | 20                |
| IsDeleted     | bool     | Indica si el producto está eliminado        | false             |
| Name          | string   | Nombre del producto                         | "Producto X"      |
| Description   | string   | Descripción del producto                    | "Descripción..."  |
| CategoryId    | int      | Valor contaste                          | 1                 |
| Image         | string   | Valor contaste                   | "none.jpg"      |
| Discount      | decimal  | Valor contaste                          | 0.0               |

---

## Consideraciones Técnicas

- **Todos los campos son obligatorios** y deben tener el tipo de dato correcto.
- El campo `PartNumber` es clave: si ya existe, el producto se actualiza; si no, se inserta como nuevo.
- El JSON debe ser un arreglo (array) de productos.
- Se recomienda validar el JSON antes de enviarlo para evitar errores de formato o datos faltantes.



## Información

- Para grandes volúmenes (miles de productos):  si se recibe una lista de, por ejemplo, 100,000 productos en una sola llamada, el método los procesa internamente en lotes de 10,000 (o el tamaño que se defina en el parámetro batchSize).
- Mantener consistencia en los tipos de datos (por ejemplo, no usar comillas en valores numéricos).
- Revisar que no haya duplicados en el campo `PartNumber` dentro del mismo lote.


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAzNjEwMjgwMSwtMTYwNjY0NzU3Ml19
-->