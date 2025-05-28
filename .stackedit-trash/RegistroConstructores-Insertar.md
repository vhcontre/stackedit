##  RegistroConstructores: BaseController
Esta es la documentación de las APIs del sistema Contratar que utilizan principalmente Sonda.Framework.Website.Web.

## Insertar
Graba los datos del proveedor.

**URL**  :  `/API/RegistroConstructores/Insertar`

**CURL**: `curl -X POST http://host/API/RegistroConstructores/Insertar`

**Schema / Model** : SondaIConstruye.Framework.Entidad.DTO.RIUPP.`ProveedorDTO`

	{
		"id": 0,
		"informacionEmpresa": {
			"tipoProveedor": 1,
			"razonSocial": "string",
			"nombreFantasia": "string",
			"numeroCUIT": "string",
			"numeroIngresosBrutos": "string",
			"numeroIERIC": "string",
			"fechaVencimientoIERIC": "2021-02-26T19:30:30.294Z",
			"numeroRegistroConstructores": "string",
			"correoElectronicoInstitucional": "string",
			"id": 0,
			"tiposEmpresa": [
				3
			]
		},
		"informacionBasicaDC": {
			"id": 0,
			"idProveedor": 0,
			"constitucionProveedorDC": {
				"id": 0,
				"lugar": "string",
				"fecha": "2021-02-26T19:30:30.294Z",
				"fechaVigenciaContratoUTE": "2021-02-26T19:30:30.294Z",
				"numeroConstitucion": "string",
				"esUltimaModificacionEstatuto": true,
				"tipoConstitucion": 1
			},
			"modificacionEstatuto": {
				"id": 0,
				"lugar": "string",
				"fecha": "2021-02-26T19:30:30.294Z",
				"fechaVigenciaContratoUTE": "2021-02-26T19:30:30.294Z",
				"numeroConstitucion": "string",
				"esUltimaModificacionEstatuto": true,
				"tipoConstitucion": 1
			},
			"domicilio": {
				"id": 0,
				"calle": "string",
				"codigoAreaAlternativo": "string",
				"codigoAreaContacto": "string",
				"codigoPostal": "string",
				"fax": "string",
				"localidad": {
					"id": 0,
					"descripcion": "string",
					"departamento": {
						"id": 0,
						"descripcion": "string",
						"provincia": {
							"id": 0,
							"descripcion": "string",
							"pais": {
								"id": 0,
								"descripcion": "string",
								"nacionalidad": "string"
							}
						}
					}
				},
				"nombreCalle": "string",
				"nombreLocalidad": "string",
				"numeroCalle": "string",
				"numeroDepartamento": "string",
				"numeroPiso": "string",
				"pais": {
					"id": 0,
					"descripcion": "string",
					"nacionalidad": "string"
				},
				"provincia": {
					"id": 0,
					"descripcion": "string",
					"pais": {
						"id": 0,
						"descripcion": "string",
						"nacionalidad": "string"
					}
				},
				"departamento": {
					"id": 0,
					"descripcion": "string",
					"provincia": {
						"id": 0,
						"descripcion": "string",
						"pais": {
							"id": 0,
							"descripcion": "string",
							"nacionalidad": "string"
						}
					}
				},
				"telefonoAlternativo": "string",
				"telefonoContacto": "string",
				"tipoDireccion": 0
			},
			"domicilioEspecial": {
				"id": 0,
				"calle": "string",
				"codigoAreaAlternativo": "string",
				"codigoAreaContacto": "string",
				"codigoPostal": "string",
				"fax": "string",
				"localidad": {
					"id": 0,
					"descripcion": "string",
					"departamento": {
						"id": 0,
						"descripcion": "string",
						"provincia": {
							"id": 0,
							"descripcion": "string",
							"pais": {
								"id": 0,
								"descripcion": "string",
								"nacionalidad": "string"
							}
						}
					}
				},
				"nombreCalle": "string",
				"nombreLocalidad": "string",
				"numeroCalle": "string",
				"numeroDepartamento": "string",
				"numeroPiso": "string",
				"pais": {
					"id": 0,
					"descripcion": "string",
					"nacionalidad": "string"
				},
				"provincia": {
					"id": 0,
					"descripcion": "string",
					"pais": {
						"id": 0,
						"descripcion": "string",
						"nacionalidad": "string"
					}
				},
				"departamento": {
					"id": 0,
					"descripcion": "string",
					"provincia": {
						"id": 0,
						"descripcion": "string",
						"pais": {
							"id": 0,
							"descripcion": "string",
							"nacionalidad": "string"
						}
					}
				},
				"telefonoAlternativo": "string",
				"telefonoContacto": "string",
				"tipoDireccion": 0
			}
		},
		"personaFisica": {
			"id": 0,
			"apellido": "string",
			"estadoCivil": true,
			"fechaNacimiento": "2021-02-26T19:30:30.294Z",
			"idPais": 0,
			"nombre": "string",
			"numeroCuit": "string",
			"cargo": "string",
			"numeroDocumento": "string",
			"personasLegales": [{
				"id": 0,
				"autorizadoParaOfertar": true,
				"autorizadoParaOfertarporRIUPP": true,
				"cargo": "string",
				"esAgregado": true,
				"esEliminado": true,
				"idUsuario": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
				"montoLimiteSuma": true,
				"tipoPersonaLegal": 0,
				"usuario": {
					"clave": "string",
					"email": "string",
					"emailAlternativo": "string",
					"numeroCUIT": "string",
					"activo": true,
					"fechaCreacion": "string",
					"id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
					"idPerfil": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
					"nombreUsuario": "string",
					"rol": "string",
					"estadoUsuario": 0
				},
				"valorLimiteSuma": 0,
				"activo": true,
				"rol": "string",
				"profesion": "string",
				"numeroMatricula": "string",
				"fechaVencimientoContrato": "2021-02-26T19:30:30.294Z",
				"esContratado": true,
				"esAsociado": true,
				"nombre": "string",
				"apellido": "string",
				"nombreCompleto": "string",
				"nombreCompletoCUIT": "string",
				"roles": [{
					"rolPersonaLegal": 0,
					"descripcion": "string"
				}]
			}],
			"tipoDocumentoIdentidad": 0,
			"limiteOferta": true,
			"montoLimiteOferta": 0,
			"esAdministradorLegitimado": true,
			"email": "string",
			"emailAlternativo": "string",
			"profesion": "string",
			"numeroMatricula": "string",
			"fechaVencimientoContrato": "2021-02-26T19:30:30.294Z",
			"esContratado": true,
			"esAsociado": true,
			"domicilio": "string",
			"telefono": "string",
			"usuario": {
				"clave": "string",
				"email": "string",
				"emailAlternativo": "string",
				"numeroCUIT": "string",
				"activo": true,
				"fechaCreacion": "string",
				"id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
				"idPerfil": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
				"nombreUsuario": "string",
				"rol": "string",
				"estadoUsuario": 0
			}
		},
		"domicilioReal": {
			"id": 0,
			"calle": "string",
			"codigoAreaAlternativo": "string",
			"codigoAreaContacto": "string",
			"codigoPostal": "string",
			"fax": "string",
			"localidad": {
				"id": 0,
				"descripcion": "string",
				"departamento": {
					"id": 0,
					"descripcion": "string",
					"provincia": {
						"id": 0,
						"descripcion": "string",
						"pais": {
							"id": 0,
							"descripcion": "string",
							"nacionalidad": "string"
						}
					}
				}
			},
			"nombreCalle": "string",
			"nombreLocalidad": "string",
			"numeroCalle": "string",
			"numeroDepartamento": "string",
			"numeroPiso": "string",
			"pais": {
				"id": 0,
				"descripcion": "string",
				"nacionalidad": "string"
			},
			"provincia": {
				"id": 0,
				"descripcion": "string",
				"pais": {
					"id": 0,
					"descripcion": "string",
					"nacionalidad": "string"
				}
			},
			"departamento": {
				"id": 0,
				"descripcion": "string",
				"provincia": {
					"id": 0,
					"descripcion": "string",
					"pais": {
						"id": 0,
						"descripcion": "string",
						"nacionalidad": "string"
					}
				}
			},
			"telefonoAlternativo": "string",
			"telefonoContacto": "string",
			"tipoDireccion": 0
		},
		"domicilioEspecial": {
			"id": 0,
			"calle": "string",
			"codigoAreaAlternativo": "string",
			"codigoAreaContacto": "string",
			"codigoPostal": "string",
			"fax": "string",
			"localidad": {
				"id": 0,
				"descripcion": "string",
				"departamento": {
					"id": 0,
					"descripcion": "string",
					"provincia": {
						"id": 0,
						"descripcion": "string",
						"pais": {
							"id": 0,
							"descripcion": "string",
							"nacionalidad": "string"
						}
					}
				}
			},
			"nombreCalle": "string",
			"nombreLocalidad": "string",
			"numeroCalle": "string",
			"numeroDepartamento": "string",
			"numeroPiso": "string",
			"pais": {
				"id": 0,
				"descripcion": "string",
				"nacionalidad": "string"
			},
			"provincia": {
				"id": 0,
				"descripcion": "string",
				"pais": {
					"id": 0,
					"descripcion": "string",
					"nacionalidad": "string"
				}
			},
			"departamento": {
				"id": 0,
				"descripcion": "string",
				"provincia": {
					"id": 0,
					"descripcion": "string",
					"pais": {
						"id": 0,
						"descripcion": "string",
						"nacionalidad": "string"
					}
				}
			},
			"telefonoAlternativo": "string",
			"telefonoContacto": "string",
			"tipoDireccion": 0
		},
		"lugarConstitucion": "string",
		"fechaConstitucion": "2021-02-26T19:30:30.294Z",
		"balance": {
			"ejerciciosContables": [{
				"id": 0,
				"fechaCierre": "2021-02-26T19:30:30.294Z",
				"numeroEjercicio": 0,
				"activoCorriente": 0,
				"pasivoCorriente": 0,
				"bienesDeCambio": 0,
				"costoMercaderiasVendidas": 0,
				"pasivoTotal": 0,
				"activoTotal": 0,
				"resultadoEjercicio": 0,
				"patrimonioNeto": 0,
				"capital": 0,
				"ventasTotalesEjercicio": 0
			}],
			"sectorEmpresarial": 0
		},
		"especialidades": [{
			"id": 0,
			"nombre": "string"
		}],
		"observacionesDesactualizacionClase": "string",
		"estadoProveedor": 0,
		"estadoAnteriorProveedor": 0,
		"fechaPreInscripcion": "2021-02-26T19:30:30.294Z",
		"fechaVigenciaContratoUTE": "2021-02-26T19:30:30.294Z",
		"motivo": "string",
		"numeroInterno": "string",
		"personasLegales": [{
			"id": 0,
			"autorizadoParaOfertar": true,
			"autorizadoParaOfertarporRIUPP": true,
			"cargo": "string",
			"esAgregado": true,
			"esEliminado": true,
			"idUsuario": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
			"montoLimiteSuma": true,
			"tipoPersonaLegal": 0,
			"usuario": {
				"clave": "string",
				"email": "string",
				"emailAlternativo": "string",
				"numeroCUIT": "string",
				"activo": true,
				"fechaCreacion": "string",
				"id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
				"idPerfil": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
				"nombreUsuario": "string",
				"rol": "string",
				"estadoUsuario": 0
			},
			"valorLimiteSuma": 0,
			"activo": true,
			"rol": "string",
			"profesion": "string",
			"numeroMatricula": "string",
			"fechaVencimientoContrato": "2021-02-26T19:30:30.294Z",
			"esContratado": true,
			"esAsociado": true,
			"nombre": "string",
			"apellido": "string",
			"nombreCompleto": "string",
			"nombreCompletoCUIT": "string",
			"roles": [{
				"rolPersonaLegal": 0,
				"descripcion": "string"
			}]
		}],
		"apoderados": [{
			"id": 0,
			"autorizadoParaOfertar": true,
			"autorizadoParaOfertarporRIUPP": true,
			"cargo": "string",
			"esAgregado": true,
			"esEliminado": true,
			"idUsuario": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
			"montoLimiteSuma": true,
			"tipoPersonaLegal": 0,
			"usuario": {
				"clave": "string",
				"email": "string",
				"emailAlternativo": "string",
				"numeroCUIT": "string",
				"activo": true,
				"fechaCreacion": "string",
				"id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
				"idPerfil": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
				"nombreUsuario": "string",
				"rol": "string",
				"estadoUsuario": 0
			},
			"valorLimiteSuma": 0,
			"activo": true,
			"rol": "string",
			"profesion": "string",
			"numeroMatricula": "string",
			"fechaVencimientoContrato": "2021-02-26T19:30:30.294Z",
			"esContratado": true,
			"esAsociado": true,
			"nombre": "string",
			"apellido": "string",
			"nombreCompleto": "string",
			"nombreCompletoCUIT": "string",
			"roles": [{
				"rolPersonaLegal": 0,
				"descripcion": "string"
			}]
		}],
		"representantesLegales": [{
			"id": 0,
			"autorizadoParaOfertar": true,
			"autorizadoParaOfertarporRIUPP": true,
			"cargo": "string",
			"esAgregado": true,
			"esEliminado": true,
			"idUsuario": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
			"montoLimiteSuma": true,
			"tipoPersonaLegal": 0,
			"usuario": {
				"clave": "string",
				"email": "string",
				"emailAlternativo": "string",
				"numeroCUIT": "string",
				"activo": true,
				"fechaCreacion": "string",
				"id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
				"idPerfil": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
				"nombreUsuario": "string",
				"rol": "string",
				"estadoUsuario": 0
			},
			"valorLimiteSuma": 0,
			"activo": true,
			"rol": "string",
			"profesion": "string",
			"numeroMatricula": "string",
			"fechaVencimientoContrato": "2021-02-26T19:30:30.294Z",
			"esContratado": true,
			"esAsociado": true,
			"nombre": "string",
			"apellido": "string",
			"nombreCompleto": "string",
			"nombreCompletoCUIT": "string",
			"roles": [{
				"rolPersonaLegal": 0,
				"descripcion": "string"
			}]
		}],
		"socios": [{
			"id": 0,
			"autorizadoParaOfertar": true,
			"autorizadoParaOfertarporRIUPP": true,
			"cargo": "string",
			"esAgregado": true,
			"esEliminado": true,
			"idUsuario": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
			"montoLimiteSuma": true,
			"tipoPersonaLegal": 0,
			"usuario": {
				"clave": "string",
				"email": "string",
				"emailAlternativo": "string",
				"numeroCUIT": "string",
				"activo": true,
				"fechaCreacion": "string",
				"id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
				"idPerfil": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
				"nombreUsuario": "string",
				"rol": "string",
				"estadoUsuario": 0
			},
			"valorLimiteSuma": 0,
			"activo": true,
			"rol": "string",
			"profesion": "string",
			"numeroMatricula": "string",
			"fechaVencimientoContrato": "2021-02-26T19:30:30.295Z",
			"esContratado": true,
			"esAsociado": true,
			"nombre": "string",
			"apellido": "string",
			"nombreCompleto": "string",
			"nombreCompletoCUIT": "string",
			"roles": [{
				"rolPersonaLegal": 0,
				"descripcion": "string"
			}]
		}],
		"idSectorEmpresarial": 0,
		"ventasAnuales": [{
			"id": 0,
			"annoFiscal": 0,
			"esActivo": true,
			"totalVentas": 0
		}],
		"evaluaciones": [{
			"id": 0,
			"comentario": "string",
			"estadoEvaluacion": 1,
			"evaluacionesParciales": [{
				"estadoEvaluacion": 1,
				"tipoEvaluacion": 1
			}],
			"fechaEvaluacion": "2021-02-26T19:30:30.295Z",
			"formularioEvaluacionXml": "string",
			"idUsuarioEvaluacion": "3fa85f64-5717-4562-b3fc-2c963f66afa6"
		}],
		"mvtoHistoricos": [{
			"id": 0,
			"comentario": "string",
			"estado": 0,
			"fecha": "2021-02-26T19:30:30.295Z",
			"idAccion": 1,
			"idUsuarioRiupp": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
			"usuario": {}
		}],
		"numeroInscripcion": {
			"numeroRegistroComercio": "string",
			"numeroInspeccionJusticia": "string",
			"numeroINAC": "string",
			"numeroRECIGE": "string",
			"idProveedor": "string"
		},
		"proveedoresUTE": [{
			"id": 0,
			"cuit": "string",
			"razonSocial": "string",
			"idProveedorSeleccionado": 0,
			"porcentajeDeParticipacion": 0
		}],
		"personaLegalFisica": {
			"id": 0,
			"autorizadoParaOfertar": true,
			"autorizadoParaOfertarporRIUPP": true,
			"cargo": "string",
			"esAgregado": true,
			"esEliminado": true,
			"idUsuario": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
			"montoLimiteSuma": true,
			"tipoPersonaLegal": 0,
			"usuario": {
				"clave": "string",
				"email": "string",
				"emailAlternativo": "string",
				"numeroCUIT": "string",
				"activo": true,
				"fechaCreacion": "string",
				"id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
				"idPerfil": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
				"nombreUsuario": "string",
				"rol": "string",
				"estadoUsuario": 0
			},
			"valorLimiteSuma": 0,
			"activo": true,
			"rol": "string",
			"profesion": "string",
			"numeroMatricula": "string",
			"fechaVencimientoContrato": "2021-02-26T19:30:30.295Z",
			"esContratado": true,
			"esAsociado": true,
			"nombre": "string",
			"apellido": "string",
			"nombreCompleto": "string",
			"nombreCompletoCUIT": "string",
			"roles": [{
				"rolPersonaLegal": 0,
				"descripcion": "string"
			}]
		},
		"tipoProveedor": 1,
		"numeroRegistroComercio": "string",
		"numeroInspeccionJusticia": "string",
		"numeroINAC": "string",
		"numeroRECIGE": "string",
		"numeroIngresosBrutos": "string",
		"numeroIERIC": "string",
		"vencimientoIERIC": "2021-02-26T19:30:30.295Z",
		"constituciones": [{
			"id": 0,
			"lugar": "string",
			"fecha": "2021-02-26T19:30:30.295Z",
			"fechaVigenciaContratoUTE": "2021-02-26T19:30:30.295Z",
			"numeroConstitucion": "string",
			"esUltimaModificacionEstatuto": true,
			"tipoConstitucion": 1
		}],
		"categoria": 0,
		"empresa": {
			"id": 0,
			"direcciones": [{
				"id": 0,
				"calle": "string",
				"codigoAreaAlternativo": "string",
				"codigoAreaContacto": "string",
				"codigoPostal": "string",
				"fax": "string",
				"localidad": {
					"id": 0,
					"descripcion": "string",
					"departamento": {
						"id": 0,
						"descripcion": "string",
						"provincia": {
							"id": 0,
							"descripcion": "string",
							"pais": {
								"id": 0,
								"descripcion": "string",
								"nacionalidad": "string"
							}
						}
					}
				},
				"nombreCalle": "string",
				"nombreLocalidad": "string",
				"numeroCalle": "string",
				"numeroDepartamento": "string",
				"numeroPiso": "string",
				"pais": {
					"id": 0,
					"descripcion": "string",
					"nacionalidad": "string"
				},
				"provincia": {
					"id": 0,
					"descripcion": "string",
					"pais": {
						"id": 0,
						"descripcion": "string",
						"nacionalidad": "string"
					}
				},
				"departamento": {
					"id": 0,
					"descripcion": "string",
					"provincia": {
						"id": 0,
						"descripcion": "string",
						"pais": {
							"id": 0,
							"descripcion": "string",
							"nacionalidad": "string"
						}
					}
				},
				"telefonoAlternativo": "string",
				"telefonoContacto": "string",
				"tipoDireccion": 0
			}],
			"esActivo": true,
			"fechaCreacion": "2021-02-26T19:30:30.295Z",
			"idPais": 0,
			"nombreFantasia": "string",
			"nombreRazonSocial": "string",
			"numeroCuit": "string",
			"numeroPasaporte": "string",
			"numeroDocumento": "string",
			"correoInstitucional": "string",
			"tipoDocumentoIdentidad": 0,
			"tiposEmpresa": [
				3
			]
		},
		"documentos": [{
			"fechaVencimiento": "2021-02-26T19:30:30.295Z",
			"codigo": 0,
			"descripcion": "string",
			"idProveedor": 0,
			"primerAviso": true,
			"segundoAviso": true,
			"vencido": true
		}] }

**Método de la solicitud**  :  `POST`

**Requiere autenticación**  : Si

**Permisos requeridos**  : Ninguno
 
## Respuesta exitosa

**Condición**  : La credencial debe existir y la misma tiene los permisos necesarios.

**Código de estado**  :  `200 OK`

**Contenido** : 
    


## Respuestas de error

**Condición** : .

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
eyJoaXN0b3J5IjpbLTEzMzU4Mzk0NDldfQ==
-->