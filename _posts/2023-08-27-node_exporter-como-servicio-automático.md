---
title: Node_exporter como servicio con inicio automático
date: 2023-08-27 14:53:00 -0500
categories: [ARTICULO]
tags: [prometheus, grafana, node_exporter, linux]
render_with_liquid: false
toc: true
image:
  path: /assets/images/node_exporter/Miniatura.png
---
## Introducción.
Es este articulo explicaré la forma de como poner a node_exporter como servicio con inicio autoático en un equipo Linux.

En mi caso tengo varios servidores Linux los cuales empece a monitorear con node_exporter. El problema esta que cuando se reinicia el equipo node_exporter deja de funcionar y se debe iniciar de forma manual.
Con esta solución podras ejecutar node_exporter y tenerlo como servicio que se ejecutará con el inicio de sesión del equipo, de forma automática.

## Instalación.
Descargar node exporter https://prometheus.io/download/
```shell
wget https://github.com/prometheus/node_exporter/releases/download/v1.6.1/node_exporter-1.6.1.linux-amd64.tar.gz
tar xvfz node_exporter-1.6.1.linux-amd64.tar.gz
mv node_exporter-1.6.1.linux-amd64 node_exporter
mv nose_exporter/ /opt/
```
Dentro del directorio creamos el archivo node_exporter.service
```bash
[Unit]
Description=Node Exporter
After=network.target
[Service]
User=operador
Type=simple
Restart=always
RestartSec=1
ExecStart=/opt/node_exporter/node_exporter  --web.listen-address=:9100
[Install]
WantedBy=multi-user.target
```
Creamos un enlace simbólico de node_Exporter en la ruta /etc/systemd/system/
```bash
sudo ln -s /opt/node_exporter/node_exporter.service /etc/systemd/system/node_exporter.service
```

Asignamos permisos al directorio node_exporter
```bash
sudo chown -R root:root node_exporter/
sudo chmod -R 755 node_exporter/
```

Verificamos que al reinicio funcione.
```bash
sudo systemctl daemon-reload
sudo systemctl start node_exporter
sudo systemctl enable node_exporter.service
sudo systemctl enable --now node_exporter.service
sudo systemctl status node_exporter
```
Una ve hecho esto podras recoger las metricas con Prometheus y luego exportarla a Grafana.
