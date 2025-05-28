## **Documentación de Endpoints de Claro Video API 📱**

Se detallan los **endpoints** disponibles para interactuar con la API de **CMS**. Cada endpoint está descrito con su propósito, parámetros y ejemplo de uso.

----------

### 1. **Endpoint: /services/content/data**

**Descripción:**  
Este endpoint se utiliza para recuperar datos de contenido desde el servicio de Claro Video, solicitando información específicamente para un dispositivo web y un usuario identificado. 📊

**Método:** `GET`

#### **Parámetros de consulta:**

-   **device_id**: Identificador del dispositivo (valor: `web`)
    
-   **device_category**: Categoría del dispositivo (valor: `web`)
    
-   **device_model**: Modelo del dispositivo (valor: `web`)
    
-   **device_type**: Tipo de dispositivo (valor: `web`)
    
-   **device_so**: Sistema operativo del dispositivo (valor: `Chrome`)
    
-   **format**: Formato de la respuesta (valor: `json`)
    
-   **device_manufacturer**: Fabricante del dispositivo (valor: `generic`)
    
-   **authpn**: Autorización del cliente (valor: `webclient`)
    
-   **authpt**: Token de autorización (valor: `tfg1h3j4k6fd7`)
    
-   **api_version**: Versión de la API (valor: `v5.92`)
    
-   **region**: Región en la que se solicita la información (valor: `panama`)
    
-   **HKS**: Clave de seguridad del cliente (valor: `web6009881e38690`)
    
-   **user_id**: Identificador del usuario (valor: `51301700`)
    
-   **group_id**: Identificador del grupo de usuario (valor: `843018`)
    

#### **Respuesta esperada:**

Un objeto JSON que contiene los datos relacionados con el contenido para el usuario y dispositivo especificados. 📝

----------

### 2. **Endpoint: /services/epg/menu**

**Descripción:**  
Este endpoint devuelve el menú de la Guía Electrónica de Programación (EPG) de Claro Video para un dispositivo STB (Set Top Box) en Argentina. 🇦🇷📺

**Método:** `GET`

#### **Parámetros de consulta:**

-   **HKS**: Clave de seguridad del cliente (valor: `BI1066042030422360219bfe21b41`)
    
-   **api_version**: Versión de la API (valor: `v5.91`)
    
-   **authpn**: Plataforma de autenticación (valor: `amco`)
    
-   **authpt**: Token de autenticación (valor: `12e4i8l6a581a`)
    
-   **device_category**: Categoría del dispositivo (valor: `stb`)
    
-   **device_id**: Identificador del dispositivo (valor: `BI10660420304223`)
    
-   **device_manufacturer**: Fabricante del dispositivo (valor: `kaonmedia`)
    
-   **device_model**: Modelo del dispositivo (valor: `sc7210`)
    
-   **device_name**: Nombre del dispositivo (valor: `Hi3798MV100`)
    
-   **device_so**: Sistema operativo del dispositivo (valor: `Android%204.4.2`)
    
-   **device_type**: Tipo de dispositivo (valor: `ptv`)
    
-   **format**: Formato de la respuesta (valor: `json`)
    
-   **region**: Región (valor: `argentina`)
    
-   **user_id**: Identificador del usuario (valor: `50619746`)
    

#### **Respuesta esperada:**

Un objeto JSON que contiene el menú de la EPG correspondiente para la región y dispositivo especificado. 🗓️

----------

### 3. **Endpoint: /services/cms/leveluser**

**Descripción:**  
Este endpoint obtiene el nivel de usuario en el CMS (Content Management System) para un usuario en un dispositivo STB (Set Top Box) de Roku en México. 🇲🇽

**Método:** `GET`

#### **Parámetros de consulta:**

-   **authpn**: Plataforma de autenticación (valor: `roku`)
    
-   **node**: Nodo del CMS (valor: `homeuser`)
    
-   **device_category**: Categoría del dispositivo (valor: `stb`)
    
-   **device_manufacturer**: Fabricante del dispositivo (valor: `roku`)
    
-   **user_id**: Identificador del usuario (valor: `12952303`)
    
-   **authpt**: Token de autenticación (valor: `IdbIIWeFzYdy`)
    
-   **region**: Región (valor: `mexico`)
    
-   **device_model**: Modelo del dispositivo (valor: `generic`)
    
-   **device_type**: Tipo de dispositivo (valor: `generic`)
    
-   **format**: Formato de la respuesta (valor: `json`)
    
-   **api_version**: Versión de la API (valor: `v5.86`)
    
-   **HKS**: Clave de seguridad del cliente (valor: `web6022e4fa98991`)
    
-   **user_hash**: Hash del usuario (valor: `MjY0MzQ3MTJ8MTYxMjg5OTU3OHwyYjg4NWVlMDQ4MDI0ODBkZGZiOTAxYWI0YmNkMWFiYmMyMjkzZDM4NTc4NzM5MzhhOQ==`)
    

#### **Respuesta esperada:**

Un objeto JSON con la información del nivel de usuario en el CMS. 🔑

----------

### 4. **Endpoint: /services/epg/channel**

**Descripción:**  
Este endpoint obtiene los canales de la Guía Electrónica de Programación (EPG) para un dispositivo web en México. 🇲🇽📡

**Método:** `GET`

#### **Parámetros de consulta:**

-   **HKS**: Clave de seguridad del cliente (valor: `c5bb514e2112a0ae7d107c5384b30a78`)
    
-   **api_version**: Versión de la API (valor: `v5.92`)
    
-   **authpn**: Plataforma de autenticación (valor: `html5player`)
    
-   **authpt**: Token de autenticación (valor: `ad5565dfgsftr`)
    
-   **dateTimeShift**: Si se debe aplicar un desplazamiento de tiempo (valor: `false`)
    
-   **date_from**: Fecha de inicio para los canales (valor: `20210720000000`)
    
-   **date_to**: Fecha de fin para los canales (valor: `20210721000000`)
    
-   **device_category**: Categoría del dispositivo (valor: `web`)
    
-   **device_id**: Identificador del dispositivo (valor: `web`)
    
-   **device_manufacturer**: Fabricante del dispositivo (valor: `windows`)
    
-   **device_model**: Modelo del dispositivo (valor: `html5`)
    
-   **device_so**: Sistema operativo del dispositivo (valor: `Chrome`)
    
-   **device_type**: Tipo de dispositivo (valor: `html5`)
    
-   **epg_version**: Versión de la EPG (valor: `41279`)
    
-   **format**: Formato de la respuesta (valor: `json`)
    
-   **quantity**: Cantidad de canales (valor: `200`)
    
-   **region**: Región (valor: `mexico`)
    

#### **Respuesta esperada:**

Un objeto JSON que contiene los detalles de los canales para las fechas especificadas. 📅

----------
### 5. **Endpoint: /plans/v1/offers**

**Descripción:**  
Este endpoint recupera las ofertas de planes de suscripción disponibles para un usuario en Argentina. 💳

**Método:** `GET`

#### **Parámetros de consulta:**

-   **user_token**: Token de usuario (valor: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9...`)
    
-   **region**: Región (valor: `argentina`)
    

#### **Respuesta esperada:**

Un objeto JSON que contiene las ofertas de planes disponibles para el usuario, basado en su token y región. 🏷️

----------

### 6. **Endpoint: /services/content/filters**

**Descripción:**  
Este endpoint devuelve los filtros disponibles para el contenido en la plataforma Claro Video en Argentina. 🎥

**Método:** `GET`

#### **Parámetros de consulta:**

-   **device_category**: Categoría del dispositivo (valor: `web`)
    
-   **device_model**: Modelo del dispositivo (valor: `web`)
    
-   **device_type**: Tipo de dispositivo (valor: `web`)
    
-   **format**: Formato de la respuesta (valor: `json`)
    
-   **device_manufacturer**: Fabricante del dispositivo (valor: `generic`)
    
-   **authpn**: Plataforma de autenticación (valor: `webclient`)
    
-   **authpt**: Token de autenticación (valor: `tfg1h3j4k6fd7`)
    
-   **api_version**: Versión de la API (valor: `v5.93`)
    
-   **region**: Región (valor: `argentina`)
    
-   **group_id**: Identificador del grupo (valor: `1151385`)
    

#### **Respuesta esperada:**

Un objeto JSON con los filtros disponibles para el contenido. 🎬

----------

### 7. **Endpoint: /services/cms/v3/superhighlight**

**Descripción:**  
Este endpoint obtiene la información relacionada con los super destacados de la plataforma Claro Video en Brasil. 🇧🇷✨

**Método:** `GET`

#### **Parámetros de consulta:**

-   **superhighlight**: Identificador del super destacado (valor: `prueba-preview-prod`)
    
-   **type**: Tipo de contenido (valor: `bnet`)
    
-   **region**: Región (valor: `brasil`)
    
-   **format**: Formato de la respuesta (valor: `json`)
    
-   **device_category**: Categoría del dispositivo (valor: `web`)
    
-   **device_model**: Modelo del dispositivo (valor: `web`)
    
-   **device_type**: Tipo de dispositivo (valor: `web`)
    
-   **api_version**: Versión de la API (valor: `v5.93`)
    
-   **authpn**: Plataforma de autenticación (valor: `webclient`)
    

#### **Respuesta esperada:**

Un objeto JSON con los detalles de los super destacados disponibles. 🌟

----------

### 8. **Endpoint: /content/v1/list**

**Descripción:**  
Este endpoint se utiliza para recuperar una lista de contenidos en la plataforma Claro Video, permitiendo filtrar y ordenar el contenido según diversos parámetros. 📋

**Método:** `GET`

#### **Parámetros de consulta:**

-   **category**: Categoría del contenido (valor: `movies`, `series`, `tvshows`, etc.)
    
-   **page**: Número de página para la paginación.
    
-   **limit**: Límite de elementos por página.
    
-   **order_by**: Criterio para ordenar los contenidos (puede ser por fecha, popularidad, etc.)
    
-   **region**: Región para filtrar el contenido disponible en la plataforma (valor: `panama`, `argentina`, `brasil`, etc.)
    
-   **device_id**: Identificador del dispositivo que realiza la solicitud (valor: `web`, `smarttv`, etc.)
    
-   **device_category**: Categoría del dispositivo (valor: `web`, `mobile`, `stb`, etc.)
    
-   **device_so**: Sistema operativo del dispositivo (valor: `Android`, `iOS`, `Windows`, etc.)
    
-   **api_version**: Versión de la API (valor: `v1`)
    
-   **format**: Formato de la respuesta (valor: `json`)
    

#### **Respuesta esperada:**

Un objeto JSON que contiene una lista de contenidos que corresponden a los filtros aplicados, con información adicional como títulos, descripciones, imágenes, y otras características del contenido. 🎞️

----------

### 9. **Endpoint: /content/v1/data**

**Descripción:**  
Este endpoint permite obtener información detallada sobre un contenido específico en la plataforma Claro Video, como su descripción, disponibilidad, calidad, entre otros. 🎬

**Método:** `GET`

#### **Parámetros de consulta:**

-   **content_id**: Identificador único del contenido (puede ser una película, serie, etc.)
    
-   **region**: Región para la que se solicita el contenido (valor: `panama`, `argentina`, `brasil`, etc.)
    
-   **device_id**: Identificador del dispositivo (por ejemplo: `web`, `smarttv`).
    
-   **device_category**: Categoría del dispositivo (por ejemplo: `web`, `mobile`, `stb`).
    
-   **device_so**: Sistema operativo del dispositivo (valor: `Android`, `iOS`, `Windows`, etc.)
    
-   **format**: Formato de la respuesta (valor: `json`).
    
-   **api_version**: Versión de la API (valor: `v1`).
    

#### **Respuesta esperada:**

Un objeto JSON que contiene la información detallada del contenido, como su título, descripción, año de estreno, actores, directores, categorías, disponibilidad para la región, etc. 📚


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3Mjg2NDEyOV19
-->