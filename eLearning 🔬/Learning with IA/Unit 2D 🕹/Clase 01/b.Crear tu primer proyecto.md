# How-To: Crear tu primer proyecto Unity 2D y abrirlo en Visual Studio

---

### 1. Abrir Unity Hub

* Ejecutá **Unity Hub** en tu PC/Mac.
* Si no lo tenés abierto, buscá el programa y arrancalo.

---

### 2. Crear nuevo proyecto

* En Unity Hub → pestaña **Projects** → botón **New Project**.
* Elegí la plantilla **2D** (debería ser la primera opción o cerca).
* Poné nombre a tu proyecto, ejemplo: `MiPrimerJuego2D`.
* Seleccioná la ubicación donde querés guardar el proyecto (una carpeta simple, sin espacios ni caracteres raros).
* Hacé clic en **Create**.

---

### 3. Conocer la ventana principal de Unity

* Se abrirá el editor Unity con tu proyecto nuevo.
* Verificá que ves estas ventanas:

  * **Scene** (donde podés construir el mundo).
  * **Game** (vista previa del juego).
  * **Hierarchy** (lista de objetos en escena).
  * **Inspector** (propiedades del objeto seleccionado).
  * **Project** (archivos del proyecto).
  * **Console** (mensajes y errores).

---

### 4. Crear un GameObject vacío

* En la ventana **Hierarchy**, hacé clic derecho → **Create Empty**.
* Renombrá ese objeto a `Player` (por ejemplo).

---

### 5. Crear el script C# para controlar al Player

* Con el `Player` seleccionado, en la ventana **Inspector**, hacé clic en **Add Component** → seleccioná **New Script**.
* Poné el nombre: `PlayerController` y asegurate que el lenguaje sea **C#**.
* Presioná **Create and Add**.

---

### 6. Escribir código para mover al Player

* En Unity, hacé doble clic en el script `PlayerController.cs`.
* Esto abrirá Visual Studio (o el editor que tengas configurado).
* Pegá este código dentro, reemplazando el contenido generado por defecto:

```csharp
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    public float speed = 5f;

    void Update()
    {
        float move = Input.GetAxis("Horizontal");
        transform.Translate(Vector3.right * move * speed * Time.deltaTime);
    }
}
```

* Guardá el archivo.

---

### 7. Volver a Unity y probar el juego

* Volvé a Unity.
* Presioná el botón **Play** (arriba, en el centro).
* Usá las flechas izquierda y derecha (o A/D) para mover el objeto `Player`.
* Deberías ver que se mueve horizontalmente en la ventana **Game**.

---

### 8. Modificar velocidad desde el Inspector (opcional)

* Con el `Player` seleccionado, en el **Inspector** buscá el campo `Speed`.
* Cambiá el valor a, por ejemplo, 10 y volvé a presionar **Play** para notar que va más rápido.

---

### 9. Guardar el proyecto

* En Unity, guardá la escena: `File > Save Scene` y poné un nombre como `MainScene`.
* Guardá el proyecto: `File > Save Project`.

---

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ4NDczMDg1Nl19
-->