##  ProveedoresController : BaseController

Esta es la documentación de las APIs del sistema Contratar que se utiliza principalmente desde Sonda.Framework.Website.Web.

## ObtenerDatosConstancia
Obtiene los detalles del proveedor con su Constancia Histórica Inscripción.

**URL**  :  `/API/Proveedores/GetSmall/:id/:fecha`

**CURL**: 
`curl -X GET http://host/API/Proveedores/ObtenerDatosConstancia?id=12481&fecha=Thu%20Feb%2025%202021`

**Parámetros de URL** : 
`id=[long]` Id del proveedor
`fecha=[DateTime]` Consulta de fecha emisión histórica

**Método de la solicitud**  :  `GET`

**Requiere autenticación**  : Si

**Permisos requeridos**  : Ninguno
 
## Respuesta exitosa

**Condición**  : La credencial debe existir y la misma tiene los permisos necesarios.

**Código de estado**  :  `200 OK`

**Contenido** : Servicios.DataContracts.Proveedor.`ConstanciaInscripcionDataContract`
    
	{
		"FechaConsulta": "25/2/2021",
		"FechaEmisionHistorica": "25/2/2021",
		"RazonSocial": "EMPRESA S.R.L.",
		"TipoPersoneria": "Sociedad de responsabilidad limitada",
		"NumeroCUIT": "30600043000",
		"TiposEmpresa": [3],
		"EstadoProveedor": "Desactualizado por documentos...",
		"EstadoAnteriorProveedor": "Inscripto",
		"CapacidadContratacion": 2288.14,
		"CapacidadEjecucion": 2847.71,
		"FueInscripto": true,
		"FechaPreinscripcion": "2019-06-13T10:55:30",
		"PorcentajesPorEspecialidades": [{
			"DescripcionEspecialidad": "Obras de Arquitectura",
			"Porcentaje": 81.47,
			"Id": 10793
	}, {
		"DescripcionEspecialidad": "Sanitaria",
		"Porcentaje": 18.53,
		"Id": 10794
	}],
	"ObrasEnProcesoDeAdjudicacion": [],
	"ObrasAdjudicadasYEnEjecucion": [{
		"Codigo": 27,
		"Especialidades": null,
		"FechaAdjudicacion": "31/12/2017",
		"EstadoObra": "En ejecución",
		"Denominacion": "Sistema Denominación",
		"RazonSocialComitente": "Obras Razón Social Comitente",
		"MontoVigente": 9999.00,
		"MontoCertificado": 9999.00,
		"Saldo": 3136.00,
		"FueInscripta": true,
		"Id": 4469
	}, {
		"Codigo": 28,
		"Especialidades": null,
		"FechaAdjudicacion": "1/3/2017",
		"EstadoObra": "En ejecución",
		"Denominacion": "Edificio de Control General",
		"RazonSocialComitente": "Ministerio del Gobierno",
		"MontoVigente": 7704.00,
		"MontoCertificado": 9177.00,
		"Saldo": 11476.00,
		"FueInscripta": true,
		"Id": 4472
	}, {
		"Codigo": 29,
		"Especialidades": null,
		"FechaAdjudicacion": "8/8/2017",
		"EstadoObra": "En ejecución",
		"Denominacion": "COMPLETAMIENTO  DE  LAS  OBRAS",
		"RazonSocialComitente": "Razon Social Comitente",
		"MontoVigente": 9558.00,
		"MontoCertificado": 9143.00,
		"Saldo": 4156.00,
		"FueInscripta": true,
		"Id": 4476
	}],
	"LeyendaEjercicio": "2021: Año de Martín Miguel de Güemes",
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
eyJoaXN0b3J5IjpbMzMxNjE3ODZdfQ==
-->