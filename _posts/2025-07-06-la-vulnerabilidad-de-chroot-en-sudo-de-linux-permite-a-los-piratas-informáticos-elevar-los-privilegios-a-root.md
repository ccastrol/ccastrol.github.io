---
layout: post
title: La vulnerabilidad de chroot en sudo de Linux permite a los piratas informáticos
  elevar los privilegios a root
author: author_01
categories:
- ciberseguridad
tags:
- linux
- root
- chroot
image:
  path: "/assets/img/CHROOT.png"
  alt: Vulnerabilidad permite obtener acceso root
date: 2025-07-06 10:02 -0500
---
Una vulnerabilidad crítica descubierta en la utilidad Sudo permite a usuarios locales sin privilegios obtener acceso root. La falla afecta configuraciones por defecto en múltiples distribuciones Linux. No existen soluciones alternativas, por lo que se requiere actualización inmediata.

## CVE:

CVE-2025-32463 (CVSS 9.8):
Esta vulnerabilidad se relaciona con un fallo en el manejo de la opción --chroot (-R) introducida en Sudo 1.9.14. Esta opción permite invocar entornos chroot que cargan configuraciones y bibliotecas maliciosas a través del sistema NSS (Name Service Switch). La vulnerabilidad permite que bibliotecas diseñadas por el atacante sean cargadas por Sudo con privilegios root, facilitando una escalada completa de privilegios.

El exploit demostrado utiliza un archivo /etc/nsswitch.conf manipulado dentro del chroot, que apunta a bibliotecas .so maliciosas cargadas por Sudo al ejecutar comandos, sin requerir permisos previos de sudo.


## Productos Afectados:

Sudo desde v1.9.14 hasta v1.9.17
 

## Distribuciones impactadas con configuración predeterminada:
Ubuntu 24.04.1
Fedora 41 Server
Posiblemente otras basadas en Debian, Red Hat y derivados
 

## Solución:

La única solución disponible es actualizar a Sudo 1.9.17p1 o versiones superiores, donde:

La opción -- chroot ha sido obsoleta
Se han eliminado las funciones inseguras pivot_root() y unpivot_root()

No existe parche temporal ni configuración alternativa segura.

## Referencias
- Fuente 1: https://cybersecuritynews.com/linux-sudo-chroot-vulnerability/
- Fuente 2: https://www.stratascale.com/vulnerability-alert-CVE-2025-32463-sudo-chroot