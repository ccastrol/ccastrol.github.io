---
#layout: single
title: Alerta de Seguridad - Sector bancario blanco de ataques a la cadena de suministro de software de código abierto
excerpt: Severidad  CRÍTICA
date: 2023-07-24
classes: wide
header:
  teaser: /assets/images/Alerta-de-seguridad-1/unnamed.png
  teaser_home_page: true
categories:
  - Ciberseguridad
  - Vulnerabilidades
tags:
  - Ciberseguridad
---

![](/assets/images/Alerta-de-seguridad-1/unnamed.png)

## Sector bancario blanco de ataques a la cadena de suministro de software de código abierto

Un actor de amenazas aprovechó la plataforma NPM para cargar un par de paquetes que contenían un  script de preinstalación  que ejecutaba su objetivo malicioso tras la instalación. el colaborador detrás de estos paquetes estaba vinculado a una página de perfil de LinkedIn de una persona que se hacía pasar por empleado del banco.

Recientemente los investigadores de seguridad cibernética dijeron que han descubierto lo que dicen que es el primer ataque a la cadena de suministro de software de código abierto dirigido específicamente al sector bancario.

"Estos ataques mostraron técnicas avanzadas, incluido el objetivo de componentes específicos en los activos web del banco víctima al adjuntarle funcionalidades maliciosas", dijo Checkmarx en un informe publicado la semana pasada.

"Los atacantes emplearon tácticas engañosas como crear un perfil falso de LinkedIn para parecer centros de mando y control (C2) creíbles y personalizados para cada objetivo, explotando servicios legítimos para actividades ilícitas".

### Suplantación de identidad de empleados

Curiosamente, el colaborador detrás de estos paquetes estaba vinculado a una página de perfil de LinkedIn de una persona que se hacía pasar por empleado del banco objetivo. Nuestra suposición inicial fue que esto puede ser un ejercicio de prueba de penetración por parte del banco. Sin embargo, la respuesta que recibimos al contactar a la institución para obtener aclaraciones pintó una imagen diferente: el banco no estaba al tanto de esta actividad.

### Enganchando a la página de inicio de sesión

Los actores de la amenaza cargaron un paquete en NPM que contenía una carga útil magistralmente diseñada. Este código malicioso se diseñó meticulosamente para mezclarse con el sitio web del banco de la víctima y permanecer inactivo hasta que se le solicitara que entrara en acción.

La carga útil reveló que el atacante había identificado un ID de elemento único en el HTML de la página de inicio de sesión y diseñó su código para adherirse a un elemento de formulario de inicio de sesión específico, interceptando sigilosamente los datos de inicio de sesión y luego transmitiéndolos a una ubicación remota.

 

### Conclusión

Anticipamos una escalada constante en los ataques dirigidos, incluso a los bancos. Nuestra intención principal con este blog es arrojar luz sobre las tácticas, técnicas y procedimientos (TTP) que hemos observado y fomentar la comprensión colectiva y la conciencia de estas amenazas emergentes. La necesidad del momento es permanecer alerta, evolucionar continuamente nuestras defensas y estar un paso por delante de los actores de amenazas.



