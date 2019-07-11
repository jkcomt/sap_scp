# Introducción a SAP ABAP

Este documento supone ser una introducción a temas de ABAP para principiantes.
Su revisión y actualización está abierta a sugerencias.

 [¿Qué es ABAP?](#%C2%BFQu%C3%A9-es-ABAP)  
 [Diccionario de Datos](#Diccionario-de-Datos)  
 [Elementos del Diccionario de Datos](#Elementos-del-Diccionario-de-Datos)
 1. [Tablas](#1-Tablas)  
    1.1 [Tablas Transparentes](#11-Tablas-Transparentes)  
    1.2 [Tablas Pool](#12-Tablas-Pool-Pooled-Tables)  
    1.3 [Tablas Cluster](#13-Tablas-Cluster-Cluster-Tables)
2. [Componentes de Tablas](#2-Componentes-de-Tablas)  
   2.1 [El Dominio](#21-El-Dominio)   
   2.2 [Elemento de Datos](#22-Elemento-de-Datos)   
   2.3 [Tablas](#23-Tablas)
3. [Vista de Actualización](#3-Vista-de-Actualizaci%C3%B3n)

## ¿Qué es ABAP?
---
<p align="justify">
ABAP (Advanced Business Application Programming) es un lenguaje de cuarta generación, propiedad de SAP, que se utiliza para programar la mayoría de sus productos (R/3, mySAP Business suite...). Utiliza sentencias de Open SQL para conectarse con prácticamente cualquier base de datos. Cuenta con miles de funciones para el manejo de archivos, bases de datos, fechas, etc. Permite conexiones RFC (Remote Function Calls) para conectar a los sistemas SAP con cualquier otro sistema o lenguaje de programación. 
</p>

## Diccionario de Datos
---
<p align="justify">
El Diccionario de Datos ABAP (Data Dictionary) es la fuente central de información sobre los datos almacenados en el sistema. Su rol principal es la creación y administración de las definiciones de datos (o metadatos)

Ejemplos de las tareas que realizaremos desde el diccionario de datos de ABAP son la creación de tablas, incorporación y visualización de la información almacenada, definición de los tipos de datos que utilizan los campos de las tablas, definición de la documentación relacionada a cada campo y mucho más.
</p>

## Elementos del Diccionario de Datos
---
### 1. Tablas

<p align="justify">
Las tablas del diccionario de SAP son la fuente de información central y estructurada de la empresa. SAP utiliza un tipo de base de datos de tipo relacional con tablas que contienen uno o más campos clave. SAP contiene tablas estándar de las cuales se alimentan y a las cuales informan las transacciones del sistema, si bien es verdad que al diccionario se le pueden añadir tablas de creación propia.

[Tablas Standard de SAP][tipos de tablas standard en sap]

Se dividen en 3 tipos de datos :

</p>

### 1.1 Tablas Transparentes

<p align="justify">
Una tabla transparente corresponde a un conjunto definido de campos estructurados almacenada en el diccionario de SAP. Una tabla transparente puede ser “llenada” con información. De hecho, una tabla en general es la unidad mínima necesario para introducir información en nuestra base de datos.

Es el tipo más común de tabla y es el más utilizado por los
desarrolladores ABAP

</p>

### 1.2 Tablas Pool (Pooled Tables)

<p align="justify">
Guarda registros de datos procedentes de las tablas definidas en el Dictionary ABAP y no dependen los unos de los otros. Se podrían combinar varias tablas SAP pequeñas en una tabla de base de datos.

[Más info en este link.][tablas pool]

</p>

![img tabla pool]

### 1.3 Tablas Cluster (Cluster Tables):

<p align="justify">
Guardan datos de diferentes tablas en una tabla de base de datos. En consecuencia, la intersección de los campos clave de las tablas cluster forma la clave del cluster.

[Más info en este link.][tablas cluster]

</p>

![img tabla cluster]

### 2. Componentes de Tablas
### 2.1 El Dominio

<p align="justify">
En un dominio podemos definir que valores puede tener un campo (caracteres, números enteros, números con decimales, …), así como la longitud de los mismos.
</p>

+ Transacción SE11
+ Seleccionar la dominio y dar un nombre a nuestro dominio

![img dominio1]
+ Damos una descripción al dominio y establecemos un tipo de datos y longitud del mismo.

![img dominio2]

+ El la pestaña Ámbito de valores podemos definir que valores puede tomar el campo.

![img dominio3]

+ Grabamos y Activamos

### 2.2 Elemento de Datos

<p align="justify">
En un Elemento de Datos definimos el dominio y la descripción del campo al que irá referenciado en la tabla.
</p>

+ Transacción SE11
+ Seleccionamos la opción Tipo de Datos, damos un nombre y le damos a crear, a continuación se nos mostrará un Pop-Up en el que seleccionaremos la opción Elemento de Datos

![img elem dato1]

+ Le damos una descripción y asignamos un dominio, en este caso asignaremos el dominio que hemos creado anteriormente.

![img elem dato2]

+ En la pestaña Denom. Campo creamos la definición del campo al que irá asociado en la tabla. Esta descripción será la que se mostrará en la cabecera de la tabla.

![img elem dato3]

### 2.3 Tablas
<p align="justify">
Una vez tenemos creados los Dominos y Elementos de Datos, crearemos la Tabla Z.
</p>

+ Transacción SE11
+ Definimos la descripción de usuario y la clase de entrega.

![img tabla1]

+ Creamos los campos de la tabla y le asignamos el elemento de datos.

![img tabla2]

>**Clase de Entrega**: Se utiliza para controlar el transporte de datos de la tabla para una instalación, actualización o cópia del cliente y el transporte. También se utiliza para el mantenimiento extendido de la tabla. Para la mayoría de los casos se utilizara el tipo A.  
>**Actualización Vista Tabla**: Se utiliza para las vistas de la tabla, vistas y mantenimiento , en nuestro caso seleccionamos Vista/actualización permitida con restricciones.

+ Definimos los campos de la tabla y le asignamos el elemento de datos a cada uno.

![img tabla3]

>Deberemos de marcar la clave de la tabla.

+ Configurar Opciones Técnicas de la tabla y definir los parámetros de memoria lógicos.

![img tabla4]

![img tabla5]

+ Definir categoría de aplicación de la tabla, en el menú de opciones superior Detalles > Categoría de Apliación.

![img tabla6]
>En función del tipo, definiremos como ampliaremos la tabla en el futuro, en nuestro caso seleccionamos Ampliable de cualquier manera.

+ Guardamos y Activamos.

[Más info][link abap1]

### 3. Vista de Actualización
---
<p align="justify">
Una imagen o vista de actualización es una forma que SAP nos proporciona para poder introducir datos en tablas sin necesidad de entrar en el explorador de tablas ni tener que programar.

Posteriormente, si se desea acceder en forma más directa a la vista de mantenimiento, también puede ser conveniente y útil asociarla a una transacción.
</p>

### Crear la Vista de mantenimiento

<p align="justify">
El primer paso será acceder a la transacción SE11 donde será necesario ingresar el nombre de la tabla para la cual se desea crear la vista de mantenimiento.

Asumiendo que la tabla fue creada previamente, bastará con ingresar el nombre de la misma en el campo correspondiente.

En este caso, a modo de ejemplo, la tabla tiene como nombre ZDI_EMPLEADOS.
</p>

![img visual1]

Luego será necesario seleccionar Change (Modificar).

En la pantalla obtenida, se mostrará la estructura de la tabla y dirigirse a Utilities → Table Maintenance Generator.

![img visual2]

La próxima pantalla que aparecerá en este proceso será similar a la siguiente:

![img visual3]

Como se muestra en la figura precedente, será necesario seleccionar la opción Find Scr. Number(s).

En la mayoría de los casos bastará con dejar la opción por defecto que es la primera:

![img visual4]

Finalmente, habrá que seleccionar el icono correspondiente a crear:

![img visual5]

Luego se deberá seleccionar el motivo por el cual se está creando la vista de mantenimiento:

![img visual6]

Es recomendable en la pantalla siguiente, dejar los valores que se muestran por defecto:

![img visual7]

El mensaje siguiente informa que la vista ha sido creada satisfactoriamente.

![img visual8]

Finalmente, para corroborar que la vista de mantenimiento ha sido creada correctamente, bastará con acceder a la transacción SM30 y colocar el nombre correspondiente a la tabla para la cual se ha creado la vista de mantenimiento, como se muestra en la figura siguiente:

![img visual9]

A partir de aquí, se podrán visualizar los datos al entrar a través de la opción Display o alterar los mismos entrando por la opción Maintain.

### Asociar la vista de mantenimiento a una transacción

Para poder asociar la vista de mantenimiento creada previamente a una transacción, los pasos a seguir serán los siguientes:

Acceder a la transacción **SE93**:

![img visual10]

En esta pantalla se escribirá el nuevo nombre de la transacción y luego seleccionar Create (en este caso el nombre de la transacción será el mismo que el de la vista de mantenimiento y el de la tabla para que sea más claro el ejemplo, de todas formas, se podría asignar un nombre diferente).

Habrá que ingresar una descripción (en este caso se eligió EMPLEADOS) y luego seleccionar la opción Transaction with parameters.

![img visual11]

En la siguiente pantalla será necesario configurar los siguientes parámetros:

+ **Transaction**: se indtroducirá SM30 (que corresponde a la transacción de vistas de mantenimiento).

+ **Name of screen field** (debajo de Default Values, abajo del lado izquierdo): se completará con VIEWNAME y se colocará en el parámetro Value, el nombre de la vista de mantenimiento creada (en este caso: ZDI_EMPLEADOS).

+ Finalmente será necesario tildar la opción ***Inherit GUI atributes.***

![img visual12]

Guarden los cambios realizados presionando ![img visual13]

SAP solicitará información correspondiente al **Package** en el cual se está trabajando y el usuario responsable, como se presenta en la figura siguiente:

![img visual14]

Posteriormente, se solicitará información referente a la orden de transporte:

![img visual15]

Solo restará ingresar el nombre de la transacción recientemente creada y verificar que esté funcionando correctamente:

![img visual16]

Como último paso, ya a partir de aquí se puede acceder a la vista de mantenimiento creada previamente **accediendo a la transacción que fue creada recientemente**, como se muestra en la siguiente pantalla:

![img visual18]
<!-- enlaces -->

[tipos de tablas standard en sap]: https://www.blogdesap.com/2010/03/tablas-del-diccionario.html
[tablas pool]:    https://training.logaligroup.com/tablas-pool/
[tablas cluster]: https://training.logaligroup.com/tablas-cluster/
[link abap1]: http://desarrollofacil.com/abap/
<!-- imagenes -->

[img tabla pool]:   https://training.logaligroup.com/wp-content/uploads/2018/05/01-12.png

[img tabla cluster]:https://training.logaligroup.com/wp-content/uploads/2018/05/02-11.png

[img dominio1]:http://desarrollofacil.com/wp-content/uploads/2016/09/Dominio_1.png
[img dominio2]:http://desarrollofacil.com/wp-content/uploads/2016/09/Dominio_2.png
[img dominio3]:http://desarrollofacil.com/wp-content/uploads/2016/09/Dominio_3.png

[img elem dato1]:http://desarrollofacil.com/wp-content/uploads/2016/09/Imagen8.png
[img elem dato2]:http://desarrollofacil.com/wp-content/uploads/2016/09/Imagen5.png
[img elem dato3]:http://desarrollofacil.com/wp-content/uploads/2016/09/Imagen6.png

[img tabla1]:http://desarrollofacil.com/wp-content/uploads/2016/09/Imagen9.png
[img tabla2]:http://desarrollofacil.com/wp-content/uploads/2016/09/Imagen10.png
[img tabla3]:http://desarrollofacil.com/wp-content/uploads/2016/09/Imagen11.png
[img tabla4]:http://desarrollofacil.com/wp-content/uploads/2016/09/Imagen12.png
[img tabla5]:http://desarrollofacil.com/wp-content/uploads/2016/09/Cap-2.png
[img tabla6]:http://desarrollofacil.com/wp-content/uploads/2016/09/Imagen14.png

[img visual1]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-transaccion-SE11_1.png

[img visual2]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-tip-generar-Vista-mantenimiento_2.png
[img visual3]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-vista-mantenimiento-find-screen_3.png
[img visual4]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-maint-screen-number_4.png
[img visual5]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-crear-vista-mantenimiento_5.png
[img visual6]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-vista-mant-razones-cambio_6.png
[img visual7]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-vista-razones-cambio-detail_7.png
[img visual8]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-confirmacion-vista-mantenimiento-creada_8.png
[img visual9]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-vista-mantenimiento-transaccion-SM30_9-1.png
[img visual10]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-vista-mantenimiento-transacion-SE93_10-1.png
[img visual11]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-transaction-with-parameters_11-1.png
[img visual12]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-asociar-transaccion_12-2.png
[img visual13]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-vista-mantenimiento-boton-SAVE.png
[img visual14]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-vista-mantenimiento-crear-paquete_13.png
[img visual15]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-vista-mantenimiento-orden-transporte_14.png
[img visual16]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-ingresar-transaccion-vista-mantenimiento_15-1.png
[img visual17]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-ingresar-transaccion-vista-mantenimiento_15-1.png
[img visual18]:http://www.teknodatips.com.ar/images/tips/ABAP-Vista-mantenimiento-y-transaccion/SAP-TIP-vista-mantenimiento-final_16-1.png