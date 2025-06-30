## Jira: https://evoltis.atlassian.net/browse/TAL-3491
### **Subtareas [MAESTROS] 8.4 CONFIGURACIÓN TOPES DE DESCUENTOS - INCREMENTOS**  

---

#### **🔹 [FRONTEND] - Implementación de Vista General y Auditoría (Funcionalidad)**
1. **Vista General (UI)**  
   - Mostrar pestaña **"General"** con los siguientes campos:  
     - **Nombre de la compañía**: Texto completo (sin tipo de persona) → `[business_unit_variation_configuration].[business_units].[companies].[people]`.  
     - **Unidad de Negocios**: Texto → `[business_unit_variation_configuration].[business_units].[Name]`.  
     - **Nombre de la configuración**: Texto → `[business_unit_variation_configuration].[Name]`.  
     - **Máximo Incremento**: Decimal (formato `40.00 %`).  
     - **Máximo Descuento**: Decimal (formato `10.00 %`).  
     - **Fecha de Creación**: Formato `DD/MM/YYYY`.  
     - **Creador por**: Nombre completo (sin tipo de persona) → `[users].[people]`.  
     - **Habilitado**: Mostrar como **"Sí" (1)** o **"No" (0)**.  

2. **Vista Auditoría (UI)**  
   - Implementar pestaña **"Auditoría"** con el componente `[AUDITORIA]`.  
   - Mostrar datos de auditoría de la tabla `[business_unit_variation_configuration]`.  

3. **Navegación y Redirección**  
   - Botón/Enlace para **"Volver"** → Redirige a [URL de solicitud de acceso](https://evoltis.atlassian.net/wiki/spaces/Maipu/pages/1550090264).  
   - Breadcrumb funcional con redirecciones (Home → Configuraciones → ...).  

---

#### **🔹 [BACKEND] - Configuración General y Auditoría (Funcionalidad)**  
1. **API de Datos (General)**  
   - Endpoint para obtener datos de:  
     - Compañía, Unidad de Negocios, Configuración (nombre, incremento, descuento).  
     - Fecha de creación y usuario creador (formateados).  
     - Estado `IsEnabled` (traducido a `1`/`0`).  

2. **API de Auditoría**  
   - Endpoint específico para datos de auditoría (`[business_unit_variation_configuration]`).  
   - Incluir historial de cambios, usuario modificador, etc.  

3. **Seguridad y Validaciones**  
   - Asegurar que el usuario tenga permiso **"Consulta"** para acceder a los datos.  
   - Filtrar datos según la unidad de negocio del usuario (si aplica).  


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTUxNTU5NTkxXX0=
-->