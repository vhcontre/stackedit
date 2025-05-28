### Deshacer la contenerización del Frontend

- Para avanzar en nuestro proyecto, es imprescindible contar con un entorno de desarrollo adecuado. Este entorno nos permitirá realizar pruebas, desarrollar nuevas funcionalidades y realizar integraciones de manera eficiente y segura. Con el entorno de desarrollo bien configurado, podremos agilizar el proceso de desarrollo y garantizar el software que entregamos.

> Por favor, siga los pasos sugeridos para establecer el entorno de desarrollo de manera óptima.

1. Detener contenedor web-1 y ngnix-1 en docker. 

2. Modificar archivo .env.local dentro de app/ con el contenido:

> MONGO_URI=mongodb://localhost:27017/registroconstructores 

3. Modificar package.json de app/:

` "scripts": {
"dev": "next dev", 
`

4. En terminal hacer build del rnc registroconstructores/app/:

> npm install

5. En terminal hacer build del rnc registroconstructores/app/:

> npm run build

6. En terminal ejecutar app rnc registroconstructores/app/:

> npm run dev

7. Ingresar al sistema por http://localhost:3000/

  

## Importante

  

### Levantar contenedor docker IPFS

### Levantar contenedor docker MongoDB
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NDk2NDg1MTRdfQ==
-->