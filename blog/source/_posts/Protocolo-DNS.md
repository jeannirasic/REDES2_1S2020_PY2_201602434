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

<p>

    
</p>