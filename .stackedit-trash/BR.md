## **Documentación de Endpoints de Claro Video API 📱**

Se detallan los **endpoints** disponibles para interactuar con la API de **Brasil/Auth**. Cada endpoint está descrito con su propósito, parámetros y ejemplo de uso.

----------

### **1. user/login By userhash** 🔑

-   **Descripción**: Este endpoint es utilizado para realizar el login de un usuario mediante un "userhash". La respuesta incluye un token de autenticación y datos relacionados con la sesión del usuario. 👤💻
    
-   **Método**: `GET` 🚀
    
-   **URL**: `{{SERVER_URL}}/services/user/login`
    

**Parámetros de consulta (Query Parameters):**

```
| Clave               | Descripción                                   | Valor Ejemplo                           |
|---------------------|-----------------------------------------------|-----------------------------------------|
| HKS                 | String que identifica la sesión.              | 03b0d59e7ff3cac790adb31285d0093364911490b2f14 |
| api_version         | Versión de la API.                            | v5.93                                   |
| authpn              | Identificador de proveedor de autenticación.  | {{authpn}}                              |
| authpt              | Identificador de tipo de autenticación.       | {{authpt}}                              |
| device_category     | Categoría del dispositivo.                    | {{device_category}}                     |
| device_id           | ID del dispositivo.                           | 03b0d59e-7ff3-cac7-90ad-b31285d00933    |
| device_manufacturer | Fabricante del dispositivo.                   | {{device_manufacturer}}                 |
| device_model        | Modelo del dispositivo.                       | {{device_model}}                        |
| device_name         | Nombre del dispositivo.                       | lg                                      |
| device_so           | Sistema operativo del dispositivo.            | Linux                                   |
| device_type         | Tipo de dispositivo.                          | {{device_type}}                         |
| format              | Formato de la respuesta.                      | json                                    |
| includpaywayprofile | Incluir perfil de pago.                      | true                                    |
| region              | Región del usuario.                           | argentina                               |
| user_id             | ID del usuario.                               | {{userId}}                              |
| userhash            | Hash del usuario.                             | {{userHash}}                            |

```

**Encabezados (Headers):**

```
| Clave        | Valor               | Estado    |
|--------------|---------------------|-----------|
| partition    | claromexhomolog     | Desactivado|
| partition    | clarobnetuat        | Activado  |
| partition    | claroglobaluat      | Desactivado|

```

**Scripts:**

-   **Prerrequest**: No tiene scripts asociados.
    
-   **Test**: Al recibir la respuesta, se extraen los valores y se almacenan como variables globales para su uso posterior. 📦
    

```javascript
const response = pm.response.json();
pm.globals.set("userToken", response.response.user_token);
pm.globals.set("user_session", response.response.user_session);
pm.globals.set("userHash", response.response.session_userhash);
pm.globals.set("varHKS", response.response.session_stringvalue);
pm.globals.set("userId", response.response.user_id);
pm.globals.set("username", response.response.username);

```

**Respuesta**: Vacía (sin contenido). ❌

----------

### **2. user/isloggedin** 🔒

-   **Descripción**: Este endpoint permite verificar si un usuario está autenticado o no. ✅
    
-   **Método**: `GET` 🚀
    
-   **URL**: `{{SERVER_URL}}/services/user/isloggedin`
    

**Parámetros de consulta (Query Parameters):**

```
| Clave               | Descripción                                   | Valor Ejemplo          |
|---------------------|-----------------------------------------------|------------------------|
| device_name         | Nombre del dispositivo.                       | 3810X                  |
| authpn              | Identificador de proveedor de autenticación.  | {{authpn}}             |
| device_category     | Categoría del dispositivo.                    | {{device_category}}    |
| device_manufacturer | Fabricante del dispositivo.                   | {{device_manufacturer}}|
| region              | Región del usuario.                           | argentina             |
| authpt              | Identificador de tipo de autenticación.       | {{authpt}}             |
| device_model        | Modelo del dispositivo.                       | {{device_model}}       |
| HKS                 | Valor de la sesión.                           | {{varHKS}}             |
| device_type         | Tipo de dispositivo.                          | {{device_type}}        |
| format              | Formato de la respuesta.                      | json                   |
| api_version         | Versión de la API.                            | v5.86                  |
| user_hash           | Hash del usuario.                             | {{userHash}}           |
| user_id             | ID del usuario.                               | {{userId}}             |

```

**Encabezados (Headers):**

```
| Clave        | Valor               | Estado     |
|--------------|---------------------|------------|
| partition    | clarobnetuat        | Activado   |

```

**Respuesta**: Vacía (sin contenido). ❌

----------


### **3. user/startheaderinfo** 📝

-   **Descripción**: Este endpoint se utiliza para obtener información del encabezado de la sesión del usuario. 🧑‍💻
    
-   **Método**: `GET` 🚀
    
-   **URL**: `{{SERVER_URL}}/services/user/startheaderinfo`
    

**Parámetros de consulta (Query Parameters):**

```
| Clave               | Descripción                                   | Valor Ejemplo           |
|---------------------|-----------------------------------------------|-------------------------|
| device_id           | ID del dispositivo.                           | web                     |
| device_category     | Categoría del dispositivo.                    | {{device_category}}      |
| device_manufacturer | Fabricante del dispositivo.                   | {{device_manufacturer}}  |
| device_model        | Modelo del dispositivo.                       | {{device_model}}         |
| device_type         | Tipo de dispositivo.                          | {{device_type}}          |
| api_version         | Versión de la API.                            | v5.93                    |
| authpn              | Identificador de proveedor de autenticación.  | {{authpn}}               |
| authpt              | Identificador de tipo de autenticación.       | {{authpt}}               |
| format              | Formato de la respuesta.                      | json                    |
| device_so           | Sistema operativo del dispositivo.            | Chrome                  |
| HKS                 | Valor de la sesión.                           | {{varHKS}}              |

```

**Encabezados (Headers):**

```
| Clave        | Valor               | Estado     |
|--------------|---------------------|------------|
| partition    | claromexhomolog     | Desactivado|

```

**Scripts:**

-   **Test**: Al recibir la respuesta, se extrae la región y se guarda como variable global. 🌍
    

```javascript
const response = pm.response.json();
pm.globals.set("region", response.response.region);

```

**Respuesta**: Vacía (sin contenido). ❌

----------

### **4. user/net/oauth_callback_login** 🔄

-   **Descripción**: Este endpoint es utilizado para completar el proceso de login mediante OAuth en la plataforma. 🔑🔓
    
-   **Método**: `GET` 🚀
    
-   **URL**: `{{SERVER_URL}}/services/user/net/oauth_callback_login`
    

**Parámetros de consulta (Query Parameters):**

```
| Clave               | Descripción                                   | Valor Ejemplo                  |
|---------------------|-----------------------------------------------|--------------------------------|
| authpt              | Identificador de tipo de autenticación.       | {{authpt}}                     |
| HKS                 | Valor de la sesión.                           | 2quq1jkacdnlqpfcr0nkdfos02     |
| cache               | Modo de caché.                                | refresh                        |
| code                | Código de autorización.                       | 592f60b307a58d57               |
| device_model        | Modelo del dispositivo.                       | {{device_model}}               |
| format              | Formato de la respuesta.                      | json                           |
| device_type         | Tipo de dispositivo.                          | {{device_type}}                |
| authpn              | Identificador de proveedor de autenticación.  | {{authpn}}                     |
| api_version         | Versión de la API.                            | v5.93                          |
| region              | Región del usuario.                           | brasil                         |
| device_category     | Categoría del dispositivo.                    | {{device_category}}            |
| device_manufacturer | Fabricante del dispositivo.                   | {{device_manufacturer}}        |

```

**Encabezados (Headers):**

```
| Clave        | Valor               | Estado    |
|--------------|---------------------|-----------|
| partition    | claromexhomolog     | Desactivado|

```

**Respuesta**: Vacía (sin contenido). ❌

----------

### **5. /user/hub/userinfo** 👤

-   **Descripción**: Este endpoint se utiliza para obtener la información de un usuario en la plataforma. 📋
    
-   **Método**: `GET` 🚀
    
-   **URL**: `{{SERVER_URL}}/services/user/hub/userinfo`
    

**Parámetros de consulta (Query Parameters):**

```
| Clave               | Descripción                                   | Valor Ejemplo               |
|---------------------|-----------------------------------------------|-----------------------------|
| authpn              | Identificador de proveedor de autenticación.  | amco                        |
| authpt              | Identificador de tipo de autenticación.       | 12e4i8l6a581a               |
| region              | Región del usuario.                           | argentina                   |
| api_version         | Versión de la API.                            | v5.93                       |
| customer_id         | ID del cliente.                               | userprueba2ar0017           |

```

**Encabezados (Headers):**

```
| Clave        | Valor               | Estado    |
|--------------|---------------------|-----------|
| partition    | clarobnetuat        | Activado  |

```

**Scripts:**

-   **Test**: Al recibir la respuesta, se extraen los valores de `token`, `user_hash` y `id_usuario`, y se almacenan como variables globales. 🗂
    

```javascript
const response = pm.response.json();
pm.globals.set("userToken", response.response.token);
pm.globals.set("userHash", response.response.user_hash);
pm.globals.set("userId", response.response.id_usuario);

```

**Respuesta**: Vacía (sin contenido). ❌

----------

### **6. /user/settermsandconditions** 📜

-   **Descripción**: Este endpoint se utiliza para aceptar los términos y condiciones del servicio. ✅📑
    
-   **Método**: `GET` 🚀
    
-   **URL**: `{{SERVER_URL}}/services/user/settermsandconditions`
    

**Parámetros de consulta (Query Parameters):**

```
| Clave               | Descripción                                   | Valor Ejemplo              |
|---------------------|-----------------------------------------------|----------------------------|
| terminos            | Indicador de aceptación de términos.         | 1                          |
| api_version         | Versión de la API.                            | v5.92                       |
| format              | Formato de la respuesta.                      | json                        |
| authpn              | Identificador de proveedor de autenticación.  | {{authpn}}                  |
| authpt              | Identificador de tipo de autenticación.       | {{authpt}}                  |
| device_category     | Categoría del dispositivo.                    | {{device_category}}         |
| device_type         | Tipo de dispositivo.                          | {{device_type}}             |
| device_model        | Modelo del dispositivo.                       | {{device_model}}            |
| device_manufacturer | Fabricante del dispositivo.                   | ZTE                         |
| region              | Región del usuario.                           | argentina                  |
| user_hash           | Hash del usuario.                             | {{userHash}}                |

```

**Encabezados (Headers):**

```
| Clave        | Valor               | Estado    |
|--------------|---------------------|-----------|
| partition    | clarobnetuat        | Activado  |
| Cookie       | PHPSESSID=62jkj64fcal6f40jg866h82ac1 | Activado |

```

**Respuesta**: Vacía (sin contenido). ❌

----------

### **7. /user/logout** 🚪

-   **Descripción**: Este endpoint cierra la sesión de un usuario. 👋
    
-   **Método**: `GET` 🚀
    
-   **URL**: `{{SERVER_URL}}/services/user/logout`
    

**Parámetros de consulta (Query Parameters):**

```
| Clave               | Descripción                                   | Valor Ejemplo               |
|---------------------|-----------------------------------------------|-----------------------------|
| authpt              | Identificador de tipo de autenticación.       | {{authpt}}                  |
| HKS                 | Valor de la sesión.                           | {{varHKS}}                  |
| device_model        | Modelo del dispositivo.                       | {{device_model}}            |
| device_id           | ID del dispositivo.                           | d7dc36d3-78fd-44d2-914f-d1546f0e75fa |
| user_id             | ID del usuario.                               | {{userId}}                  |
| device_so           | Sistema operativo del dispositivo.            | Android 12                 |
| device_type         | Tipo de dispositivo.                          | {{device_type}}             |
| authpn              | Identificador de proveedor de autenticación.  | {{authpn}}                  |
| api_version         | Versión de la API.                            | v5.93                       |
| region              | Región del usuario.                           | argentina                  |
| device_category     | Categoría del dispositivo.                    | {{device_category}}         |
| device_manufacturer | Fabricante del dispositivo.                   | {{device_manufacturer}}     |
| all_sessions        | Cerrar todas las sesiones.                    | true                        |

```

**Encabezados (Headers):**

```
| Clave        | Valor               | Estado    |
|--------------|---------------------|-----------|
| partition    | clarobnetuat        | Activado  |

```

**Respuesta**: Vacía (sin contenido). ❌
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyOTAzNjYwNzldfQ==
-->