---
title: Ruteo dinamico OSPF
date: 2020-05-05 00:14:05
tags:
- [Redes2]
categories:
- [Redes2]
- [Computacion]
---

<h2>¿Qué es OSPF?</h2>

<p align="justify">
    Su nombre corresponde a Open Shortest Path First que es un protocolo utilizado para redistribuir información en una 
    red. Este protocolo parte de la tecnología link-state que es basada en los algoritmos Bellman-Ford que eran
    utilizados en los protocolos de ruteo de internet tradicionales como RIP. Este protocolo ha introducido nuevos
    conceptos como autenticación de actualización de rutas, máscaras de subred de tamaño variable (VLSM), entre otros.
    Este protocolo due desarrollado debido a la necesidad de la necesidad en la comunidad de internet de utilizar un 
    protocolo de alta funcionalidad para el grupo de protocolos TCP/IP.
</p>
</br>
{% image fancybox /assets/images/OSPF/principal.jpg OSPF %}
</br>
<p align="justify">
    En la siguiente tabla se puede observar una comparación entre RIP y OSPF:
</p>
</br>
<table>
    <caption>Comparación entre RIP y OSPF</caption>
    <tr>
        <th>RIP</th>
        <th>OSPF</th>
    </tr>
    <tr>
        <td>Tiene un límite de 15 saltos. Una red RIP que tiene más de 15 saltos es considerada inalcanzable.</td>
        <td>No existe límite en la cantidad de saltos.</td>
    </tr>
    <tr>
        <td>No es capaz de manejar VLSM.</td>
        <td>Es capaz de manejar inteligentemente VLSM.</td>
    </tr>
    <tr>
        <td>El protocolo de ruteo utiliza el algoritmo de vector de distancias.</td>
        <td>El protocolo de ruteo utiliza el algoritmo del camino más corto Dijksta.</td>
    </tr>
    <tr>
        <td>Las redes son clasificadas en áreas y tablas.</td>
        <td>Las redes son clasificadas en áreas, sub áreas y sistemas autónomos.</td>
    </tr>
    <tr>
        <td>Es un protocolo simple.</td>
        <td>Es un protocolo complejo.</td>
    </tr>
    <tr>
        <td>Se adapta mejor a pequeñas redes debido a la cantidad máxima de saltos.</td>
        <td>Se adapta mejor a redes grandes debido a la cantidad máxima de saltos.</td>
    </tr>
    <tr>
        <td>Tiene lenta convergencia.</td>
        <td>Tiene rápida convergencia.</td>
    </tr>
    <tr>
        <td>Utiliza menos memoria y CPU.</td>
        <td>Utiliza mucha memoria y CPU.</td>
    </tr>
    <tr>
        <td>Consume mucho ancho de banda porque toda la tabla de ruteo es enviada.</td>
        <td>Consume poco ancho de banda porque solo manda pequeñas actualizaciones.</td>
    </tr>
</table>
</br>
{% alert warning icon %}
Para poder realizar este tutorial es necesario tener GNS3 instalado
{% endalert %}
</br>
<h2>Ejemplo de configuración de OSPF en una red pequeña</h2>
</br>
{% image fancybox /assets/images/OSPF/Topologia.png Topologia %}
{% include_code Comandos OSPF lang:html OSPF.cfg %}