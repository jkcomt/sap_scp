# Introducción al desarrollo OData con SAP Netweaver Gateway

Este documento supone ser una introducción a temas de desarrollo OData con el uso de la herramienta SAP Netweaver Gateway para principiantes.
Su revisión y actualización está abierta a sugerencias.

# Sap Netweaver Gateway 
<p align="justify">
SAP Netweaver Gateway facilita el desarrollo de aplicaciones de negocio SAP tanto en beneficio de los usuarios finales, como de los desarrolladores.

Con SAP Netweaver Gateway se rompen las barreras de la tecnología, haciendo posible explotar los datos SAP desde aplicaciones desarrolladas  en cualquier lenguaje de programación, sin que saber ABAP, sea necesario. La clave de todo esto son los servicios oData.
</p>

# OData

<p>
oData es un protocolo basado en el paradigma de desarrollo REST.

Este paradigma entre otros aspectos tiene en cuenta 5 comandos ante los que el servidor debe responder: GET, POST, PUT, DELETE y PATCH. Estos comandos se corresponden con las operaciones Create, Retrieve, Update y Delete de las interfaces CRUD.

Los servicios oData soportan este tipo de operaciones, aunque no es obligatorio que implementen todas.

En SAP Netweaver Gateway es posible crear este tipo de servicios oData que permitan crear, leer, actualizar o borrar datos procedentes de por ejemplo un SAP ERP desde una aplicación  desarrollada por ejemplo con HTML5 y Javascript.

Los servicio oData se basan en XML aunque también es posible desplegarlos utilizando JSON. La elección de un formato u otro dependerá del desarrollador y/o de la tecnología a usar para consumir servicios oData.
</p>

# Servicios OData en SAP Netweaver Gateway

## SAP Netweaver Service Builder

Desde la transacción SEGW del SAP Netweaver Gateway se pueden crear servicios oData de manera manual creando las entidades deseadas e implementando las operaciones requeridas o a partir de estructuras ya definidas como por ejemplo:

+ Estructuras de diccionario ABAP
+ Remote Function Call (RFCs)
+ BAPIs del Bussiness Object Repository (BOR)

## SAP Netweaver Gateway Client

Esta herramienta del SAP Gateway permite testear los servicios oData creados desde la transacción anterior.

