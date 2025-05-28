#  Proveedores

Esta es la documentación de las APIs del sistema Contratar que se utiliza principalmente desde Sonda.Framework.Website.Web.

## DescargarConstanciaDeInscripcion
Genera reporte PDF a partir de un identificador de proveedor y Fecha emisión.

**URL**  :  `/API/Proveedores/DescargarConstanciaDeInscripcion/:id/:fecha`

**CURL**: 
`curl -X GET http://host/API/Proveedores/DescargarConstanciaDeInscripcion?id=12481&fecha=2021-02-25`

**Parámetros de URL** : 
`id=[long]` Id del proveedor
`fecha=[DateTime]` Consulta de fecha emisión histórica

**Método de la solicitud**  :  `GET`

**Requiere autenticación**  : Si

**Permisos requeridos**  : Ninguno
 
## Respuesta exitosa

**Condición**  : La credencial debe existir y la misma debe tener los permisos necesarios.

**Código de estado**  :  `200 OK`

**Contenido** : Servicios.DataContracts.Proveedor.`ConstanciaInscripcionDataContract`

**Content-Type**: application/pdf 
    Retorna un reporte **PDF**	

## Respuestas de error

**Condición** : si el fecha no es valida o no es nula en el parámetro `fecha`.

**Código** :`404 NOT FOUND`

**Contenido** : `Se aclara que retorna toda una respuesta HMTL completa.`

	{
	   Se ha producido un problema al intentar mostrar la página.
	   Código: 000####
	   SELECT [Mensaje] FROM [ErrorSeac] WHERE IdError = @Codigo
	}

### O
**Condición** : si el proveedor no existe con el parámetro `id`.

**Código** :`404 NOT FOUND`

**Contenido** : `Se aclara que retorna toda una respuesta HMTL completa.`

	{
	   Se ha producido un problema al intentar mostrar la página.
	   Código: 000####
	   SELECT [Mensaje] FROM [ErrorSeac] WHERE IdError = @Codigo
	}

### O

**Condición** : si el usuario autorizado no tiene los permisos necesarios.

**Código** :`403 FORBIDDEN`

**Contenido** : `Se aclara que retorna toda una respuesta HMTL completa.`

	{
	   Se ha producido un problema al intentar mostrar la página.
	   Código: 000####
	   SELECT [Mensaje] FROM [ErrorSeac] WHERE IdError = @Codigo
	}

## Notas
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU4ODY3NzA0MV19
-->