### Configurar el entorno de desarrollo para el Registro Nacional de Constructores

- Para avanzar en nuestro proyecto, es imprescindible contar con un entorno de desarrollo adecuado. Este entorno nos permitirá realizar pruebas, desarrollar nuevas funcionalidades y realizar integraciones de manera eficiente y segura. Con el entorno de desarrollo bien configurado, podremos agilizar el proceso de desarrollo y garantizar el software que entregamos.

> Por favor, siga los pasos sugeridos para establecer el entorno de desarrollo de manera óptima.

Requisitos en Windows:

Visual Studio Code

Docker Desktop

Node 14

  

Repositorio Git:

https://github.com/RegistroConstructoresONC/registroconstructores.git

Pasos:

1. Descargar del repositorio de la rama 1.26 los archivos:

`.ipfs_config` y `docker-compose.yml`

2. Clonar rama main a una carpeta local a elección

3. Copiar y pegar los archivos .ipfs_config y docker-compose.yml a la raiz de la carpeta del proyecto clonado.

4. Crear archivo .env.local dentro de registroconstructores/app/ con el contenido:

```

MONGO_URI=mongodb://mongo:27017/registroconstructores

#SESSION_SECRET=liie%dWD&r9I

SESSION_SECRET=gx6HTaeBcSzxx9Iu

MODO=ONLINE

#MODO=MANTENIMIENTO

OPENID_AUTH=https://tst.autenticar.gob.ar/auth/realms/rnc-afip/protocol/openid-connect/auth?client_id=rnc&scope=openid&response_type=token&response_mode=fragment

OPENID_USERDATA=https://tst.autenticar.gob.ar/auth/realms/rnc-afip/protocol/openid-connect/userinfo

OPENID_LOGOUT=https://tst.autenticar.gob.ar/auth/realms/rnc-afip/protocol/openid-connect/logout

  

URL_CONTRATAR=https://tst.contratar.gob.ar

CONTRATAR_KEY=774f44abda2246458b019de23cc9acaa

CONTRATAR_AUTH_MODE=ONLINE

  

IPFS_NODE_APIPATH=api/v0

IPFS_NODE_PROTOCOL=http

IPFS_NODE_HOST=ipfs

IPFS_NODE_PORT=5001

```

5. Ejecutar en carpeta raiz de proyecto:

> docker-compose build

6. Ejecutar en carpeta raiz:

> docker-compose up

  

7. Ingreso al sistema en: http://localhost:8080/

  

NOTA: requiere loguear por link con token

  

*Si bien el sistema quedó funcionando, falta cargar los datos a la db mongo local, instrucciones a continuación*

  

### Popular DB en contenedor docker:

1. descomprimir dump_rnc.7z y copiar carpeta dump_rnc al contenedor mongo-1 de docker por interfaz o bien por terminal:

```

docker cp dump_rnc <id-contenedor-mogodb>:dump_rnc

```

  

2. Restaurar DB al mongodb del contenedor

  

Opcion 1: desde terminal interna del contenedor mongo-1 en docker:

```

mongorestore --db registroconstructores --drop dump_rnc

```

  

Opcion 2: restautar db desde terminal de windows:

```

docker exec -it <id-contenedor-mogodb> mongorestore --db registroconstructores --drop dump_rnc

```

  

*--drop es opcional, vaciará la db existente.*

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU4Mjc2MTg4MV19
-->