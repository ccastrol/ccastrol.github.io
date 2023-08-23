---
title: Montar Google Drive en Linux con ocamlfuse
date: 2023-08-20 18:53:00 -0500
categories: [ARTICULO, TUTORIAL]
tags: [google, ocamlfuse, drive, montar, productividad]
render_with_liquid: false
toc: true
image:
  path: /assets/images/ocamlfuse/portada.jpeg
---

En este articulo les relataré mi experiencia con Google Drive. En mi trabajo usamos Gogole Workspace para todo, desde correo electrónico hasta su suite oficmatica, pasando por colabroración con Google Drive y el uso de unidades compartidas. Todo muy bien, el probelma esta cuando eres usuario Linux y no puedes montar nativamiente las unidades de Google Drive en un directorio en Linux. Cosa que lo tienen fácil los usuarios Windows, Gracias a Google Drive Desktop, ellos puedes montar sus unidades en su sistema de ficheros.
![img-description](/assets/images/ocamlfuse/google-drive.png)_Google_Drive
Pues bien para la comunidad Linux al no tener una solución nativa se la crea les presento google-drive-ocamlfuse

## ¿Que es Google-Drive-Ocamlfuse?

google-drive-ocamlfuse es un FUSE filesystem para Google Drive, esta escrito en Ocaml, que es un lenguaje de programación multiparadigma de alto nivel y proposito general. Esto permite montar tu Gogole Drive en Linux.
Lo puedes descargar desde este enlace.
<https://github.com/astrada/google-drive-ocamlfuse>
Para mi es la mejor solución en Linux para montar Google Drive como un directorio, dentro de tu filesystem.

## ¿Como instalar Google-drive-ocamlfuse?

Para la instalación es muy simple, en el caso de derivados de debian usamos el repositorio de alessandro-strada.
```bash
sudo add-apt-repository ppa:alessandro-strada/ppa
sudo apt-get update
sudo apt-get install google-drive-ocamlfusena
```
En la pagina de github del prouyecto ta da mas opciones de instalación, incluidas docker y ArchLinux.

## Forma de uso.

Primero debemos crear un dirctorio en el cual montaremos nuestro Google Drive, un ejemplo debe ser el siguiente
```shell
mkdir ~/GoogleDrive
```
A continuación  ingresaremos el siguiente comando indicando el mountpoint. Recuerda reemplazas mountpoint por la ruta donde creaste tu directorio.
```shell
google-drive-ocamlfuse [mountpoint]
```
Esto lo que hará será montar todo tu Google Drive, unidad personal en la ruta que le hemos indicado.

## ¿Como montar unidades compartidas?
En mi caso particular he necesitado montar una unidad compartida de Google Drive. Si aquellas que se crean como discos independientes qy que puedes compartir con tu equipo de trabajo.
Para ello abrirmos el archivo de configuración de google-drive-ocamlfuse en la siguiente ruta.
```shell
cd ~/.gdfuse/default/
```
Dentro encontraremos un fichero llamado config. Y dentro de config modificamos la línea:
team_drive_id=
Aqui debemos indicar el ID de la unidad compartida, este ID lo obtenemos del URL de nuestra unidad compartida a continuación una imagen de ejemplo
![ID de google Drive](/assets/images/ocamlfuse/id_unidad.png)

Con esto solo faltaría ejecutar el comando anterior para montar la unidad y listo. Tienes tu unidad compartida montada en un directorio en tu filesystem.

## Conclusiones.
Espero que este pequeño tutorial te halla servidor, te invito a consultar la pagina del autor de google-drive-ocamlfues para mayor detalle. Hay otras soluciones similares para acceder al Google Drive desde Linux, pero esta fue la que mas me sirve. 
Les invito q ue se suscriban y escriban sus comentario.
Saludos.

