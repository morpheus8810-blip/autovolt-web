# Pendientes de cumplimiento

Fecha base: 2026-06-14. Este checklist no reemplaza la revision de un abogado, contador o ingeniero electricista; sirve para no perder los frentes que deben cerrarse antes de publicar la app, cobrar sesiones o instalar estaciones de acceso publico.

## Alta prioridad

- [ ] Reemplazar en `terminos.html` y `privacidad.html` los placeholders `[NIT]`, `[DIRECCIÓN COMERCIAL]`, `[CIUDAD]` y `[FECHA DE VIGENCIA]` con datos societarios reales y verificados contra RUT/Camara de Comercio.
- [ ] Confirmar si AutoVolt ya puede presentarse publicamente como `AutoVolt Energy S.A.S` en todos los canales, incluyendo web, app, contratos, facturas y soporte.
- [ ] Definir el correo/canal formal de PQRS, soporte, habeas data y notificaciones; hoy el sitio usa `gerencia@autovoltenergy.net` como buzon unico.
- [ ] Definir si el sitio va a usar analitica/cookies. Si se agregan GA4, Meta Pixel, Hotjar, Plausible con cookies u otra herramienta similar, publicar aviso/capa de cookies y actualizar la politica de privacidad antes de instalar el script.
- [ ] Reemplazar los badges de Google Play y App Store por URLs reales cuando las apps esten publicadas. Mientras tanto quedan visuales, no clicables.

## Proteccion de datos personales

- [ ] Validar y aprobar la politica de privacidad con abogado, especialmente tratamiento de geolocalizacion, tokens FCM, historiales de carga, billetera, pasarela de pago y soporte.
- [ ] Asegurar que el registro de la app guarde evidencia de autorizacion previa, expresa e informada del titular para datos personales y terminos.
- [ ] Definir procedimiento interno para consultas, reclamos, supresion, revocatoria de autorizacion y actualizacion de datos.
- [ ] Revisar contratos o anexos de encargado/responsable con Firebase/Google, proveedor de pagos, WhatsApp/Meta, hosting y cualquier herramienta de soporte o analitica.
- [ ] Evaluar si AutoVolt debe registrar bases de datos en el RNBD. La SIC senala que las sociedades privadas obligadas son, entre otras, las que superan 100.000 UVT de activos totales.
- [ ] Definir politica de retencion y eliminacion de datos: cuenta, sesiones, transacciones, logs OCPP, soporte y backups.

## Consumidor, pagos y facturacion

- [ ] Mostrar al conductor, antes de iniciar una carga, precio aplicable, unidad de cobro, impuestos/cargos si aplican, condiciones de disponibilidad y aceptacion expresa.
- [ ] Definir reglas de billetera: recargas, saldo no usado, reembolsos, errores de cobro, reversos, vigencia de saldos y soporte.
- [ ] Validar con abogado la aplicacion de retracto, reversion de pago y excepciones para servicios que ya empezaron con aceptacion del consumidor.
- [ ] Implementar recibo/factura o documento soporte segun el modelo tributario aprobado por contador.
- [ ] Publicar mecanismos de PQRS y trazabilidad de solicitudes dentro de la app o desde canales externos.

## Electricidad, importacion y operacion de carga

- [ ] Verificar cumplimiento RETIE vigente para productos, instalaciones electricas y personas que intervienen instalaciones.
- [ ] Para cargadores importados, confirmar certificados de conformidad aplicables y si corresponde inscripcion como productor/importador de productos sujetos a reglamentos tecnicos ante la SIC.
- [ ] Documentar expediente por estacion: diseno, memoria electrica, protecciones, puesta a tierra, certificaciones, dictamen/inspeccion cuando aplique, manuales, garantias y acta de puesta en marcha.
- [ ] Validar requisitos de conexion con operador de red, capacidad disponible, medicion, protecciones, acometida, contrato de energia y obligaciones del inmueble anfitrion.
- [ ] Revisar si la estacion es de acceso publico y aplicar condiciones vigentes de interoperabilidad, conectores, reporte de informacion operativa, precios y disponibilidad.
- [ ] Para parqueaderos de vehiculos electricos, validar senalizacion y cupos preferenciales cuando aplique al inmueble.

## Comercial y contratos

- [ ] Preparar contratos modelo para: conjunto residencial/hotel, centro comercial, operador white-label, importacion de hardware, instalacion y soporte.
- [ ] Definir anexos tecnicos: SLA, mantenimiento, responsabilidades por energia, reparto de ingresos, seguros, vandalismo, indisponibilidad y propiedad del equipo.
- [ ] Definir politica de precios y comisiones publicas: evitar promesas absolutas si dependen de prefactibilidad, consumo, tarifa de energia o negociacion con el anfitrion.
- [ ] Preparar material de prefactibilidad para visitas: carga instalada, transformador, tablero, distancia, obra civil, operador de red, seguridad y flujo vehicular.

## Fuentes oficiales consultadas

- Ley 1581 de 2012 - proteccion de datos personales: https://www.funcionpublica.gov.co/eva/gestornormativo/norma.php?i=49981
- SIC - autorizacion previa, expresa e informada para tratamiento de datos: https://sedeelectronica.sic.gov.co/publicaciones/boletin-juridico/boletin/la-autorizacion-para-el-tratamiento-de-datos-personales-debe-ser-previa-expresa-e-informada-los-responsables-y
- SIC - obligados a registrar bases en RNBD: https://sedeelectronica.sic.gov.co/publicaciones/boletin-juridico/concepto/cuales-personas-estan-obligadas-realizar-el-registro-de-bases-de-datos-personales-en-el-rnbd
- MinEnergia - RETIE vigente: https://www.minenergia.gov.co/es/misional/energia-electrica-2/reglamentos-tecnicos/reglamento-t%C3%A9cnico-de-instalaciones-el%C3%A9ctricas-retie/
- SIC - registro de productores e importadores de productos sujetos a reglamentos tecnicos: https://serviciosweb.sic.gov.co/RegistroFabricantes/web/pages/index.php
- CREG - Resolucion 40123 de 2024, interoperabilidad para estaciones de carga de acceso publico: https://gestornormativo.creg.gov.co/gestor/entorno/docs/resolucion_minminas_40123_2024.htm
- MinEnergia - proyecto/lineamientos de interoperabilidad y reporte operativo de estaciones de carga: https://www.minenergia.gov.co/es/sala-de-prensa/noticias-index/minenergia-lanza-nueva-regulacion-que-integra-todas-las-estaciones-de-carga-electrica-del-pais/
- MinTransporte - parqueaderos preferenciales para vehiculos electricos: https://mintransporte.gov.co/publicaciones/9467/gobierno-expide-decreto-con-especificaciones-para-parqueaderos-de-vehiculos-electricos/
- SIC - derecho de retracto en compras a distancia/comercio electronico: https://sedeelectronica.sic.gov.co/noticias/se-arrepintio-de-una-compra-y-no-sabe-que-hacer
