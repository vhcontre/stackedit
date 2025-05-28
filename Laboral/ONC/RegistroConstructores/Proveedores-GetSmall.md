##  ProveedoresController : BaseController
Esta es la documentación de las APIs del sistema Contratar que utilizan principalmente Sonda.Framework.Website.Web.

## GetSmall
Obtiene los detalles del proveedor con su información básica.

**URL**  :  `/API/Proveedores/GetSmall/:id/`

**CURL**: `curl -X GET http://host/API/Proveedores/GetSmall?id=12481`

**Parámetros de URL** : `id=[long]` Id del proveedor

**Método de la solicitud**  :  `GET`

**Requiere autenticación**  : Si

**Permisos requeridos**  : Ninguno
 
## Respuesta exitosa

**Condición**  : La credencial debe existir y la misma tiene los permisos necesarios.

**Código de estado**  :  `200 OK`

**Contenido** : Servicios.DataContracts.`ProveedorSmallOutputDataContract`
    
    {
	"RazonSocial": "EMPRESA S.R.L.",
	"CUIT": "30600043000",
	"TipoProveedor": "Sociedad de responsabilidad limitada",
	"TiposEmpresa": [3],
	"EstadoConstructor": "Desactualizado por documentos...",
	"EstadoPreInscripcion": 1,
	"EstadoInformacionBasica": 1,
	"EstadoBalances": 1,
	"EstadoObra": 1,
	"CapacidadContratacion": 2288.14,
	"CapacidadEjecucion": 2847.71,
	"PorcentajesPorEspecialidades": [{
		"DescripcionEspecialidad": "Obras de Arquitectura",
		"Porcentaje": 81.47,
		"Id": 10793
	}, {
		"DescripcionEspecialidad": "Especialidad",
		"Porcentaje": 20.10,
		"Id": 10794
	}],
	"RestriccionVisbilidad": false,
	"DeclaraObras": true,
	"FueInscripto": true,
	"Id": 12481 }


## Respuestas de error

**Condición** : si el proveedor no existe con el parámetro `id`.

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
eyJoaXN0b3J5IjpbLTMwNTE0MzQ4MV19
-->