Trabajo práctico en JavaScript con patrones de diseño, debemos estructurar la solución en varias partes.

### **Enfoque con Patrones de Diseño**

Para este sistema, algunos patrones de diseño clave que podemos aplicar son:

1.  **Factory Method**:
    
    -   Para la creación de usuarios con distintos roles (chair, revisor, autor), ya que todos comparten atributos pero tienen funciones diferentes.
    -   También puede ser útil para crear artículos de distintos tipos (regular o póster).
2.  **Singleton**:
    
    -   Para manejar la conferencia y asegurarnos de que haya solo una instancia activa.
3.  **Observer**:
    
    -   Para notificar cambios de estado en las sesiones a los revisores, autores o chairs.
4.  **Strategy**:
    
    -   Para implementar diferentes estrategias de selección de artículos en la fase final (Corte fijo vs. Mejores).
5.  **State**:
    
    -   Para controlar las distintas etapas de la conferencia (Recepción, Bidding, Asignación y Revisión, Selección).

### **Plan de Implementación**

1.  **Definir clases base** (Usuario, Conferencia, Sesión, Artículo, Revisión).
2.  **Implementar Factory para Usuarios y Artículos**.
3.  **Aplicar Singleton a la Conferencia**.
4.  **Incorporar Observer para las notificaciones**.
5.  **Usar State para manejar los cambios de estado de las sesiones**.
6.  **Implementar Strategy para la selección de artículos**.


Empezar con la estructura base del código en JavaScript, definiendo las clases principales: `Usuario`, `Conferencia`, `Sesión`, `Artículo` y `Revisión`. Luego aplicar los patrones de diseño.

### **Paso 1: Clases Base**

Definir las clases principales con las propiedades básicas necesarias. Luego agregar lógica y patrones de diseño.

Código inicial:
```js
// Factory Method para crear usuarios
class UsuarioFactory {
    static crearUsuario(nombreCompleto, afiliacion, email, contrasena) {
        return new Usuario(nombreCompleto, afiliacion, email, contrasena);
    }
}

// Clase Usuario
class Usuario {
    constructor(nombreCompleto, afiliacion, email, contrasena) {
        this.nombreCompleto = nombreCompleto;
        this.afiliacion = afiliacion;
        this.email = email;
        this.contrasena = contrasena;
    }
}

// Factory Method para crear artículos
class ArticuloFactory {
    static crearArticulo(titulo, tipo, archivoAdjunto, autores, autorEncargado) {
        return new Articulo(titulo, tipo, archivoAdjunto, autores, autorEncargado);
    }
}

// Clase Artículo
class Articulo {
    constructor(titulo, tipo, archivoAdjunto, autores, autorEncargado) {
        this.titulo = titulo;
        this.tipo = tipo; // 'regular' o 'poster'
        this.archivoAdjunto = archivoAdjunto;
        this.abstract = tipo === 'regular' ? "" : null;
        this.archivoFuentes = tipo === 'poster' ? "" : null;
        this.autores = autores;
        this.autorEncargado = autorEncargado;
        this.revisiones = [];
    }
    
    agregarRevision(revision) {
        if (this.revisiones.length < 3) {
            this.revisiones.push(revision);
            Notificador.notificar(`Nueva revisión agregada por ${revision.revisor.nombreCompleto}`);
        } else {
            console.log("Este artículo ya tiene 3 revisiones.");
        }
    }
}

// Clase Revisión
class Revision {
    constructor(revisor, puntaje, comentario) {
        this.revisor = revisor;
        this.puntaje = puntaje;
        this.comentario = comentario;
    }
}

// Clase Sesión
class Sesion {
    constructor(nombre, tema, tipo, deadline) {
        this.nombre = nombre;
        this.tema = tema;
        this.tipo = tipo;
        this.deadline = deadline;
        this.articulos = [];
    }
    
    agregarArticulo(articulo) {
        this.articulos.push(articulo);
        Notificador.notificar(`Nuevo artículo agregado a la sesión: ${this.nombre}`);
    }
}

// Singleton para la clase Conferencia
class Conferencia {
    constructor(nombre, fechaInicio, fechaFin) {
        if (Conferencia.instancia) {
            return Conferencia.instancia;
        }
        this.nombre = nombre;
        this.fechaInicio = fechaInicio;
        this.fechaFin = fechaFin;
        this.chairs = [];
        this.comitePrograma = [];
        this.sesiones = [];
        Conferencia.instancia = this;
    }
    
    agregarChair(usuario) {
        this.chairs.push(usuario);
    }
    
    agregarComite(usuario) {
        this.comitePrograma.push(usuario);
    }
    
    agregarSesion(sesion) {
        this.sesiones.push(sesion);
        Notificador.notificar(`Nueva sesión agregada a la conferencia: ${this.nombre}`);
    }
}

// Observer para notificaciones
class Notificador {
    static observadores = [];
    
    static suscribir(observador) {
        this.observadores.push(observador);
    }
    
    static notificar(mensaje) {
        this.observadores.forEach(observador => observador.actualizar(mensaje));
    }
}

// Ejemplo de un observador
class ObservadorConsola {
    actualizar(mensaje) {
        console.log(`Notificación: ${mensaje}`);
    }
}

// Suscribimos un observador
Notificador.suscribir(new ObservadorConsola());

```

Este código establece las clases base sin patrones de diseño aún. Ahora podemos los siguientes:

1.  Aplicar **Factory Method** para la creación de usuarios y artículos.
2.  Convertir **Conferencia** en un **Singleton**.
3.  Implementar **Observer** para manejar notificaciones.
4.  Incorporar **State** para gestionar los estados de las sesiones.
5.  Agregar **Strategy** para la selección de artículos.

```js
// Singleton: Gestor de Conferencia
class Conference {
    constructor(name) {
        if (Conference.instance) {
            return Conference.instance;
        }
        this.name = name;
        this.sessions = [];
        Conference.instance = this;
    }
    
    addSession(session) {
        this.sessions.push(session);
    }
}

// Factory Method: Creación de usuarios
class User {
    constructor(name, affiliation, email) {
        this.name = name;
        this.affiliation = affiliation;
        this.email = email;
    }
}

class UserFactory {
    static createUser(type, name, affiliation, email) {
        switch (type) {
            case "Chair":
                return new Chair(name, affiliation, email);
            case "Revisor":
                return new Revisor(name, affiliation, email);
            case "Autor":
                return new Autor(name, affiliation, email);
            default:
                throw new Error("Tipo de usuario desconocido");
        }
    }
}

class Chair extends User {}
class Revisor extends User {
    expressInterest(article, interestLevel) {
        console.log(`${this.name} expresa interés: ${interestLevel} en el artículo ${article.title}`);
    }
}
class Autor extends User {}

// Observer: Notificación de cambios a los autores
class Article {
    constructor(title, type) {
        this.title = title;
        this.type = type;
        this.authors = [];
        this.observers = [];
    }
    
    addObserver(observer) {
        this.observers.push(observer);
    }
    
    notifyObservers(message) {
        this.observers.forEach(observer => observer.update(message));
    }
    
    changeStatus(newStatus) {
        console.log(`Artículo ${this.title} cambiado a estado: ${newStatus}`);
        this.notifyObservers(`El estado del artículo '${this.title}' cambió a ${newStatus}`);
    }
}

// Strategy: Diferentes estrategias de selección de artículos
class SelectionStrategy {
    selectArticles(articles) {
        throw new Error("Método selectArticles() debe ser implementado");
    }
}

class FixedCutoffStrategy extends SelectionStrategy {
    constructor(percentage) {
        super();
        this.percentage = percentage;
    }
    selectArticles(articles) {
        const numAccepted = Math.ceil(articles.length * this.percentage);
        return articles.sort((a, b) => b.score - a.score).slice(0, numAccepted);
    }
}

class BestScoreStrategy extends SelectionStrategy {
    constructor(minScore) {
        super();
        this.minScore = minScore;
    }
    selectArticles(articles) {
        return articles.filter(article => article.score >= this.minScore);
    }
}

// State: Gestión de estados de la sesión
class SessionState {
    handle(session) {
        throw new Error("Método handle() debe ser implementado");
    }
}

class ReceptionState extends SessionState {
    handle(session) {
        console.log("Estado: Recepción. Se pueden enviar artículos.");
        session.setState(new BiddingState());
    }
}

class BiddingState extends SessionState {
    handle(session) {
        console.log("Estado: Bidding. Revisores expresan interés.");
        session.setState(new ReviewState());
    }
}

class ReviewState extends SessionState {
    handle(session) {
        console.log("Estado: Revisión. Revisores evalúan artículos.");
        session.setState(new SelectionState());
    }
}

class SelectionState extends SessionState {
    handle(session) {
        console.log("Estado: Selección. Se eligen los mejores artículos.");
    }
}

class Session {
    constructor(name, selectionStrategy) {
        this.name = name;
        this.articles = [];
        this.state = new ReceptionState();
        this.selectionStrategy = selectionStrategy;
    }
    
    setState(newState) {
        this.state = newState;
    }
    
    processState() {
        this.state.handle(this);
    }
    
    selectArticles() {
        return this.selectionStrategy.selectArticles(this.articles);
    }
}

// Ejemplo de uso
// Singleton: Se crea una única instancia de la conferencia
const globalConference = new Conference("ComfyChair 2025");

// Creación de una sesión con Strategy (FixedCutoffStrategy)
const sessionAI = new Session("Inteligencia Artificial", new FixedCutoffStrategy(0.5));
globalConference.addSession(sessionAI);

// Factory Method: Creación de usuarios
const chair = UserFactory.createUser("Chair", "Ana Pérez", "UNLP", "ana@example.com");
const revisor = UserFactory.createUser("Revisor", "Carlos López", "UNLP", "carlos@example.com");
const autor = UserFactory.createUser("Autor", "María Gómez", "UBA", "maria@example.com");

// Creación de un artículo y aplicación del patrón Observer
const article1 = new Article("Redes Neuronales en la Industria", "Regular");
article1.authors.push(autor); // Se asocia un autor al artículo
article1.addObserver(autor); // El autor será notificado de cambios en el artículo

// Se agrega el artículo a la sesión
sessionAI.articles.push(article1);

console.log("Inicio del proceso de la sesión");
// Aplicación del patrón State: transiciones de estado de la sesión
sessionAI.processState(); // Pasa a Bidding
sessionAI.processState(); // Pasa a Revisión
sessionAI.processState(); // Pasa a Selección

console.log("Proceso de selección de artículos");
// Aplicación del patrón Strategy para seleccionar artículos
const acceptedArticles = sessionAI.selectArticles();
console.log("Artículos aceptados:", acceptedArticles.map(a => a.title));

```

Justificación teórica y técnica de cada patrón utilizado en tu implementación del sistema de gestión de conferencias:

----------

### **1. Singleton – Gestión de la Conferencia**

**Justificación teórica:**  
El patrón **Singleton** se utiliza para garantizar que una clase tenga una única instancia y proporcionar un punto de acceso global a ella. Esto es útil cuando se necesita un objeto centralizado que coordine las operaciones de un sistema.

**Justificación técnica:**  
En el contexto de la conferencia, solo debe existir una instancia de la clase `Conference`, ya que representa un único evento académico donde se organizan las sesiones. Implementar Singleton evita la creación de múltiples instancias que puedan generar inconsistencias en la gestión de sesiones.

----------

### **2. Factory Method – Creación de Usuarios**

**Justificación teórica:**  
El patrón **Factory Method** permite encapsular la lógica de creación de objetos, facilitando la creación de instancias sin exponer directamente la lógica de instanciación. Se usa para proporcionar una interfaz común y reducir el acoplamiento en el código.

**Justificación técnica:**  
Se usa un `UserFactory` para crear diferentes tipos de usuarios (`Chair`, `Revisor`, `Autor`). Esto simplifica la creación y evita que el código que usa estos objetos tenga que conocer los detalles de su construcción, promoviendo la extensibilidad y mantenibilidad.

----------

### **3. Observer – Notificación de Cambios en los Artículos**

**Justificación teórica:**  
El patrón **Observer** define una relación de suscripción entre objetos, permitiendo que múltiples observadores sean notificados automáticamente cuando el estado del sujeto cambia.

**Justificación técnica:**  
Los autores de un artículo necesitan ser notificados cuando su estado cambia. Al usar `addObserver()` en la clase `Article`, los autores pueden recibir notificaciones cuando su artículo pase por distintos estados (por ejemplo, aceptado o rechazado). Esto mejora la comunicación dentro del sistema sin necesidad de acoplar fuertemente los componentes.

----------

### **4. Strategy – Selección de Artículos**

**Justificación teórica:**  
El patrón **Strategy** permite definir una familia de algoritmos, encapsularlos y hacerlos intercambiables sin modificar el código cliente. Esto es útil cuando un comportamiento puede variar y se quiere permitir su modificación sin alterar la estructura principal del código.

**Justificación técnica:**  
Dado que existen múltiples formas de seleccionar artículos en una conferencia (por porcentaje de corte o por puntaje mínimo), se definen estrategias de selección (`FixedCutoffStrategy` y `BestScoreStrategy`). Esto permite cambiar fácilmente el criterio de selección sin modificar el código de la clase `Session`.

----------

### **5. State – Gestión del Estado de la Sesión**

**Justificación teórica:**  
El patrón **State** permite que un objeto altere su comportamiento cuando cambia su estado interno. Es una alternativa a las estructuras condicionales complejas y facilita la transición entre estados de manera clara.

**Justificación técnica:**  
El flujo de una sesión académica pasa por varios estados (`Recepción`, `Bidding`, `Revisión` y `Selección`). Implementar un patrón de estado permite gestionar estos cambios sin usar estructuras condicionales anidadas, asegurando que cada estado tenga su propia lógica de transición y facilitando futuras modificaciones.

----------

### **Conclusión General**

Cada patrón aplicado responde a una necesidad específica del sistema de gestión de conferencias:

-   **Singleton** evita duplicaciones en la conferencia.
-   **Factory Method** simplifica la creación de usuarios y mejora la extensibilidad.
-   **Observer** permite la notificación automática a los autores sobre el estado de sus artículos.
-   **Strategy** proporciona flexibilidad en los criterios de selección de artículos.
-   **State** organiza la transición de la sesión entre sus diferentes etapas sin complejidad innecesaria.

Esta combinación de patrones mejora la organización, modularidad y mantenibilidad del código, asegurando que el sistema sea flexible y escalable para futuras modificaciones.

----------


<!--stackedit_data:
eyJoaXN0b3J5IjpbODU2NDU5MTI4XX0=
-->