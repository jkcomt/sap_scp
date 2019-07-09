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
</p>
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

