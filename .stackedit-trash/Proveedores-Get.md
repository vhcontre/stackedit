##  ProveedoresController : BaseController
Esta es la documentación de las APIs del sistema Contratar que utilizan principalmente Sonda.Framework.Website.Web.

## Get
Obtiene los datos del proveedor para la Preinscripción.

**URL**  :  `/API/Proveedores/Get/:id/`

**CURL**: `curl -X GET http://host/API/Proveedores/Get?id=12481`

**Parámetros de URL** : `id=[long]` Id del proveedor

**Método de la solicitud**  :  `GET`

**Requiere autenticación**  : Si

**Permisos requeridos**  : Ninguno
 
## Respuesta exitosa

**Condición**  : La credencial debe existir y la misma tiene los permisos necesarios.

**Código de estado**  :  `200 OK`

**Contenido** : Servicios.DataContracts.`PreinscripcionProveedorOutputDataContract`
    
    {
	"InformacionEmpresa": {
		"Id": 0,
		"tipoProveedor": 7,
		"TiposEmpresa": [3],
		"RazonSocial": "EMPRESA S.R.L.",
		"NombreFantasia": "",
		"NumeroCuit": "30600043000",
		"NumeroRegistroConstructores": "9972",
		"CorreoElectronicoInstitucional": "30600043000@email.com"
	},
	"InformacionBasicaDC": null,
	"DatosPersonaFisica": null,
	"PersonasLegales": [{
		"Id": 45754,
		"IdUsuario": "3f26d307-54cb-493c-93cc-7e5d3e378e30",
		"DatosPersona": {
			"Id": 92370,
			"Nombre": "Nombre",
			"Apellido": "Apellido",
			"NumeroCuit": "27-12345678-0",
			"TipoDocumentoIdentidad": 1,
			"DescripcionDocumentoIdentidad": "DNI",
			"NumeroDocumento": "12345678",
			"NombreUsuario": "username",
			"DescripcionPais": null,
			"IdPais": 0,
			"EstadoCivil": false,
			"Email": "correo@mail.com",
			"EmailAlternativo": "alternativo@email.com",
			"LimiteOferta": false,
			"MontoLimiteOferta": "0,00",
			"EsAdministradorLegitimado": true,
			"conyuge": null
		},
		"AutorizadoParaOfertar": true,
		"MontoLimiteSuma": false,
		"ValorLimiteSuma": 0,
		"TipoPersonaLegal": 1,
		"EstadoUsuario": 1,
		"FueInscripta": true
	}],
	"ProveedoresUTE": [],
	"NumeroDeInscripcion": null,
	"FechaPreinscripcion": "2019-06-13T10:55:30",
	"PermisoParaEditar": false,
	"FueInscripto": true,
	"EnEvaluacion": false,
	"Id": 12481
	}


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
eyJoaXN0b3J5IjpbLTEyMzkyNjgxMDRdfQ==
-->