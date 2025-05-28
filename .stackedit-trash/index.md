# Descripción de Endpoints

## PGS

### `GET /services/payway/confirm`
- **Descripción**: Confirma una compra utilizando un token cifrado que contiene información de la compra.
- **Parámetros**:
  - `buylink`: Token cifrado con información de la compra.
  - `payway`: Método de pago seleccionado.
  - `region`: Región del usuario.
  - `device_category`, `device_manufacturer`, `device_model`, `device_type`: Información del dispositivo.
  - `HKS`: Token de seguridad.
  - `numberField`: Número de teléfono del usuario.
  - `authpn`, `authpt`: Credenciales de autenticación.
  - `api_version`: Versión de la API.

---

### `GET /services/payway/linealchannels`
- **Descripción**: Obtiene información sobre los canales lineales disponibles.
- **Parámetros**:
  - `device_manufacturer`, `device_category`, `device_model`, `device_type`: Información del dispositivo.
  - `region`: Región del usuario.
  - `HKS`: Token de seguridad.
  - `user_id`: ID del usuario.
  - `format`: Formato de la respuesta (JSON).
  - `authpn`, `authpt`: Credenciales de autenticación.
  - `api_version`: Versión de la API.

---

### `GET /services/payway/workflowstart`
- **Descripción**: Inicia un flujo de trabajo para realizar un pago.
- **Parámetros**:
  - `object_type`: Tipo de objeto.
  - `offer_id`, `group_id`: Identificadores de la oferta y grupo.
  - `device_category`, `device_manufacturer`, `device_model`, `device_type`: Información del dispositivo.
  - `HKS`: Token de seguridad.
  - `region`: Región del usuario.
  - `user_id`: ID del usuario.
  - `authpn`, `authpt`: Credenciales de autenticación.
  - `api_version`: Versión de la API.
  - `format`: Formato de la respuesta (JSON).

---

### `GET /services/payway/purchasebuttoninfo`
- **Descripción**: Obtiene información sobre el botón de compra.
- **Parámetros**:
  - `device_id`, `device_category`, `device_model`, `device_type`, `device_so`, `device_manufacturer`: Información del dispositivo.
  - `authpn`, `authpt`: Credenciales de autenticación.
  - `api_version`: Versión de la API.
  - `region`: Región del usuario.
  - `HKS`: Token de seguridad.
  - `user_id`: ID del usuario.
  - `group_id`: ID del grupo.

---

### `GET /services/payway/desencripta`
- **Descripción**: Desencripta un token cifrado.
- **Parámetros**:
  - `payway`: Método de pago.
  - `region`: Región del usuario.
  - `device_category`, `device_manufacturer`, `device_model`, `device_type`: Información del dispositivo.
  - `HKS`: Token de seguridad.
  - `api_version`: Versión de la API.
  - `authpn`, `authpt`: Credenciales de autenticación.
  - `format`: Formato de la respuesta.

---

### `GET /services/payway/planselector`
- **Descripción**: Selecciona un plan de pago.
- **Parámetros**:
  - `user_token`: Token del usuario.
  - `region`: Región del usuario.
  - `authpn`, `authpt`: Credenciales de autenticación.
  - `device_category`, `device_manufacturer`, `device_model`, `device_type`: Información del dispositivo.
  - `api_version`: Versión de la API.
  - `object_type`: Tipo de objeto.

---

## USR

### `GET /likes/v1/{id}/like`
- **Descripción**: Obtiene el estado de "like" de un contenido.
- **Parámetros**:
  - `authpn`, `authpt`: Credenciales de autenticación.
  - `device_category`, `device_manufacturer`, `device_type`, `device_model`: Información del dispositivo.
  - `api_version`: Versión de la API.
  - `region`: Región del usuario.
  - `user_id`: ID del usuario.

---

### `POST /likes/v1/{id}/like`
- **Descripción**: Marca un contenido como "like".
- **Cuerpo**:
  - **Parámetros**: Igual que el endpoint anterior.

---

### `DELETE /likes/v1/{id}/like`
- **Descripción**: Elimina el "like" de un contenido.
- **Parámetros**: Igual que el endpoint anterior.

---

### `GET /services/user/login`
- **Descripción**: Inicia sesión para un usuario.
- **Parámetros**:
  - `includpaywayprofile`: Incluir perfil de pago.
  - `device_manufacturer`, `device_category`, `device_type`, `device_model`: Información del dispositivo.
  - `region`: Región del usuario.
  - `userhash`: Hash del usuario.
  - `HKS`: Token de seguridad.
  - `authpn`, `authpt`: Credenciales de autenticación.
  - `api_version`: Versión de la API.

---

### `GET /services/user/setusertype`
- **Descripción**: Establece el tipo de usuario.
- **Parámetros**:
  - `authpn`, `authpt`: Credenciales de autenticación.
  - `user_id`: ID del usuario.

---

### `GET /services/user/authdevice`
- **Descripción**: Autentica un dispositivo.
- **Parámetros**:
  - `authpn`, `authpt`: Credenciales de autenticación.
  - `device_category`, `device_type`, `device_model`, `device_manufacturer`: Información del dispositivo.
  - `HKS`: Token de seguridad.
  - `api_version`: Versión de la API.
  - `region`: Región del usuario.
  - `device_so`: Sistema operativo del dispositivo.
  - `serial_id`: ID del dispositivo.
  - `format`: Formato de la respuesta.

---

### `GET /services/user/getbookmark`
- **Descripción**: Obtiene los marcadores del usuario.
- **Parámetros**:
  - `api_version`: Versión de la API.
  - `format`: Formato de la respuesta.
  - `region`: Región del usuario.
  - `authpn`, `authpt`: Credenciales de autenticación.
  - `device_type`, `device_model`, `device_category`, `device_manufacturer`: Información del dispositivo.
  - `user_hash`: Hash del usuario.
  - `lasttouch`: Última interacción.

---

## PLY

### `POST /concurrent-streaming/{USER_ID}`
- **Descripción**: Crea un nuevo stream concurrente.
- **Cuerpo**:
  
---

### `GET /concurrent-streaming/{USER_ID}`
- **Descripción**: Lista los streams concurrentes del usuario.

---

### `DELETE /concurrent-streaming/{USER_ID}/{STREAM_UUID}`
- **Descripción**: Elimina un stream concurrente.

---

### `GET /concurrent-streaming/is_alive`
- **Descripción**: Verifica el estado del servicio.

---

### `GET /services/css/list`
- **Descripción**: Lista los servicios CSS disponibles.
- **Parámetros**:
  - `device_manufacturer`, `device_category`, `device_model`, `device_type`: Información del dispositivo.
  - `authpn`, `authpt`: Credenciales de autenticación.
  - `user_id`: ID del usuario.

---

## Recording

### `GET /services/recordings/data`
- **Descripción**: Obtiene datos de grabaciones.
- **Parámetros**:
  - `api_version`, `authpn`, `authpt`: Credenciales y versión de la API.
  - `format`: Formato de la respuesta.
  - `region`: Región del usuario.
  - `device_id`, `device_category`, `device_model`, `device_type`, `device_manufacturer`: Información del dispositivo.
  - `user_token`: Token del usuario.
  - `record_id`: ID de la grabación.

---

### `GET /services/recordings/series/add`
- **Descripción**: Agrega una serie a las grabaciones.
- **Parámetros**: Similar al endpoint anterior, con `channel_id` y `event_id`.

---

### `GET /services/recordings/series/list`
- **Descripción**: Lista las series grabadas.
- **Parámetros**: Similar al endpoint anterior, con `series_id`.

---

### `GET /services/recordings/delete`
- **Descripción**: Elimina una grabación.
- **Parámetros**: Similar al endpoint anterior, con `record_id` y `programme_id`.

---

### `GET /services/recordings/list`
- **Descripción**: Lista las grabaciones disponibles.
- **Parámetros**: Similar al endpoint anterior.

---

## Device

### `GET /services/device/list`
- **Descripción**: Lista los dispositivos registrados.
- **Parámetros**:
  - `api_version`, `region`, `HKS`, `user_hash`: Información de autenticación.
  - `css`: Indica si se incluye CSS.
  - `authpt`, `authpn`: Credenciales de autenticación.
  - `format`: Formato de la respuesta.

---

### `GET /services/device/modify`
- **Descripción**: Modifica la información de un dispositivo.
- **Parámetros**: Similar al endpoint anterior, con `device_id` y `device_name`.

# CMS

## `GET /services/content/data`
- **Descripción**: Obtiene información detallada sobre un contenido específico.
- **Parámetros**:
  - `device_id`: Identificador del dispositivo (por ejemplo, "web").
  - `device_category`: Categoría del dispositivo (por ejemplo, "web").
  - `device_model`: Modelo del dispositivo (por ejemplo, "web").
  - `device_type`: Tipo de dispositivo (por ejemplo, "web").
  - `device_so`: Sistema operativo del dispositivo (por ejemplo, "Chrome").
  - `format`: Formato de la respuesta (por ejemplo, "json").
  - `device_manufacturer`: Fabricante del dispositivo (por ejemplo, "generic").
  - `authpn`: Credencial de autenticación del cliente (por ejemplo, "webclient").
  - `authpt`: Credencial de autenticación del token (por ejemplo, "tfg1h3j4k6fd7").
  - `api_version`: Versión de la API (por ejemplo, "v5.92").
  - `region`: Región del usuario (por ejemplo, "panama").
  - `HKS`: Token de seguridad.
  - `user_id`: Identificador del usuario.
  - `group_id`: Identificador del grupo.

---



<!--stackedit_data:
eyJoaXN0b3J5IjpbNTQ0NjE5OTU2XX0=
-->