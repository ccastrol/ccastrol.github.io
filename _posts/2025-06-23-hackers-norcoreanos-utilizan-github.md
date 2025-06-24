---
layout: post
title: Hackers norcoreanos utilizan Github
author: author_01
categories:
- ciberseguridad
tags:
- hackers
- norcoreanos
- github
image:
  path: "/assets/img/Malware.jpg"
  alt: Hakers Norcoreanos utilizan Github
date: 2025-06-23 21:26 -0500
---
Expertos en ciberseguridad han alertado sobre una sofisticada campaña de ciberespionaje atribuida al grupo norcoreano Kimsuky, que emplea plataformas legítimas como GitHub y Dropbox para distribuir malware y establecer infraestructura de comando y control.

Desde marzo de 2025, se ha observado cómo los atacantes han desarrollado un enfoque altamente dirigido utilizando cuentas de GitHub con tokens de acceso personal (PAT) incrustados en su malware, lo que les permite mantener comunicación persistente y discreta con repositorios privados.

El análisis forense ha revelado que estos repositorios cumplen una doble función: albergan archivos maliciosos disfrazados de documentos legítimos y sirven como depósito para la información extraída de las víctimas, incluyendo registros de sistema y datos sensibles.

Esta campaña ha sido identificada tras la publicación de un script de PowerShell en la red social X, lo que condujo al descubrimiento de una infraestructura bien organizada que apunta a instituciones surcoreanas, con señuelos personalizados que simulan firmas legales, organismos financieros y agencias gubernamentales.


## Descripción general de la cadena de ataque:

El malware utiliza tokens PAT para acceder a repositorios privados, desde donde descarga scripts y carga archivos extraídos de los sistemas infectados en carpetas como /log y /boot. Cada archivo generado sigue un patrón único basado en IP y hora, lo que facilita el rastreo individual de víctimas.

Entre los elementos técnicos observados se encuentran documentos como onf.txt y ofx.txt, utilizados para robar información y cargarla periódicamente mediante tareas programadas. Estos mecanismos indican una operación escalable, silenciosa y altamente automatizada.

El grupo también mantiene infraestructura C2 (comando y control) en dominios falsos como sitios de phishing de Naver, y ha sido vinculado con campañas previas gracias a GUIDs compartidos y convenciones de codificación típicas de sus herramientas como XenoRAT.


## Mecanismo de infección:

El ataque comienza con correos electrónicos de phishing dirigidos, que se hacen pasar por bufetes de abogados o entidades financieras de confianza. Estos correos contienen archivos comprimidos protegidos con contraseña que incluyen scripts de PowerShell maliciosos.

Al ser ejecutados, los scripts establecen comunicación con GitHub, descargando cargas útiles comprimidas que se modifican con encabezados GZIP para evadir los motores de detección. El malware se ejecuta en memoria y evita escribir en disco para no dejar rastros.

Una tarea programada se encarga de ejecutar nuevos scripts cada 30 minutos, lo que permite a los atacantes actualizar las funcionalidades del malware, pasando de reconocimiento básico a un troyano de acceso remoto completo sin interacción adicional de la víctima.

La arquitectura modular del malware permite operar en diversas etapas: inicialización, recolección de datos, persistencia y control remoto. Este enfoque permite una evolución constante y una vigilancia prolongada del entorno comprometido.


## Conclusión:

La campaña atribuida a Kimsuky refleja una alta sofisticación operativa al utilizar plataformas legítimas como GitHub y Dropbox para evadir mecanismos de seguridad tradicionales, manteniendo control persistente mediante repositorios privados autenticados con tokens codificados. Su uso de tareas programadas, técnicas de evasión como compresión con encabezados GZIP y la personalización por objetivo revelan una planificación meticulosa centrada en el robo de información estratégica. Esta táctica subraya la necesidad de monitorear accesos a servicios en la nube y concientizar a los usuarios frente al phishing, ya que se prevé que estos métodos continúen evolucionando y representen una amenaza creciente para los equipos de ciberdefensa globales.

## Indicadores de compromiso

| Tipo                         | Valor            |
| :--------------------------- | :--------------- |
| C&C IP                       | 80.71.157[.]55, 158.247.253[.]215, 165.154.78[.]9     |
| Mutex               | Dansweit_Hk65, Cheetah_0716    |
| Email               | janman8907@gmail.com |
| .NET GUID           | 12DE1212-167D-45BA-1284-780DA98CF901  |
