
### Python entorno virtual
python -m venv venv
venv\Scripts\activate

pip install -r requirements.txt
python run.py

----
>Cumplir ciertos requisitos previos en tu sistema:

#### 🔹 **Python (Entorno Virtual)**

1.  **Instalar Python** (versión 3.6 o superior recomendada).
    
    -   Para verificar:
        
        ```sh
        python --version
        
        ```
        
2.  **Tener `pip` instalado** (suele venir con Python).
    
    -   Para verificar:
        
        ```sh
        pip --version
        
        ```
        
3.  **Crear y activar el entorno virtual:**
    
    -   Windows:
        
        ```sh
        python -m venv venv
        venv\Scripts\activate
        
        ```
        
    -   Linux/macOS:
        
        ```sh
        python -m venv venv
        source venv/bin/activate
        
        ```
        
4.  **Asegurarte de que `requirements.txt` existe y contiene las dependencias necesarias.**
    
    -   Instalarlas con:
        
        ```sh
        pip install -r requirements.txt
        
        ```
        
5.  **Ejecutar el script:**
    
    ```sh
    python run.py
    
    ```
    

-----



### Angular
- npm install (la pirmera vez)
- npm start

>Cumplir ciertos requisitos previos en tu sistema:
#### 🔹 **Angular (Frontend)**

1.  **Tener instalado Node.js y npm** (Recomendado: Node.js 16 o superior).
    
    -   Para verificar:
        
        ```sh
        node -v
        npm -v
        
        ```
        
2.  **Instalar las dependencias del proyecto (solo la primera vez o cuando haya cambios en `package.json`):**
    
    ```sh
    npm install
    
    ```
    
3.  **Ejecutar la aplicación:**
    
    ```sh
    npm start
    
    ```


> **ABM**

src/
├── app/
│   ├── core/
│   │   ├── services/
│   │   │   ├── task.service.ts       
│   │   ├── models/
│   │   │   ├── task.model.ts
│   │   ├── interceptors/
│   │   │   ├── auth.interceptor.ts         
│   ├── shared/
│   │   ├── components/
│   │   │   ├── table/
│   │   │   │   ├── table.component.ts    
│   │   │   │   ├── table.component.html
│   ├── features/
│   │   ├── tasks/                      
│   │   │   ├── tasks.module.ts         
│   │   │   ├── tasks-routing.module.ts 
│   │   │   ├── components/               
│   │   │   │   ├── task-list/          
│   │   │   │   │   ├── task-list.component.ts
│   │   │   │   │   ├── task-list.component.html
│   │   │   │   ├── task-detail/        
│   │   │   │   │   ├── task-detail.component.ts
│   │   │   │   │   ├── task-detail.component.html
│   │   │   │   ├── task-form/          
│   │   │   │   │   ├── task-form.component.ts
│   │   │   │   │   ├── task-form.component.html
│   │   │   ├── services/
│   │   │   │   ├── task-api.service.ts 
│   │   │   ├── models/
│   │   │   │   ├── task.model.ts
│   │   │   │          
│   │   │   ├── auth/                      
│   │   │   ├── auth.module.ts         
│   │   │   ├── auth-routing.module.ts 
│   │   │   ├── components/               
│   │   │   │   ├── login/          
│   │   │   │   │   ├── login.component.ts
│   │   │   │   │   ├── login.component.html
│   │   │   ├── guards/
│   │   │   │   ├── auth.guard.ts    
│   │   │   ├── services/
│   │   │   │   ├── auth.service.ts    
│   ├── app.routes.ts                     
│   ├── app.module.ts

ng generate class core/models/task --type=model
ng generate service core/services/task

ng generate component features/tasks/components/task-list
ng generate component features/tasks/components/task-form
ng generate module features/tasks --routing
ng generate service features/tasks/services/task-api

#### Datos

>login
```json
{
	"username": "vcontreras",
	"password": "Python$2024"
}
```
>task
```json
{
	"title":  "Desarrollo",
	"description":  "Esta es una descripción de la tarea PPyC.",
	"completed":  false,
	"due_date":  "2025-04-05T19:59:59"
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDM2OTE2NzZdfQ==
-->