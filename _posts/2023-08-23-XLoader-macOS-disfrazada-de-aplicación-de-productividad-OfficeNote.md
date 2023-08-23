---
title: Nueva variante del malware XLoader macOS disfrazada de aplicación de productividad 'OfficeNote'
date: 2023-08-23 14:34:00 -0500
categories: [CIBERSEGURIDAD]
tags: [macos, apple, ios, officenote, malware]
render_with_liquid: false
toc: true
image:
  path: /assets/images/alertas/ios-onenote.png
---

Ha aparecido una nueva variante de un malware de Apple macOS llamado XLoader , enmascarando sus características maliciosas bajo la apariencia de una aplicación de productividad de oficina llamada "OfficeNote".

"La nueva versión de XLoader se incluye dentro de una imagen de disco estándar de Apple con el nombre OfficeNote.dmg", dijeron los investigadores de seguridad de SentinelOne, Dinesh Devadoss y Phil Stokes, en un análisis realizado el lunes. "La aplicación que contiene está firmada con la firma del desarrollador MAIT JAKHU (54YDV8NU9C)"

XLoader, detectado por primera vez en 2020, se considera un sucesor de Formbook y es un ladrón de información y registrador de teclas que se ofrece bajo el modelo de malware como servicio (MaaS). Una variante macOS del malware surgió en julio de 2021, distribuida como un programa Java en forma de un archivo .JAR compilado.

"Dichos archivos requieren Java Runtime Environment y, por esa razón, el archivo .jar malicioso no se ejecutará en una instalación de macOS lista para usar, ya que Apple dejó de enviar JRE con Mac hace más de una década", señaló la firma de ciberseguridad en ese momento.

La última versión de XLoader soluciona esta limitación cambiando a lenguajes de programación como C y Objective C, con el archivo de imagen de disco firmado el 17 de julio de 2023. Desde entonces, Apple revocó la firma.

SentinelOne dijo que detectó múltiples envíos del artefacto en VirusTotal durante el mes de julio de 2023, lo que indica una campaña generalizada.

"Los anuncios en los foros de crimeware ofrecen la versión para Mac en alquiler a $199/mes o $299/3 meses", dijeron los investigadores. "Curiosamente, esto es relativamente costoso en comparación con las variantes de Windows de XLoader, que cuestan $ 59 / mes y $ 129 / 3 meses".

Una vez ejecutado, OfficeNote arroja un mensaje de error que dice que "no se puede abrir porque no se puede encontrar el elemento original", pero, en realidad, instala un agente de inicio en segundo plano para persistencia

XLoader está diseñado para recopilar datos del portapapeles, así como información almacenada en los directorios asociados con navegadores web como Google Chrome y Mozilla Firefox. Safari, sin embargo, no está dirigido.

Además de tomar medidas para evadir el análisis tanto de forma manual como mediante soluciones automatizadas, el malware está configurado para ejecutar comandos de suspensión para retrasar su ejecución y evitar la aparición de señales de alerta.

"XLoader continúa presentando una amenaza para los usuarios y las empresas de macOS", concluyeron los investigadores.

"Esta última iteración disfrazada como una aplicación de productividad de oficina muestra que los objetivos de interés son claramente los usuarios en un entorno de trabajo. El malware intenta robar los secretos del navegador y del portapapeles que podrían usarse o venderse a otros actores de amenazas para un mayor compromiso".

## Fuentes: 
* Fuente 1: New Variant of XLoader macOS Malware Disguised as 'OfficeNote' Productivity App
* Fuente 2: MacOS users are being targeted by a new malware variant disguised as a signed productivity application called ‘OfficeNote’.
