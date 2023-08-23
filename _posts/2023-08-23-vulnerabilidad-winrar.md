---
title: La vulnerabilidad de WinRAR permite la ejecución de código arbitrario a través de archivos maliciosos
date: 2023-08-23 14:03:00 -0500
categories: [CIBERSEGURIDAD]
tags: [winrar, vulnerabilidad, crítica,  ]
math: true
mermaid: true
toc: true
image:
  path: /assets/images/winrar/winrar_virus.png
---

Esta vulnerabilidad permite a atacantes remotos ejecutar código arbitrario en las instalaciones afectadas de RARLAB WinRAR. Se requiere la interacción del usuario para explotar esta vulnerabilidad, ya que el objetivo debe visitar una página maliciosa o abrir un archivo malicioso.

La falla específica existe en el procesamiento de los volúmenes de recuperación.

El problema se debe a la falta de una validación adecuada de los datos proporcionados por el usuario, lo que puede provocar un acceso a la memoria más allá del final de un búfer asignado. Un atacante puede aprovechar esta vulnerabilidad para ejecutar código en el contexto del proceso actual.

## Mitigar el riesgo

RARLAB lanzó la verrsión 6.23 de Winrar el 2 de agosto de 2023, abordando efectivamente la vulnerabilidad CVE-2023-40477. Por lo tanto, se recomienda encarecidamente a los usuarios de WinRAR que apliquen la actualización de seguridad disponible de inmediato.

Aparte de la corrección del código de procesamiento de volúmenes de recuperación RAR4, la versión 6.23 soluciona un problema con archivos especialmente diseñados que conducen a un inicio de archivo incorrecto, que también se considera un problema de alta gravedad.

También se debe tener en cuenta que Microsoft ahora está  probando el soporte nativo  en Windows 11 para archivos RAR, 7-Zip y GZ, por lo que ya no se requerirá software de terceros como WinRAR en esta versión a menos que se necesiten sus funciones avanzadas.

Aquellos que continúen usando WinRAR deben mantener el software actualizado, ya que los piratas informáticos abusaron de fallas similares en el pasado para instalar malware.

Aparte de eso, tener cuidado con los archivos RAR que abre y usar una herramienta antivirus que pueda escanear archivos sería una buena medida de seguridad.

## Versión final de WinRAR 6.23

Se agregó la extracción de archivos XZ utilizando el filtro ARM64.

Los archivos temporales Rar$LS*, creados al extraer o probar varios archivos desde el menú contextual de Windows, ahora se eliminan de inmediato. Anteriormente, solo se eliminaban en las próximas ejecuciones de WinRAR y solo si tenían al menos 1 hora de antigüedad.

## Conclusiones

Se solucionó un problema de seguridad relacionado con la escritura fuera de los límites en el código de procesamiento de volúmenes de recuperación RAR4.

WinRAR podría iniciar un archivo incorrecto después de que un usuario hiciera doble clic en un elemento en un archivo especialmente diseñado.

los temas de la interfaz se aplicaron a los íconos de archivo incluso si la opción "Aplicar a los íconos de archivo" en el cuadro de diálogo "Organizar temas" estaba desactivada.


## Fuentes:
* Fuente 1: https://www.blackhatethicalhacking.com/news/winrar-vulnerability

* Fuente 2: https://www.bleepingcomputer.com/news/security/winrar-flaw-lets-hackers-run-programs-when-you-open-rar-archives/
