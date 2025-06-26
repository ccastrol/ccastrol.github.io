---
layout: post
title: Vulnerabilidad del cliente web de Zimbra
author: author_01
categories:
- ciberseguridad
tags:
- zimbra
- vilnerabilidad
- javascript
image:
  path: "/assets/img/zimbra-injection.png"
  alt: zimbra con vulnerabilidades críticas, incluyendo fallas de XSS almacenado,
    inyección SQL, SSRF, DoS y LFI.
date: 2025-06-25 20:37 -0500
---
Zimbra Collaboration Suite (ZCS), ampliamente utilizada por organizaciones para la gestión de correo electrónico, ha sido afectada por múltiples vulnerabilidades críticas, incluyendo fallas de XSS almacenado, inyección SQL, SSRF, DoS y LFI. Estas fallas podrían permitir a atacantes ejecutar código arbitrario, robar credenciales, secuestrar sesiones o acceder a archivos internos del servidor. La más destacada, CVE-2025-27915, afecta al cliente web clásico de Zimbra y permite ejecutar JavaScript malicioso en el navegador de la víctima sin interacción adicional.
 

## ID CVE

CVE-2025-25064 – Inyección SQL en el endpoint ZimbraSync
CVE-2025-27915 – XSS almacenado (ejecución JavaScript en archivos ICS)
CVE-2024-45516 – XSS almacenado en contenido HTML compartido
CVE-2025-25065 – En el analizador de fuentes RSS que permite la redirección de red interna, corregido en el parche 43 de 9.0.0 y 10.0.12.
CVE-2024-54663 – Permite el acceso no autorizado a archivos a través de /h/restun punto final, resuelto en 10.0.11 y 10.1.3.
DoS sin ID CVE reportado – Interrupción del servicio desde la consola administrativa

## Versiones afectadas:

Zimbra 9.0.0 hasta Patch 43 (recomendado: Patch 46)
Zimbra 10.0.0 hasta 10.0.12 (recomendado: 10.0.15)
Zimbra 10.1.0 hasta 10.1.4 (recomendado: 10.1.9)

## Descripción de la cadena de ataque:

Los atacantes envían correos con archivos ICS manipulados o elementos HTML maliciosos. Cuando las víctimas abren invitaciones de calendario o acceden a contenido compartido, se ejecuta JavaScript arbitrario. En el caso del XSS almacenado, el código malicioso se aloja en el servidor y se activa automáticamente al acceder a la interfaz web. Esto permite robar cookies, redirigir correos, secuestrar sesiones o aplicar reglas de reenvío hacia direcciones controladas por el atacante. En paralelo, otras vulnerabilidades como la inyección SQL permiten extraer metadatos de correos confidenciales y realizar acciones como denegación de servicio o lectura de archivos internos.


## Mecanismo de infección:

El ataque se origina desde contenidos manipulados como archivos ICS maliciosos enviados por correo. Al ser abiertos en el cliente web clásico, se ejecutan eventos JavaScript embebidos en etiquetas HTML (<details ontoggle>), permitiendo el control de la sesión del usuario. Otras vulnerabilidades, como la SQLi y la LFI, explotan endpoints específicos (por ejemplo, ZimbraSync y /h/rest) para ejecutar comandos o acceder a información sin autenticación suficiente. La persistencia del XSS almacenado lo hace particularmente peligroso, ya que se activa sin requerir interacción constante.


## Solución:

Actualizar inmediatamente a las versiones parchadas oficiales:

9.0.0 Patch 46
10.0.15
10.1.9
Además, aplicar nuevas configuraciones de sanitización y políticas CSP para prevenir futuras inyecciones.

 	
## Referencias

- Fuente 1: <https://cybersecuritynews.com/zimbra-classic-web-client-vulnerability/>
- Fuente 2: <https://cyberpress.org/zimbra-classic-web-client-flaw/>