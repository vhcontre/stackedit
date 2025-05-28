##  ProveedoresController : BaseController
Esta es la documentación de las APIs del sistema Contratar que utilizan principalmente Sonda.Framework.Website.Web.

## ObtenerDatosFactorMultiplicadorProveedor
Obtiene los detalles de los datos factor multiplicador proveedor

**URL**  :  `/API/Proveedores/ObtenerDatosFactorMultiplicadorProveedor/:id/`

**CURL**: `curl -X GET http://host/API/Proveedores/ObtenerDatosFactorMultiplicadorProveedor?id=12481`

**Parámetros de URL** : `id=[long]` Id del proveedor

**Método de la solicitud**  :  `GET`

**Requiere autenticación**  : Si

**Permisos requeridos**  : Ninguno
 
## Respuesta exitosa

**Condición**  : La credencial debe existir y la misma tiene los permisos necesarios.

**Código de estado**  :  `200 OK`

**Contenido** : Servicios.DataContracts.Proveedor.`DatosParcialesOutputDataContract<T>`
    
    {
	"Data": [{
		"IndiceSolvencia": 615,
		"FactorIndiceSolvencia": 1.0,
		"IndiceLiquidez": 382,
		"FactorIndiceLiquidez": 0.35,
		"IndiceEndeudamiento": 0.8609,
		"FactorIndiceEndeudamiento": 0.65,
		"IndiceCapitalPropio": 0.5374,
		"FactorIndiceCapitalPropio": 0.65,
		"ResultadoIGJ": 1.4,
		"Resultado": 4.45,
		"Id": 5317
	}],
	"EsVisible": true,
	"Id": 0}


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
eyJoaXN0b3J5IjpbMTE1NDY5NDE2N119
-->