---
title: Protocolo ICMP
date: 2020-05-05 00:13:31
tags:
- [Redes2]
categories:
- [Redes2]
- [Computacion]
---

<h2>¿Qué es ICMP?</h2>
<p align="justify">
    Corresponde a sus siglas en inglés Internet Control Message Protocol. Como su nombre lo dice, es el protocolo encargado del 
    envío de los mensajes de internet. ICMP es un protocolo de nivel de transporte dentro de TCP / IP que comunica información 
    sobre problemas de conectividad de red a la fuente 
    <!-- more --> 
    de la transmisión comprometida. Envía mensajes de control tales como la 
    red de destino inalcanzable, la ruta de origen falló y el apagado de origen. Utiliza una estructura de paquete de datos con 
    un encabezado de 8 bytes y una sección de datos de tamaño variable.
</p>
</br>
{% image fancybox /assets/images/ICMP/principal.jpg ICMP %}
</br>
<h2>¿Cómo funciona?</h2>
<p align="justify">
    ICMP es utilizado por un dispositivo, como un enrutador, para comunicarse con la fuente de un paquete de datos sobre problemas de transmisión. Por ejemplo, si no se entrega un datagrama, ICMP podría informarlo al host con detalles para ayudar a ver dónde salió mal la transmisión. Es un protocolo que cree en la comunicación directa en el lugar de trabajo.
</p>
</br>
<h2>PING</h2>
<p align="justify">
    Ping utiliza mensajes ICMP para informar información sobre conectividad de red y la velocidad de transmisión de datos entre un host y una computadora de destino. Es uno de los pocos casos en los que un usuario puede interactuar directamente con ICMP, que generalmente solo funciona para permitir que las computadoras en red se comuniquen entre sí automáticamente.
</p>
</br>
<h2>Otros usos</h2>
<p align="justify">
    El objetivo principal de ICMP es informar de errores. Cuando dos dispositivos se conectan a través de Internet, el ICMP genera errores para compartir con el dispositivo emisor en caso de que alguno de los datos no llegue a su destino previsto.
</p>
<p align="justify">
    Un uso secundario del protocolo ICMP es realizar diagnósticos de red; Las utilidades de terminal de uso común traceroute y ping funcionan con ICMP. La utilidad traceroute se usa para mostrar la ruta de enrutamiento entre dos dispositivos de Internet. La ruta de enrutamiento es la ruta física real de los enrutadores conectados que una solicitud debe atravesar antes de llegar a su destino. El viaje entre un enrutador y otro se conoce como "salto", y un traceroute también informa el tiempo requerido para cada salto en el camino. Esto puede ser útil para determinar las fuentes de retraso de la red.
</p>
</br>
{% image fancybox /assets/images/ICMP/diagrama.png Usos %}
<p align="justify">
    La utilidad ping es una versión simplificada de traceroute. Un ping probará la velocidad de la conexión entre dos dispositivos e informará exactamente cuánto tiempo tarda un paquete de datos en llegar a su destino y volver al dispositivo del remitente. Aunque el ping no proporciona datos sobre el enrutamiento o los saltos, sigue siendo una métrica muy útil para medir la latencia entre dos dispositivos. Los mensajes de solicitud de eco y respuesta de eco ICMP se usan comúnmente con el fin de realizar un ping. Lamentablemente, los ataques a la red pueden explotar este proceso, creando medios de interrupción como el ICMP Flood Attack y el Ping of Death attack.
</p>
</br>
{% alert warning icon %}
Para poder realizar este tutorial es necesario tener GNS3 instalado
{% endalert %}
</br>
<h2>Ejemplo del uso de ICMP a través de un PING</h2>
<p align="justify">
    En la siguiente imagen se muestra la topología del ejemplo.  
</p>
</br>
{% image fancybox /assets/images/ICMP/1.png Paso 1 %}
<p align="justify">
    Se debe de configurar el segundo puerto de manera troncal y los demás de tipo acceso en el etherswitch 1.
</p>
</br>
{% image fancybox /assets/images/ICMP/2.png Paso 2 %}
<p align="justify">
    Se debe de configurar el segundo puerto de manera troncal y los demás de tipo acceso en el etherswitch 2.
</p>
</br>
{% image fancybox /assets/images/ICMP/3.png Paso 3 %}
<p align="justify">
    Configuramos la ip de la PC1 con los siguientes comandos.
</p>
</br>
{% include_code Comandos ICMP lang:html from:1 to:4 ICMP.cfg %}
</br>
{% image fancybox /assets/images/ICMP/4.png Paso 4 %}
<p align="justify">
    Configuramos la ip de la PC2 con los siguientes comandos.
</p>
</br>
{% include_code Comandos ICMP lang:html from:6 to:9 ICMP.cfg %}
</br>
{% image fancybox /assets/images/ICMP/5.png Paso 5 %}
<p align="justify">
    Configuramos la ip de la PC3 con los siguientes comandos.
</p>
</br>
{% include_code Comandos ICMP lang:html from:11 to:14 ICMP.cfg %}
</br>
{% image fancybox /assets/images/ICMP/6.png Paso 6 %}
<p align="justify">
    Configuramos la ip de la PC4 con los siguientes comandos.
</p>
</br>
{% include_code Comandos ICMP lang:html from:16 to:19 ICMP.cfg %}
</br>
{% image fancybox /assets/images/ICMP/7.png Paso 7 %}
<p align="justify">
    Validamos la configuración de la PC1 con los siguientes comandos.
</p>
</br>
{% include_code Comandos ICMP lang:html from:21 to:24 ICMP.cfg %}
</br>
{% image fancybox /assets/images/ICMP/8.png Paso 8 %}
<p align="justify">
    Validamos la configuración de la PC2 con los siguientes comandos.
</p>
</br>
{% include_code Comandos ICMP lang:html from:26 to:29 ICMP.cfg %}
</br>
{% image fancybox /assets/images/ICMP/9.png Paso 9 %}
<p align="justify">
    Validamos la configuración de la PC3 con los siguientes comandos.
</p>
</br>
{% include_code Comandos ICMP lang:html from:31 to:34 ICMP.cfg %}
</br>
{% image fancybox /assets/images/ICMP/10.png Paso 10 %}
<p align="justify">
    Validamos la configuración de la PC4 con los siguientes comandos.
</p>
</br>
{% include_code Comandos ICMP lang:html from:36 to:39 ICMP.cfg %}
</br>
{% image fancybox /assets/images/ICMP/11.png Paso 11 %}
<p align="justify">
    Todos los comandos utilizados se muestran a continuación.
</p>
</br>

{% include_code Comandos ICMP lang:html ICMP.cfg %}


