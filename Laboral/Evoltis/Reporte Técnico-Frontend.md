### **📄 Reporte Técnico: Tecnologías Aplicadas en el Frontend**

## **1. PrimeNG**

### 📌 **Implementación en nuestro código**

Se utilizó **PrimeNG** para mejorar la interfaz de usuario y facilitar la construcción de componentes reutilizables.

### 🔹 **Ejemplo en el código**

-   Se uso **PrimeNG Table (`p-table`)** para mostrar la lista de productos con paginación y filtros:
    
    ```html
    <p-table [value]="productosFiltrados" [paginator]="true" [rows]="5">
      <ng-template pTemplate="header">
        <tr>
          <th pSortableColumn="id">ID</th>
          <th pSortableColumn="nombre">Nombre</th>
          <th pSortableColumn="precio">Precio</th>
          <th pSortableColumn="stock">Stock</th>
          <th>Acciones</th>
        </tr>
      </ng-template>
      <ng-template pTemplate="body" let-producto>
        <tr>
          <td>{{ producto.id }}</td>
          <td>{{ producto.nombre }}</td>
          <td>{{ producto.precio | currency }}</td>
          <td>{{ producto.stock }}</td>
          <td>
            <button pButton label="Editar" (click)="editarProducto(producto)" class="p-button-sm p-button-outlined"></button>
            <button pButton label="Eliminar" (click)="eliminarProducto(producto.id)" class="p-button-sm p-button-danger"></button>
          </td>
        </tr>
      </ng-template>
    </p-table>
    
    ```
    
-   **Botón para agregar productos:**
    
    ```html
    <button pButton label="Nuevo Producto" (click)="nuevoProducto()" class="p-button-raised p-button-success"></button>
    
    ```
----------

## **2. Formularios Reactivos**

### 📌 **Implementación 

Se utilizó **Formularios Reactivos** para gestionar la entrada de datos en el formulario de productos.

### 🔹 **Código**

-   **Definimos el formulario en `producto-form.component.ts`:**
    
    ```typescript
    productoForm = new FormGroup({
      nombre: new FormControl('', [Validators.required, Validators.minLength(3)]),
      precio: new FormControl(0, [Validators.required, Validators.min(1)]),
      stock: new FormControl(0, [Validators.required, Validators.min(0)]),
    });
    
    ```
    
-   **Vinculación con el HTML:**
    
    ```html
    <form [formGroup]="productoForm" (ngSubmit)="guardarProducto()">
      <div class="p-field">
        <label for="nombre">Nombre</label>
        <input id="nombre" type="text" pInputText formControlName="nombre" />
        <small *ngIf="productoForm.get('nombre')?.invalid && productoForm.get('nombre')?.touched">
          Nombre es requerido (mínimo 3 caracteres).
        </small>
      </div>
    
      <div class="p-field">
        <label for="precio">Precio</label>
        <input id="precio" type="number" pInputText formControlName="precio" />
        <small *ngIf="productoForm.get('precio')?.invalid && productoForm.get('precio')?.touched">
          Precio debe ser mayor a 0.
        </small>
      </div>
    
      <button pButton type="submit" label="Guardar" [disabled]="productoForm.invalid"></button>
    </form>
    
    ```

----------

## **3. Tabla con filtros**

### 📌 **Implementación**

Implementamos un campo de búsqueda que filtra los productos en la tabla **sin necesidad de recargar la página**.

### 🔹 **Código en nuestro proyecto**

-   **Filtro en el HTML:**
    
    ```html
    <input type="text" pInputText placeholder="Buscar..." (input)="filtrarProductos($event)" />
    
    ```
    
-   **Lógica del filtro en `productos.component.ts`:**
    
    ```typescript
    filtrarProductos(event: Event) {
      const filtro = (event.target as HTMLInputElement).value.toLowerCase();
      this.productosFiltrados = this.productos.filter(producto =>
        producto.nombre.toLowerCase().includes(filtro) ||
        producto.id.toString().includes(filtro) ||
        producto.precio.toString().includes(filtro) ||
        producto.stock.toString().includes(filtro)
      );
    }
    
    ```
----------

## **4. Redux (NgRx) para Estado Global**

### 📌 **Implementación**

Redux (NgRx) se utilizó para **almacenar y gestionar el estado global de los productos**, evitando peticiones innecesarias al backend.

### 🔹 **Código en nuestro proyecto**

1️⃣ **Definimos el estado en `producto.reducer.ts`:**

```typescript
export interface ProductoState {
  productos: Producto[];
}

export const initialState: ProductoState = {
  productos: []
};

export const productoReducer = createReducer(
  initialState,
  on(ProductoActions.cargarProductos, (state, { productos }) => ({
    ...state,
    productos: [...productos]
  })),
  on(ProductoActions.eliminarProducto, (state, { id }) => ({
    ...state,
    productos: state.productos.filter(producto => producto.id !== id)
  }))
);

```

2️⃣ **Definimos las acciones en `producto.actions.ts`:**

```typescript
export const cargarProductos = createAction(
  '[Producto] Cargar Productos',
  props<{ productos: Producto[] }>()
);

export const eliminarProducto = createAction(
  '[Producto] Eliminar Producto',
  props<{ id: number }>()
);

```

3️⃣ **Cargamos los productos en `productos.component.ts`:**

```typescript
ngOnInit() {
  this.store.select('productos').subscribe(state => {
    if (state) {
      this.productos = state.productos;
      this.productosFiltrados = [...this.productos];
    }
  });
  this.cargarProductos();
}

cargarProductos() {
  this.productoService.getProductos().subscribe((productos) => {
    this.store.dispatch(ProductoActions.cargarProductos({ productos }));
  });
}

```

4️⃣ **Eliminar producto y actualizar el store:**

```typescript
eliminarProducto(id: number) {
  if (confirm('¿Seguro que deseas eliminar este producto?')) {
    this.productoService.deleteProducto(id).subscribe(() => {
      this.store.dispatch(ProductoActions.eliminarProducto({ id }));
    });
  }
}

```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyMjQ2MjgwNjNdfQ==
-->