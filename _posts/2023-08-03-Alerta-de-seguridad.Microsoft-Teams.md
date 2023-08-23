---
title: Alerta de Seguridad -Microsoft expone las tácticas furtivas de phishing de los piratas informáticos rusos a través de los chats de Microsoft Teams
date: 2023-08-03 11:33:00 +0800
categories: [CIBERSEGURIDAD]
tags: [microsoft, teams, phishing]
math: true
mermaid: true
toc: true
image:
  path: /assets/images/Alerta-microsoft-teams/teams.jpg
---

Microsoft ha revelado este miércoles que ha identificado una serie de ataques de ingeniería social muy selectivos perpetrados por un agente ruso que utiliza señuelos de phishing para el robo de credenciales enviados a través de chats de Microsoft Teams.

El gigante de la tecnología atribuyó los ataques a un grupo que rastrea como Midnight Blizzard (anteriormente Nobelium). También se le conoce como APT29, BlueBravo, Cozy Bear, Iron Hemlock y The Dukes.

"En esta última actividad, el actor de la amenaza utiliza inquilinos de Microsoft 365 previamente comprometidos propiedad de pequeñas empresas para crear nuevos dominios que aparecen como entidades de soporte técnico", dijo la compañía.

"Usando estos dominios de inquilinos comprometidos, Midnight Blizzard aprovecha los mensajes de Teams para enviar señuelos que intentan robar credenciales de una organización objetivo al involucrar a un usuario y obtener la aprobación de los avisos de autenticación de múltiples factores (MFA)."

Microsoft dijo que la campaña, observada desde al menos finales de mayo de 2023, afectó a menos de 40 organizaciones en todo el mundo que abarcan los sectores de gobierno, organizaciones no gubernamentales (ONG), servicios de TI, tecnología, fabricación discreta y medios de comunicación.

Se ha observado que el actor de la amenaza utiliza técnicas de robo de tokens para el acceso inicial a los entornos objetivo, junto con otros métodos como el spear-phishing de autenticación, el rociado de contraseñas y los ataques de fuerza bruta.

Otro rasgo distintivo conocido es su explotación de entornos locales para trasladarse lateralmente a la nube, así como el abuso de la cadena de confianza de los proveedores de servicios para obtener acceso a clientes posteriores, como se observó en el hackeo de SolarWinds de 2020.

En la nueva ronda de ataques vinculados a Midnight Blizzard, se añade un nuevo subdominio onmicrosoft.com a un inquilino previamente comprometido en ataques, seguido de la creación de un nuevo usuario con ese subdominio para iniciar una solicitud de chat de Teams con objetivos potenciales haciéndose pasar por una persona de soporte técnico o el equipo de Protección de Identidad de Microsoft.

"Si el usuario acepta la solicitud de mensaje, recibe un mensaje de Microsoft Teams del atacante intentando convencerle de que introduzca un código en la aplicación Microsoft Authenticator de su dispositivo móvil", explica Microsoft.

Si la víctima sigue las instrucciones, el actor de la amenaza recibe un token para autenticarse como el usuario objetivo, lo que permite la toma de control de la cuenta y la actividad posterior al ataque.

"En algunos casos, el actor intenta añadir un dispositivo a la organización como dispositivo gestionado a través de Microsoft Entra ID (anteriormente Azure Active Directory), probablemente un intento de eludir las políticas de acceso condicional configuradas para restringir el acceso a recursos específicos sólo a los dispositivos gestionados", advirtió Microsoft.

Los hallazgos se producen días después de que se atribuyera al actor de la amenaza ataques de phishing dirigidos a entidades diplomáticas de toda Europa del Este con el objetivo de entregar un nuevo backdoor llamado GraphicalProton.

También siguen al descubrimiento de varios nuevos vectores de ataque Azure AD (AAD) Connect que podrían permitir a ciberactores maliciosos crear una puerta trasera indetectable robando hashes criptográficos de contraseñas mediante la inyección de código malicioso en un proceso de sincronización de hash e interceptando credenciales mediante un ataque adversary-in-the-middle (AitM).

"Por ejemplo, los atacantes pueden aprovechar la extracción de hashes NT para asegurarse de que reciben cada cambio de contraseña futuro en el dominio", dijo Sygnia en una declaración compartida con The Hacker News.

"Los actores de amenazas también pueden utilizar [Active Directory Certificate Services] para obtener las contraseñas de AAD Connector, así como servir como un man-in-the-middle y lanzar ataques contra los canales cifrados SSL en la red mediante la explotación de configuraciones erróneas en las plantillas de certificados que tienen autenticación de servidor."

### Recomendaciones
>
* Adoptar postura de ciberseguridad proactiva.
* Verificar que los equipos de seguridad esten con sus firmas actualizadas.
* Matener el conocimiento situacional de las últimas amenazas y brechas dentro de la organización.
* Mantener protocolo estricto de actualizaciones.
* Procurar tener siempre activo el firewall.
* Desactivar comunicación con dominios externos.
* Si es necesario mantener los canales de comunicación externos, las organizaciones pueden definir dominios específicos en una lista de permitidos para reducir el riesgo de explotación.
{: .prompt-tip }

### Fuentes.
Fuente 1: https://thehackernews.com/2023/08/microsoft-exposes-russian-hackers.html

