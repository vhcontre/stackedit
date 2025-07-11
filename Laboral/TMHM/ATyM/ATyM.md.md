## 📌**Documento de Detalle de Trabajo - Implementación de Servicios Rental**  
**Sistemas Involucrados:** ATyM (Sistema Interno) y Web Institucional  
**Tecnología:** .NET  

---

## **1. Objetivo**  
Implementar las funcionalidades faltantes para el módulo de **Rental** en los sistemas ATyM y Web Institucional, completando el sexto requisito pendiente según lo solicitado.  

---

## **2. Alcance**  
### **2.1 Web Institucional**  
- **Adjuntar imagen en formulario de Rental**  
  - Modificar el formulario principal para permitir al cliente subir una imagen al final.  
  - La imagen debe enviarse **solo al correo** de `FormularioTMHM` sin almacenarse en ATyM.  

### **2.2 ATyM (Sistema Interno)**  
#### **Flujo de Estados Modificado**  
- **Omisión de pasos intermedios:**  
  - Las solicitudes de Rental pasarán directamente de **"Recepción" → "Planificación"** (sin estados intermedios).  
- **Agregar calendario en "Planificación":**  
  - Permitir seleccionar fecha mediante un calendario interactivo.  

#### **Notificaciones por Email**  
1. **Al pasar de "Recepción" a "Planificación":**  
   - Enviar correo automático al cliente con detalles de la solicitud.  
2. **Al finalizar "Planificación":**  
   - Enviar otro correo confirmando la fecha programada.  
3. **Al marcar "Servicio Realizado/Cumplido":**  
   - Agregar una instancia donde el planificador debe tildar esta opción y enviar confirmación al cliente.  

#### **Carga Masiva de Datos**  
- **Subida del Maestro Rental:**  
  - Permitir al usuario interno (TMHM) cargar un archivo maestro (ej. Excel) con datos de **cliente-modelo-chasis** para actualizar la tabla `RentalParque`.  
  - La carga se realiza **una vez al mes** aproximadamente.  

---

## **3. Requerimientos Técnicos**  
### **3.1 Web Institucional**  
- **Frontend:**  
  - Agregar campo `input type="file"` en el formulario de Rental.  
  - Validar formato (ej. JPG, PNG) y tamaño máximo (ej. 5MB).  
- **Backend:**  
  - Ajustar el método de envío para incluir la imagen como adjunto en el correo a `FormularioTMHM`.  

### **3.2 ATyM **  
- **Base de Datos:**  
  - Modificar el flujo de estados en la tabla correspondiente (eliminar pasos intermedios).  
  - Crear campo para almacenar la fecha seleccionada en "Planificación".  
- **Notificaciones:**  
  - Configurar triggers para enviar correos en los cambios de estado.  
- **Carga Masiva:**  
  - Desarrollar una pantalla con:  
    - Opción para subir archivo (Excel/CSV).  
    - Validación de datos antes de importar a `RentalParque`.  
    - Log de errores (ej. registros duplicados).  

---

## **4. Entregables**  
1. **Web Institucional:**  
   - Formulario de Rental con carga de imágenes funcional. ✅ Sí
2. **ATyM:**  
   - Flujo de estados simplificado (Recepción → Planificación → Realizado).  ✅ Sí
   - Nuevo flujo de estado  (Servicio realizado).  ✅ Sí 
   - Calendario en etapa de Planificación.  ✅ Sí   
   - Notificaciones automáticas por email en cada transición clave.  ✅ Sí
   - Módulo de carga masiva de clientes-modelos-chasis.  ❌ No
---

## **5. Consideraciones**  
- **Pruebas:**  
  - Verificar que los correos se envíen correctamente en cada transición.  
  - Validar la importación de datos masivos con archivos de prueba.  
- **Seguridad:**  
  - Restringir la carga de archivos a formatos permitidos (evitar scripts maliciosos).  

---

**Elaborado por:** Víctor Hugo Contreras
**Fecha:** 09-05-2025
**Revisado por:** Martín Rosmino

--- 


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyMzY3NjU4NTVdfQ==
-->