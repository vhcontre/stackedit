#  **Documento Técnico: Ejemplo de para crear subtareas**

### **Subtareas en Jira**  
Este documento técnico ejemplifica cómo descomponer una historia de usuario (*User Story*) en **subtareas técnicas específicas en Jira**.  

[➕ Añadir]  -> **Subtareas**

1. **Dividir el alcance** en componentes accionables:  
   - Cada subtarea (_ej: REP-4513, REP-4514_) debe abordar un bloque lógico (BD, backend, frontend).  

2. **Documentación integrada (**Descripción Funcional**)**:  
   - Cada subtarea debe incluir:  
     - **Descripción técnica**
     - **Criterios de aceptación**. 
  
  >Nota: Las líneas de los criterios de aceptación que puedan necesitar ajustes se marcarán con fondo **lila** para diferenciarlas.

---
  
 ## 📌**Ejemplo**
  
## *[TRANSACCIONES] 38.3 NOTA DE TRASLADO | VER DETALLE*

Jira: https://evoltis.atlassian.net/browse/REP-4125

>Desarrollar nueva funcionalidad que muestre información detallada del Proveedor y Productos relacionados cuando una Nota de Traslado está asociada a un Reclamo (*InventoryClaim*).  



## **Subtareas Técnicas**  

### 📝 **REP-4513 .BASE DE DATOS: Armar set de datos**  
**Descripción**  
- Generar dataset de prueba en tablas:  
  - `delivery_notes` (con registros vinculados a `inventory_claims`).  
  - `inventory_claims` (con estados válidos en `inventory_claims_states`).  
  - Relacionar con `suppliers`, `people`, y `products`.  
**Nota**: Incluir casos borde (ej: dirección NULL, múltiples unidades de medida).  

---

### 📝 **REP-4514. BACKEND Ajuste GET: spareparts/DeliveryNote/{id}**  
**Descripción**  
- DeliveryNoteMappingService . Modificar el mapeo de Reciever:
  ```csharp
  // Ejemplo en DeliveryNoteMappingService
  if (deliveryNote.InventoryClaimId != null) 
  {
      receiver.Name = inventoryClaim.Supplier.Person.FullName;
      receiver.Address = FormatAddress(inventoryClaim.Supplier.Person.Address);
  }
  ```  

- DeliveryNoteDetailMappingService . Modificar el mapeo de WarehouseAddress
- Agregar a DeliveryNoteDetailViewModel la propiedad InventoryClaimId nulleable

---

### 📝 **REP-4516. FRONTEND: Ajuste delivery-note-detail.component**  
**Descripción**  
- Lógica condicional para sección "Detalle de Productos":  
  ```typescript
  if (deliveryNote.inventoryClaimId) {
    this.loadInventoryClaimDetails(deliveryNote.inventoryClaimId);
  }
  ```  
**Requisitos**:  
- Ocultar sección si `InventoryClaimId` es NULL.  
- Mostrar datos de producto (código, lote, cantidad + símbolo UM).  

---

### 📝 **REP-4517. BACKEND Agregar GET: spareparts/InventoryClaim/{id}**  
**Descripción**  
- Nuevo endpoint para obtener detalles de reclamos:  
  - **Response**:  
    ```json
    {
      "productCode": "PR-001",
      "productName": "Producto X",
      "lotCode": "LOT-2024",
      "quantity": "5 kg",
      "supplierDetails": { ... }
    }
    ```  
---

### 📝 **REP-4518. FRONTEND: Agregar estado inventory-claims-detail**  
**Descripción**  
- Modificar componente para mostrar:  
  - Tabla con datos detalles del producto (código, descripción, lote).  
  - Sección de proveedor (nombre + dirección formateada).  
  - **Estados**:  
    - `loading` (carga de datos).  
    - `error` (manejo de reclamos no encontrados).  

---
**Imagen**  
[Subtarea en Jira](https://tecnovoznoroeste-my.sharepoint.com/:i:/r/personal/vcontreras_evoltis_com/Documents/Archivos%20de%20chat%20de%20Microsoft%20Teams/subtareas-ejemplos.png?csf=1&web=1&e=5bWjni)
---

### 🔢 **4. Asignación de puntos**  
- **Criterios**:  
  - Ver [Excel] Comprometido vs Quemado 
  - **Story Points**: 3 pts.  

---

### 🧪 **5. Pruebas**  
**Casos a validar**:  
- [ ] `DeliveryNote` sin `InventoryClaimId` → Secciones ocultas.  
- [ ] Unidades de medida: Múltiplo vs. Unidad base.  
- [ ] Dirección NULL → Mostrar "No especificado".  




<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3NTkwNjQyNjddfQ==
-->