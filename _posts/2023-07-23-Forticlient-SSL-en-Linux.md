---
#layout: single
title: Conectar a Forticlient con OpenfortiVPN
excerpt: "Son muchas las empresas que usan Forticlient para conectar por VPN. Hoy te explico como conectar por Forticlient SSL usando OpenFortiVPN."
date: 2023-07-23
classes: wide
header:
  teaser: /assets/images/openfortivpn/portada.png
  teaser_home_page: true
categories:
  - Utilidades
  - Networking
  - Vulnerabilidades
tags:
  - Herramientas
  - Windows
  - Linux
  - Domain Controller
  - Guía
---

![](/assets/images/openfortivpn/portada.png)

## ¿Como conectamos a una red VPN en Linux?
Es muy sencillo. primero tenemos que instalar openfortivpn

```bash
sudo apt-get install openfortivpn
```

Luego de esto debemos configurarlo para ello abrimos nuestro archivo ubicado en la ruta `/etc/openfortivpn/config` 

```bash
### configuration file for openfortivpn, see man openfortivpn(1) ###
# host = IP o URL de tu VPN
# port = Puerto que usas
# username = Nombre de usuario
# password = Clave de tu usuario
# trusted-cert = Aqui debes ingresar todo tu cert
```





