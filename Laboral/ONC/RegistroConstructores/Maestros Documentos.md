##  Parametros: BaseController
Esta es la documentación de las APIs del sistema Contratar que utilizan principalmente Sonda.Framework.Website.Web.

## ObtenerTiposDocumentos
Obtiene los tipos de documentos.

**URL**  :  `/API/Parametros/ObtenerTiposDocumentos`

**CURL**: `curl -X GET http://host/API/Parametros/ObtenerTiposDocumentos`

**Parámetros de URL** : `` 

**Método de la solicitud**  :  `GET`

**Requiere autenticación**  : Si

**Permisos requeridos**  : Ninguno
 
## Respuesta exitosa

**Condición**  : La credencial debe existir y la misma tiene los permisos necesarios.

**Código de estado**  :  `200 OK`

**Contenido** : Servicios.DataContracts.Base.`EnumOutputDataContract`
   
	 [{
		"Id": 5,
		"Descripcion": "CI"
	}, {
		"Id": 1,
		"Descripcion": "DNI"
	}, {
		"Id": 2,
		"Descripcion": "LC"
	}, {
		"Id": 3,
		"Descripcion": "LE"
	}, {
		"Id": 4,
		"Descripcion": "Pasaporte"
	}]


## Respuestas de error

**Condición** : No existe.

**Código** :`404 NOT FOUND`

**Contenido** : `Se aclara que retorna toda una respuesta HMTL completa.`

	{
	   Se ha producido un problema al intentar mostrar la página.
	   Código: 000####
	}

### O

**Condición** : si el usuario autorizado no tiene los permisos necesarios.

**Código** :`403 FORBIDDEN`

**Contenido** : `Se aclara que retorna toda una respuesta HMTL completa.`

	{
	   Se ha producido un problema al intentar mostrar la página.
	   Código: 000####	   
	}

## Notas
* Con el código de error que muestra la página, puede obtener el detalle de este desde la tabla [ErrorSeac]
>SELECT [Mensaje] FROM [ErrorSeac] WHERE IdError = @Codigo
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTM5NDU5OTQ3XX0=
-->