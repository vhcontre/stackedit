## Jira: https://evoltis.atlassian.net/browse/TAL-3491
### **Subtareas [MAESTROS] 8.4 CONFIGURACIÓN TOPES DE DESCUENTOS - INCREMENTOS**  

#### **🔹 [FRONTEND] - Configuración de rutas, navegación y permisos (Seguridad)**  
1. **Configuración de rutas y navegación**  
   - Crear estructura de menú en el frontend:  
     - Padre: `Configuraciones` (URL: `/configs`).  
     - Hijo: `Topes de Descuentos/Incrementos` (URL: `/configs/discounts-increases/`).  
     - Nieto: `Ver Detalle` (URL: `/configs/discounts-increases/detail`).  
   - Implementar breadcrumb dinámico:  
     ```plaintext
     Home → Configuraciones → Descuentos-Incrementos → Ver Detalle
     ```  
   - Configurar redirecciones en breadcrumb:  
     - *Home* → Redirige a `/home`.  
     - *Descuentos-Incrementos* → Redirige a [URL de solicitud de acceso](https://evoltis.atlassian.net/wiki/...).  

2. **Lógica de permisos en frontend**  
   - Ocultar/mostrar opciones de menú según el permiso **"Consulta"**.  
   - Redirección automática a `/home` si el usuario no tiene permisos (tras validación inicial).  

---

#### **🔹 [SECURITY-DB] - Scripts para estructura de menú y permisos (Seguridad)**  
1. **Scripts sql para la estructura de menú y permisos**  
   - Crear Scripts para:  
     - Obtener jerarquía de menú (incluyendo las nuevas opciones).  
     - Validar permisos del usuario para `Ver Detalle` (rol "Consulta").     

2. **Lógica de seguridad en backend**  
   - Validar permisos en cada request a `/configs/discounts-increases/detail`.  
   - Retornar `ERROR` si el usuario no tiene acceso (frontend redirige a Home).  
---

### **Validaciones técnicas cruzadas**  
- **Frontend-Backend**:  
  - Asegurar que las URLs coincidan en ambas capas.  
  - Sincronizar nombres de permisos (`"Consulta"`).  
- **Seguridad**:  
  - **Backend** debe rechazar peticiones sin token válido o permisos.  


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMzNDEwNDEyOF19
-->