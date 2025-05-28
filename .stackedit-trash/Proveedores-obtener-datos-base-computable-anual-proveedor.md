##  ProveedoresController : BaseController
Esta es la documentación de las APIs del sistema Contratar que utilizan principalmente Sonda.Framework.Website.Web.

## ObtenerDatosBaseComputableAnualProveedor
Obtiene los detalles de los Datos Base Computable Anual Proveedor

**URL**  :  `/API/Proveedores/ObtenerDatosBaseComputableAnualProveedor/:id/`

**CURL**: `curl -X GET http://host/API/Proveedores/ObtenerDatosBaseComputableAnualProveedor?id=12481`

**Parámetros de URL** : `id=[long]` Id del proveedor

**Método de la solicitud**  :  `GET`

**Requiere autenticación**  : Si

**Permisos requeridos**  : Ninguno
 
## Respuesta exitosa

**Condición**  : La credencial debe existir y la misma tiene los permisos necesarios.

**Código de estado**  :  `200 OK`

**Contenido** : Servicios.DataContracts.Proveedor.`DatosParcialesOutputDataContract<T>`
T: Servicios.DataContracts.Proveedor.DatosBaseComputableAnualOutputDataContract

    {
	"Data": [{
		"MontoHomogenizado": 1983.3782,
		"FechaInicioEjercicio": "2014-01-01T00:00:00",
		"FechaFinEjercicio": "2014-12-31T00:00:00",
		"Id": 17985
	}, {
		"MontoHomogenizado": 1983.2208,
		"FechaInicioEjercicio": "2015-01-01T00:00:00",
		"FechaFinEjercicio": "2015-12-31T00:00:00",
		"Id": 17986
	}, {
		"MontoHomogenizado": 1983.7699,
		"FechaInicioEjercicio": "2016-01-01T00:00:00",
		"FechaFinEjercicio": "2016-12-31T00:00:00",
		"Id": 17987
	}, {
		"MontoHomogenizado": 1983.8256,
		"FechaInicioEjercicio": "2011-01-01T00:00:00",
		"FechaFinEjercicio": "2011-12-31T00:00:00",
		"Id": 17988
	}, {
		"MontoHomogenizado": 1983.9125,
		"FechaInicioEjercicio": "2010-01-01T00:00:00",
		"FechaFinEjercicio": "2010-12-31T00:00:00",
		"Id": 17993
	}],
	"EsVisible": true,
	"Id": 0 }


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
eyJoaXN0b3J5IjpbMTM0NDE5MzE1Nl19
-->