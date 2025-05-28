##  ProveedoresController : BaseController
Esta es la documentación de las APIs del sistema Contratar que utilizan principalmente Sonda.Framework.Website.Web.

## ObtenerDocumentosDelProveedor
Obtiene los detalles de los datos factor multiplicador proveedor

**URL**  :  `/API/Proveedores/ObtenerDocumentosDelProveedor/:id/`

**CURL**: `curl -X GET http://host/API/Proveedores/ObtenerDocumentosDelProveedor?id=12481`

**Parámetros de URL** : `id=[long]` Id del proveedor

**Método de la solicitud**  :  `GET`

**Requiere autenticación**  : Si

**Permisos requeridos**  : Ninguno
 
## Respuesta exitosa

**Condición**  : La credencial debe existir y la misma tiene los permisos necesarios.

**Código de estado**  :  `200 OK`

**Contenido** : Servicios.DataContracts.Proveedor.`DatosParcialesOutputDataContract<T>`
T: Servicios.DataContracts.Proveedor.DocumentoRUPSADEDataContract
    
    {
	"Data": [{
		"FechaVencimiento": null,
		"Descripcion": "Balance",
		"NumeroGEDO": "IF-2019-71771350-APN-DNCOPRCYFC#JGM",
		"Id": 574793
	}, {
		"FechaVencimiento": null,
		"Descripcion": "Balance",
		"NumeroGEDO": "IF-2019-64339003-APN-DNCOPRCYFC#JGM",
		"Id": 574795
	}, {
		"FechaVencimiento": null,
		"Descripcion": "Ultima acta de designación de autoridades y distribución de cargos",
		"NumeroGEDO": "IF-2019-64333538-APN-DNCOPRCYFC#JGM",
		"Id": 574799
	}, {
		"FechaVencimiento": null,
		"Descripcion": "Acta Administrador Legitimado",
		"NumeroGEDO": "IF-2019-71078122-APN-DNCOPRCYFC#JGM",
		"Id": 574801
	}, {
		"FechaVencimiento": "2020-06-30T00:00:00",
		"Descripcion": "Balance Contable",
		"NumeroGEDO": "-",
		"Id": 0
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
eyJoaXN0b3J5IjpbMzgyNjI1MjEzXX0=
-->