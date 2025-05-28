**Workflow básico de Jira** para gestionar proyectos ágiles (como Scrum o Kanban), incluyendo los conceptos clave: **Brief, Épicas, Historias de Usuario (User Stories), Tareas** y el flujo de trabajo estándar.  

---

## **1. Estructura Jerárquica en Jira**  
En Jira, los elementos se organizan así (de mayor a menor):  
1. **Brief/Iniciativa** (Opcional, a alto nivel).  
2. **Épica** (Agrupa funcionalidades grandes, ej: "Sistema de Login").  
3. **Historia de Usuario (User Story)** (Requerimientos específicos, ej: "Como usuario, quiero iniciar sesión con Google").  
4. **Tarea/Subtarea** (Pasos concretos para completar la historia, ej: "Integrar API de OAuth").  

---

## **2. Workflow Básico en Jira**  
### **Paso 1: Crear una Épica**  
- **Qué es**: Una gran funcionalidad que requiere múltiples historias.  
- **Ejemplo**:  
  - *Nombre*: "Rediseño del Dashboard".  
  - *Descripción*: "Mejorar la interfaz del panel principal".  

### **Paso 2: Descomponer en Historias de Usuario**  
- **Formato estándar**:  
  > _"Como [rol], quiero [acción] para [beneficio]."_  
- **Ejemplo**:  
  - *Historia*: "Como cliente, quiero filtrar productos por precio para encontrar opciones más rápido".  
  - **Criterios de Aceptación**:  
    1. El filtro debe incluir rangos predefinidos (ej: $0-$50).  
    2. Los resultados se actualizan en tiempo real.  

### **Paso 3: Dividir en Tareas/Subtareas**  
- Ejemplo para la historia anterior:  
  - "Crear endpoint de filtrado en backend".  
  - "Diseñar componente de filtro en frontend".  

### **Paso 4: Flujo de Estados (Workflow)**  
Los tickets suelen moverse así:  
```  
📝 **To Do** → 🏗️ **In Progress** → ⏳ **In Review** → ✅ **Done**  
```  
(Opcional: "Blocked", "Testing", etc., según tu equipo).  

---

## **3. Campos Clave en Jira**  
- **Prioridad** (Alta/Media/Baja).  
- **Sprint** (Si usas Scrum, asigna historias a iteraciones).  
- **Estimación** (Horas o *Story Points*).  
- **Asignado a** (Responsable).  

---

## **4. Consejos Prácticos**  
✔ **Usa etiquetas** (ej: `frontend`, `bug`) para filtrar.  
✔ **Vincula issues** (ej: "Esta tarea bloquea la historia X").  
✔ **Comenta actualizaciones** para mantener al equipo alineado.  

---

### **Ejemplo Visual en Jira**  
| Tipo     | Título                          | Estado      | Asignado |  
|----------|---------------------------------|------------|----------|  
| Épica    | Rediseño Dashboard             | To Do      | -        |  
| Historia | Filtrar productos por precio   | In Progress| Ana      |  
| Tarea    | Crear API de filtrado          | Done       | Carlos   |  

---


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNTk3NzY0NV19
-->