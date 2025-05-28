https://evoltis.atlassian.net/browse/REP-4125

estructurar el documento técnico basado en la información que me compartes. Aquí tienes una propuesta inicial con las subtareas técnicas necesarias para implementar esta funcionalidad en Jira:

---

# 📌**Documento Técnico: [TRANSACCIONES] 38.3 NOTA DE TRASLADO | VER DETALLE**  
## **Objetivo**  
Desarrollar nueva funcionalidad que muestre información detallada del Proveedor y Productos relacionados cuando una Nota de Traslado está asociada a un Reclamo (*InventoryClaim*).  

---

## **Subtareas Técnicas**  


### 📝**REP-4513 .BASE DE DATOS: Armar set de datos**
**Descripción**
- Generar SET de datos en las entidades: delivery_notes, inventory_claims y inventory_claims_states.

---

### 📝**REP-4514. BACKEND Ajuste GET: spareparts/DeliveryNote/{id}**  
**Descripción**
- DeliveryNoteMappingService . Modificar el mapeo de Reciever
- DeliveryNoteDetailMappingService . Modificar el mapeo de WarehouseAddress
- Agregar a DeliveryNoteDetailViewModel la propiedad InventoryClaimId nulleable 

**Pasos**:  
- [ ] Ver query SQL para obtener datos del Proveedor desde.   
- [ ] Integrar consulta en el backend (API).  
- [ ] Actualizar frontend (UI) para mostrar datos en la sección "Destinatario".  

---

### **REP-4516. FRONTEND: Ajuste delivery-note-detail.component en la sección de Ver Detalle de Productos**  

**Descripción**
Revisar GET:spareparts/DeliveryNote/{id} la propiedad InventoryClaimId sea nula. En el caso contrario , se deberá utilizar GET:spareparts/InventoryClaim/{id} para cargar los datos en la sección de ver detalle

### 📝**REP-4517. BACKEND Agregar GET: spareparts/InventoryClaim/{id}** 
**Descripción**
- Falta descripción.  

---

### 📝**REP-4518. FRONTEND: Agregar estado inventory-claims-detail**  
**Descripción**
- Falta descripción. 

---

### **4. Asignación de puntos**  
- [ ] Ponderar todas las tareas con un puntaje.  
- [ ] Ver documento Excel Comprometido Vs Quemado

### **5. Pruebas**  
- [ ] Pruebas unitarias (backend)  

---

### **6. Documentación**  
- [ ] Actualizar manual de usuario con la nueva funcionalidad.  


---  


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM2NjkyMDg3Nl19
-->