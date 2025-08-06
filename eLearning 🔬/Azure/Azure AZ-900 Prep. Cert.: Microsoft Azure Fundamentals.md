Tienes 50 máquinas virtuales hospedadas en el centro de datos local. Tienes previsto migrarlos todos a una suscripción de pago por uso en Azure. ¿Qué tipo de modelo de gasto tendrás?

----------

### ✅ Opción elegida: **Modelo de gasto operacional (OPEX)**

Cuando decidís migrar tus 50 máquinas virtuales a Azure con una **suscripción de pago por uso**, estás optando por un **modelo OPEX** (_Operational Expenditure_), en lugar de CAPEX (_Capital Expenditure_).  
Esto significa que:

-   **No hacés una gran inversión inicial** en hardware o infraestructura (CAPEX),
    
-   Sino que **pagás mensualmente** por los recursos que usás (OPEX),
    
-   Lo que te permite **escalar rápidamente** hacia arriba o hacia abajo según demanda,
    
-   Y también **predecir y controlar costos** más fácilmente en el tiempo.
    

----------

### 🧠 ¿Por qué es la mejor elección en este caso?

Porque:

-   No hay un gran gasto inicial.
    
-   Azure te permite usar solo lo que necesitás.
    
-   El modelo es flexible, ideal para migraciones progresivas.
    
-   El costo es considerado gasto operativo y por tanto deducible en muchas contabilidades empresariales.

---
¿Cuál de las siguientes es una técnica para implementar tolerancia a fallos en el software?
- Respaldo y cifrado de datos
- Cifrado de datos
- Replicación de datos
- Respaldo de datos

### ✅ **Replicación de datos**

---

### 📌 ¿Por qué?

**La replicación de datos** es una técnica **clave** para implementar **tolerancia a fallos** porque:

* Consiste en **mantener copias sincronizadas** de los datos en diferentes ubicaciones (servidores, zonas o regiones).
* Si un servidor falla, otro puede **asumir el servicio automáticamente** con los mismos datos.
* Asegura la **disponibilidad continua** del sistema, incluso ante errores o caídas.

---

### 🧠 Diferencias con otras opciones:

| Opción                          | ¿Implementa tolerancia a fallos? | ¿Qué hace?                                                                  |
| ------------------------------- | -------------------------------- | --------------------------------------------------------------------------- |
| **Respaldo y cifrado de datos** | ❌ No directamente                | Protege e integra seguridad, pero los backups no reaccionan en tiempo real. |
| **Cifrado de datos**            | ❌ No                             | Solo protege la confidencialidad. No evita ni reacciona ante fallos.        |
| **Replicación de datos**        | ✅ Sí                             | Permite que el sistema siga funcionando ante fallos.                        |
| **Respaldo de datos**           | ❌ No en tiempo real              | Permite restaurar, pero con interrupciones y pérdida de datos recientes.    |

---

    


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY2NzU0Mjg4NCwtMTUzOTQ0MTA1M119
-->