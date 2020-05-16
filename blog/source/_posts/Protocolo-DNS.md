---
title: Protocolo DNS
date: 2020-05-05 00:14:20
tags:
- [Redes2]
categories:
- [Redes2]
- [Computacion]
---

<h2>¿Qué es DNS?</h2>
<p align="justify">
    Significa Domain Name System y se le dió este nombre ya que en el mundo del internet, las páginas web son identificadas
    por una dirección ip en lugar de un nombre. Pero resulta más dificil para el ser humano aprenderse las ip.
    <!-- more --> 
    Por esta razón, se creó el DNS; para que fuera más sencillo accesar a una página web mediante el uso de un nombre en lugar
    de una dirección IP. 
</p>
{% image fancybox /assets/images/DNS/portada.png DNS %}
</br>
<h2>¿Cómo funciona DNS?</h2>
<p align="justify">
    DNS básicamente es el encargado de convertir una dirección web ingresada por un usuario a la ip que le fue asignada a ese sitio
    para que el usuario pueda ser redirigido a este. El proceso inicia cuando el usuario ingresa la dirección de la página web. Esta
    dirección es comparada con las que han sido almacenadas en la memoria cache para encontrar la ip. Si no se encuentra en la memoria,
    envía una solicitud al servidor que es el proveedor de internet de cada ordenador. Al recibir la solicitud el servidor, busca en
    su memoria cache en busca de una ip que concuerde con la dirección web enviada. Si no puede encontrar la dirección, este envía una
    solicitud al servidor root de los cuales existen 13 en total que estan colocados alrededor del mundo, son operados por 12 organiza
    ciones diferentes y cada uno tiene su propia dirección IP. El servidor root al recibir la solicitud, no sabe cual es la ip pero si
    sabe en donde exactamente se debe enviar la solicitud para obtenerla. Entonces el servidor root lo redirige al servidor top-level domain (TLD) y este le envía la solicitud a dicho servidor. El servidor TLD almacena información de los dominios top como ".com, 
    .net, .org, etc.". Sin embargo, este servidor no contiene la dirección que se ha solicitado entonces lo redirige al servidor de
    nombres. Este servidor contiene toda la información del dominio incluyendo la ip. Por consiguiente, este al recibir la solicitud,
    envia de vuelta la ip de la dirección web solicitada, este la envía de vuelta al ordenador del usuario y la almacena en su memoria
    cache. 
</p>
</br>
{% image fancybox /assets/images/DNS/Proceso.png Proceso DNS %}
</br>
{% image fancybox /assets/images/DNS/mundo.jpg Servidores %}
</br>
<p>
    En la siguiente imagen, se puede observar un ejemplo de la estructura de árbol en la que están organizados los DNS.
</p>
{% image fancybox /assets/images/DNS/arbol.jpg Estructura %}
</br>
</br>
{% alert warning icon %}
Para poder realizar este tutorial es necesario tener GNS3 instalado y haber configurado al GNS3VM
{% endalert %}
</br>
<h2>Ejemplo de configuración de un servidor DNS en una red GNS3</h2>
<p align="justify">
    El primer paso es descargar el appliance de DNS del sitio oficial de GNS3.
</p>
</br>
{% image fancybox /assets/images/DNS/1.png Paso 1 %}
</br>
<p align="justify">
    Posteriormente, debemos importar el appliance a GNS3 seleccionando la opción de "Import appliance" en el menú de "file".
</p>
</br>
{% image fancybox /assets/images/DNS/2.png Paso 2 %}
</br>
<p align="justify">
    Seleccionamos el archivo que descargamos del appliance.
</p>
</br>
{% image fancybox /assets/images/DNS/3.png Paso 3 %}
</br>
<p align="justify">
    Nos solicitará instalarla utilizando la máquina virtual de GNS3 y le damos en siguiente.
</p>
</br>
{% image fancybox /assets/images/DNS/4.png Paso 4 %}
</br>
<p align="justify">
    Nos mostrará un ejemplo de como crear dominios asociados a ip. Es importante que guardemos este formato ya que nos servirá más adelante.
</p>
</br>
{% image fancybox /assets/images/DNS/5.png Paso 5 %}
</br>
<p align="justify">
    Nos mostrará un mensaje de confirmación y seleccionamos "finish".
</p>
</br>
{% image fancybox /assets/images/DNS/6.png Paso 6 %}
</br>
<p align="justify">
    Luego podemos observar que en la sección de dispositivos finales, se ha agregado el servidor DNS.
</p>
</br>
{% image fancybox /assets/images/DNS/7.png Paso 7 %}
</br>
<p align="justify">
    Lo arrastramos y colocamos en nuestro proyecto.
</p>
</br>
{% image fancybox /assets/images/DNS/8.png Paso 8 %}
</br>
<p align="justify">
    Colocamos dos routers comunes y un etherswitch en la topología para efectos del ejemplo y realizamos las conexiones que se muestran a continuación.
</p>
</br>
{% image fancybox /assets/images/DNS/9.png Paso 9 %}
</br>
<p align="justify">
    Le damos click derecho al servidor DNS y seleccionamos la opción de "Edit config"
</p>
</br>
{% image fancybox /assets/images/DNS/10.png Paso 10 %}
</br>
<p align="justify">
    Nos mostrará una configuración inicial y presionamos en guardar.
</p>
</br>
{% image fancybox /assets/images/DNS/11.png Paso 11 %}
</br>
<p align="justify">
    Luego nos mostrará la configuración de las interfaces de DNS.
</p>
</br>
{% image fancybox /assets/images/DNS/12.png Paso 12 %}
</br>
<p align="justify">
    Modificamos el archivo de configuración como se muestra a continuación.
</p>
</br>
{% image fancybox /assets/images/DNS/13.png Paso 13 %}
</br>
<p align="justify">
    Procedemos a apagar el servidor.
</p>
</br>
{% image fancybox /assets/images/DNS/14.png Paso 14 %}
</br>
<p align="justify">
    Lo volvemos a encender.
</p>
</br>
{% image fancybox /assets/images/DNS/15.png Paso 15 %}
</br>
<p align="justify">
    Le damos click derecho nuevamente y seleccionamos la opción de "Custom console".
</p>
</br>
{% image fancybox /assets/images/DNS/16.png Paso 16 %}
</br>
<p align="justify">
    Se nos abrirá la consola del servidor.
</p>
</br>
{% image fancybox /assets/images/DNS/17.png Paso 17 %}
</br>
<p align="justify">
    Ingresamos el comando mostrado abajo para validar las configuraciones realizadas.
</p>
</br>
{% include_code Comandos DNS lang:html from:1 to:2 DNS.cfg %}
</br>
{% image fancybox /assets/images/DNS/18.png Paso 18 %}
</br>
<p align="justify">
    Agregamos una NAT de los dispositivos disponibles.
</p>
</br>
{% image fancybox /assets/images/DNS/19.png Paso 19 %}
</br>
<p align="justify">
    Nos mostrara una opción para seleccionar el servidor. Seleccionamos el de la máquina virtual de GNS3.
</p>
</br>
{% image fancybox /assets/images/DNS/20.png Paso 20 %}
</br>
<p align="justify">
    Conectamos la NAT al etherswitch.
</p>
</br>
{% image fancybox /assets/images/DNS/21.png Paso 21 %}
</br>
<p align="justify">
    Validamos la configuraciones haciendo ping a la NAT y a un dominio cualquiera. En este caso utilizamos google.com.
</p>
</br>
{% include_code Comandos DNS lang:html from:4 to:7 DNS.cfg %}
</br>
{% image fancybox /assets/images/DNS/22.png Paso 22 %}
</br>
{% image fancybox /assets/images/DNS/23.png Paso 23 %}
</br>
<p align="justify">
    Modificamos el archivo donde estan los DNS existentes utilizando los siguientes comandos y guardamos los cambios.
</p>
</br>
{% include_code Comandos DNS lang:html from:9 to:13 DNS.cfg %}
</br>
{% image fancybox /assets/images/DNS/24.png Paso 24 %}
</br>
{% image fancybox /assets/images/DNS/25.png Paso 25 %}
</br>
{% image fancybox /assets/images/DNS/26.png Paso 26 %}
</br>
<p align="justify">
    Luego, procedemos a configurar la ip del router 1 en la interfaz 0/0 utilizando los siguientes comandos.
</p>
</br>
{% include_code Comandos DNS lang:html from:15 to:22 DNS.cfg %}
</br>
{% image fancybox /assets/images/DNS/27.png Paso 27 %}
</br>
<p align="justify">
    Luego, procedemos a configurar la ip del router 2 en la interfaz 0/0 utilizando los siguientes comandos.
</p>
</br>
{% include_code Comandos DNS lang:html from:24 to:31 DNS.cfg %}
</br>
{% image fancybox /assets/images/DNS/28.png Paso 28 %}
</br>
<p align="justify">
    Finalmente, realizamos un ping desde el servidor para validar que se configuraciones de las ip se realizaron correctamente utilizando los siguientes comandos.
</p>
</br>
{% include_code Comandos DNS lang:html from:33 to:36 DNS.cfg %}
</br>
{% image fancybox /assets/images/DNS/29.png Paso 29 %}
</br>
<p align="justify">
    Puede ver todos los comandos utilizados a continuación.
</p>
</br>
{% include_code Comandos DNS lang:html DNS.cfg %}
</br>