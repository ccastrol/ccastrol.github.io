---
title: Conectar a Forticlient con OpenfortiVPN
date: 2023-07-23
categories: [ARTICULO]
tags: [windows, linux, controlador de dominio, domain controller, forticlient]
toc: true
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





