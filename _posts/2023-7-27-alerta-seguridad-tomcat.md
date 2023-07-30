---
title: Los piratas informáticos apuntan a los servidores Apache Tomcat para Mirai Botnet y Crypto Mining
date: 2023-07-27 12:53:00 -0500
pin: true
math: true
mermaid: true
categories: [ciberseguridad]
tags: [tomcat, apache,mirai, botnet,crypto, mining]
render_with_liquid: false
---

Los servidores Apache Tomcat mal configurados y mal asegurados están siendo atacados como parte de una nueva campaña diseñada para entregar el malware de botnet Mirai y los mineros de criptomonedas.

Los hallazgos son cortesía de Aqua, que detectó más de 800 ataques contra sus servidores trampa Tomcat durante un período de dos años, con el 96 % de los ataques vinculados a la red de bots Mirai.

De estos intentos de ataque, el 20 % (o 152) implicó el uso de un script de shell web denominado "neww" que se originó en 24 direcciones IP únicas, de las cuales el 68 % se originó en una sola dirección IP (104.248.157[.]218).

"El actor de amenazas buscó servidores Tomcat y lanzó un ataque de fuerza bruta contra él, intentando obtener acceso al administrador de aplicaciones web de Tomcat probando diferentes combinaciones de credenciales asociadas con él", dijo el investigador de seguridad de Aqua, Nitzan Yaakov.

Al obtener un punto de apoyo exitoso, se ha observado que los actores de amenazas implementan un archivo WAR que contiene una clase de shell web maliciosa llamada 'cmd.jsp' que, a su vez, está diseñada para escuchar solicitudes remotas y ejecutar comandos arbitrarios en el servidor Tomcat.

Esto incluye descargar y ejecutar un script de shell llamado "neww", después de lo cual el archivo se elimina con el comando de Linux " rm -rf ".

"El script contiene enlaces para descargar 12 archivos binarios, y cada archivo es adecuado para una arquitectura específica según el sistema que ha sido atacado por el actor de amenazas", señaló Yaakov.

El malware de etapa final es una variante de la infame red de bots Mirai que utiliza los hosts infectados para orquestar ataques de denegación de servicio distribuido (DDoS).

"Una vez que el actor de amenazas obtuvo acceso al administrador de aplicaciones web utilizando credenciales válidas, aprovechó la plataforma para cargar un shell web disfrazado en un archivo WAR", dijo Yaakov. "Luego, el actor de amenazas ejecutó comandos de forma remota y lanzó el ataque".

El desarrollo se produce cuando el AhnLab Security Emergency Response Center (ASEC) informó que los servidores MS-SQL mal administrados están siendo violados para implementar un malware rootkit llamado Purple Fox, que actúa como un cargador para obtener malware adicional, como los mineros de monedas.

Estos hallazgos también demuestran la naturaleza lucrativa de la minería de criptomonedas, que ha experimentado un aumento del 399 % con respecto al año pasado, con 332 millones de ataques de cryptojacking registrados en la primera mitad de 2023 a nivel mundial, según SonicWall.

### Recomendaciones
> 
* Es importante adoptar una postura de ciberseguridad proactiva para agarantizar que las organizaciones esten protegidas.
* Para mitigar, se recomienda no usar contraseñas por defecto y asegurar sus entrnos, para evitar ataques de fuerza bruta.
* Asegurar su entorno con herramientas provistas de canales oficiales.
{: .prompt-tip }

### Referencias
* Fuente 1: Hackers Target Apache Tomcat Servers for Mirai Botnet and Crypto Mining
* Fuente 2: Tomcat Under Attack: Exploring Mirai Malware and Beyond
