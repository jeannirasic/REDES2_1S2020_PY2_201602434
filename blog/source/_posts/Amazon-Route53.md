---
title: Amazon Route53
date: 2020-05-05 00:14:38
tags:
- [Redes2]
- [Amazon]
categories:
- [Redes2]
- [Computacion]
---

<h2>¿Qué es Amazon Route 53?</h2>
<p align="justify">
    Amazon Route 53 es un servicio web de Sistema de nombres de dominio (DNS) en la nube. Su función es proporcionar a los desarrolladores y las empresas una segura de enrutar a los usuarios finales a las aplicaciones de Internet mediante la traducción de direcciones web a las direcciones IP.
    <!-- more --> 
    Amazon Route 53 es capaz de realizar una conexión de las solicitudes realizadas por los usuarios con los productos que tiene AWS como
    las instancias de Amazon EC2, los buckets de Amazon S3, entre otros. La manera en la que Amazon Route 53 maneja el tráfico ayuda al usuario a que tenga una administración más sencilla del tráfico mundial con el uso de diferentes tipos de enrutamiento, el mantenimientom entre otros. Otra de las funciones que ofrece es registrar y comprar nuevos dominios y realizar una configuración automática del mismo.
</p>

{% image fancybox /assets/images/Route53/estructura.jpeg Route 53 %}
</br>
<h2>Beneficios</h2>
<h4>Es altamente disponible y confiable</h4>
<p align="justify">
    Amazon Route 53 se creó utilizando la infraestructura altamente disponible y confiable de AWS. Los servidores DNS ayudan a garantizar una capacidad para enrutar a sus usuarios finales a su aplicación. Aplicaciones como Amazon Route 53 Traffic Flow ayudan a mejorar la confiabilidad con una configuración sencilla para redirigir a sus usuarios a una ubicación diferente si el punto final de la aplicación principal no está disponible. Amazon Route 53 está diseñado para brindar el nivel de confiabilidad que requieren las aplicaciones importantes.
</p>
</br>
<h4>Es flexible</h4>
<p align="justify">
    Amazon Route 53 Traffic Flow enruta el tráfico con base a diferentes criterios, como el estado del punto final, la ubicación geográfica y la latencia. Todo esto se puede configurar para decidir qué políticas están activas en un momento dado. Esto se puede realizar utilizando la consola de Route 53, AWS SDK o la API de Route 53. Se mantienen un historial de los cambios realizados en sus políticas para poder regresar a una versión anterior de ser necesario.
</p>
</br>
<h4>Está diseñado para ser utilizados con otros servicios web de Amazon</h4>
<p align="justify">
    Amazon Route 53 está diseñado para funcionar bien con otros productos de AWS. Se puede usar Amazon Route 53 para asignar nombres de dominio a sus instancias de Amazon EC2, buckets de Amazon S3, distribuciones de Amazon CloudFront y otros recursos de AWS. 
    Al utilizar el servicio AWS Identity and Access Management (IAM) con Amazon Route 53, obtiene un control detallado sobre quién puede actualizar los datos DNS. 
</p>
</br>
<h4>Es simple</h4>
<p align="justify">
    Con el registro de autoservicio, Amazon Route 53 puede comenzar a responder las consultas de DNS en cuestión de minutos. Se pueden configurar los ajustes de DNS con la consola de administración de AWS. También se puede integrar mediante la programación de la API de Amazon Route 53 en la aplicación web general. Amazon Route 53 Traffic Flow facilita la configuración de una lógica de enrutamiento sofisticada para las aplicaciones mediante el uso del sencillo editor visual de políticas.
</p>
</br>
<h4>Es rápido</h4>
<p align="justify">
    Utilizando una red global de servidores DNS en todo el mundo, Amazon Route 53 está diseñado para enrutar automáticamente a sus usuarios a la ubicación óptima según las condiciones de la red. Este ofrece baja latencia de consulta para sus usuarios finales, así como baja latencia de actualización para sus necesidades de administración de registros DNS. Amazon Route 53 Traffic Flow permite mejorar aún más la experiencia de sus clientes ejecutando su aplicación en múltiples ubicaciones en todo el mundo y utilizando políticas de tráfico para garantizar que sus usuarios finales sean enrutados al punto final saludable más cercano para su aplicación.
</p>
</br>
<h4>Es económico</h4>
<p align="justify">
    Amazon Route 53 le transmite los beneficios de la escala de AWS. Solo se paga por los recursos que se usan, como la cantidad de consultas que el servicio responde para cada uno de sus dominios, zonas alojadas para administrar dominios a través del servicio y características opcionales como políticas de tráfico y controles de salud.
</p>
</br>
<h4>Es seguro</h4>
<p align="justify">
    Al integrar Amazon Route 53 con AWS Identity and Access Management (IAM), se pueden otorgar credenciales únicas y administrar permisos para cada usuario dentro de la cuenta de AWS y especificar quién tiene acceso a qué partes del servicio Amazon Route 53.
</p>
</br>
<h4>Es escalable</h4>
<p align="justify">
    Route 53 está diseñado para escalar automáticamente para manejar volúmenes de consulta muy grandes sin ninguna intervención.
</p>
</br>

{% alert warning icon %}
Para poder realizar este tutorial es necesario haber creado un bucket en Amazon S3 y haber comprado un dominio externo anteriormente
{% endalert %}
</br>
<h2>Ejemplo de configuración de un dominio externo en Amazon Route 53</h2>
<p>
    Primero ingresamos en nuestra cuenta de AWS, ingresamos a la consola de aws y buscamos la opción de Route 53.
</p>
</br>
{% image fancybox /assets/images/Route53/1.png Paso 1 %}
</br>
<p>
    Se muestra un menú con opciones y seleccionamos la opción de "Get Started Now" en "DNS Management".
</p>
</br>
{% image fancybox /assets/images/Route53/2.png Paso 2 %}
</br>
<p>
    Del menú de la izquierda seleccionamos "Hosted zones" y seleccionamos la opción de "Create Hosted Zone".
</p>
</br>
{% image fancybox /assets/images/Route53/3.png Paso 3 %}
</br>
<p>
    Se mostrará una ventana similar y volvemos a seleccionar la opción de "Create hosted zone".
</p>
</br>
{% image fancybox /assets/images/Route53/4.png Paso 4 %}
</br>
<p>
    Se desplegará un menú del lado derecho y en él debemos ingresar el nombre de nuestro dominio creado previamente, ingresar opcionalmente un comentario y seleccionar la opción "Public Hosted Zone" del menú de opciones de "Type". Posteriormente, 
    presionamos el botón de "Create".
</p>
</br>
{% image fancybox /assets/images/Route53/5.png Paso 5 %}
</br>
{% image fancybox /assets/images/Route53/6.png Paso 6 %}
</br>
<p>
    Se nos mostrará la "Hosted zone" creada.
</p>
</br>
{% image fancybox /assets/images/Route53/7.png Paso 7 %}
</br>
<p>
    Después seleccionamos la opción de "Import zone file" e ingresamos el archivo que obtuvimos de nuestro proveedor de DNS.
</p>
</br>
{% image fancybox /assets/images/Route53/8.png Paso 8 %}
</br>
<p>
    Después de esto, se nos debería de crear un "Record Set" automáticamente o podemos crearlo manualmente. Y ahí seleccionamos
    el bucket que habiamos creado anteriormente. 
</p>
</br>
{% image fancybox /assets/images/Route53/9.png  Paso 9 %}
</br>
<p>
    Finalmente, se guardan los cambios y ya se puede ver nuestro sitio web con el dns configurado.
</p>
</br>
{% image fancybox /assets/images/Route53/10.png Paso 10 %}
</br>