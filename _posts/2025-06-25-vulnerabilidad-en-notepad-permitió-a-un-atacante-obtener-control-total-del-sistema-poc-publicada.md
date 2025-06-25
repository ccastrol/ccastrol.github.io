---
layout: post
title: Vulnerabilidad en Notepad++ permitió a un atacante obtener control total del
  sistema – PoC publicada
author: author_01
categories:
- ciberseguridad
tags:
- notepad++
- Poc
- vulnerabilidad
image:
  path: "/assets/img/notepad++.png"
  alt: Notepad++ vulnerabilidad CVE-2025-49144
date: 2025-06-25 14:34 -0500
---
Una grave falla de escalamiento de privilegios ha sido identificada en el instalador de Notepad++ versión 8.8.1, ampliamente utilizado en entornos corporativos y por profesionales de TI. La vulnerabilidad, identificada como CVE-2025-49144, permite a atacantes ejecutar código malicioso con privilegios de sistema (NT AUTHORITY\SYSTEM), comprometiendo totalmente el equipo afectado.

El problema radica en el comportamiento inseguro del instalador al buscar archivos ejecutables sin validar su ruta, lo que permite ataques de tipo binary planting. Si un atacante coloca un ejecutable malicioso (por ejemplo, regsvr32.exe) en la misma carpeta donde se encuentra el instalador, este será cargado automáticamente con privilegios elevados durante la instalación, sin necesidad de interacción adicional del usuario.
 

## ID CVE

- CVE-2025-49144 (CVSS: 7.3, Alta gravedad)
- Producto afectado: Notepad++ v8.8.1 (y versiones anteriores)
- Versión corregida:   Notepad++ v8.8.2
 

## Descripción de la cadena de ataque:

Durante el proceso de instalación, Notepad++ v8.8.1 busca dependencias ejecutables en el directorio actual de trabajo en lugar de usar rutas absolutas. Esto expone al sistema a cargas maliciosas si se ejecuta desde ubicaciones como la carpeta "Descargas", donde un atacante podría haber colocado un archivo comprometido.
 
La explotación consiste en tres pasos: el atacante ubica un ejecutable malicioso junto al instalador legítimo, el usuario lo ejecuta sin sospechar, y el sistema otorga privilegios elevados al código malicioso. Este proceso ha sido demostrado mediante un Proof-of-Concept (PoC) disponible públicamente, incluyendo registros de Process Monitor y videos de explotación con acceso reverso a shell. 
 

## Mecanismo de infección:

Colocación de binario malicioso en el mismo directorio que el instalador legítimo.
 

Instalador ejecuta el archivo sin verificación de ruta (ej. regsvr32.exe).
 

El atacante obtiene acceso total al sistema con privilegios SYSTEM.
 

Este tipo de ataque se ha vuelto cada vez más frecuente en campañas de cadena de suministro, dado su bajo nivel de complejidad y alto impacto.

 

## Solución:

Los desarrolladores de Notepad++ lanzaron la versión 8.8.2 que corrige esta falla mediante el uso de rutas absolutas y prácticas seguras de carga de bibliotecas, conforme a las recomendaciones de Microsoft.

	
## Referencias

- Fuente 1: <https://cybersecuritynews.com/notepad-vulnerability/>
- Fuente 2: <https://gbhackers.com/notepad-vulnerability/>
- Fuente 3: <https://intruceptlabs.com/2025/06/privilege-escalation-in-notepad-v8-8-1-installer-via-binary-planting-with-public-poc-available/>