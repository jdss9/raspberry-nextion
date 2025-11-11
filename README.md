# Nextion Pi GPIO Controller

Este proyecto integra una pantalla Nextion **NX8048P050** con una **Raspberry Pi 4** para el control de puertos **GPIO**, permitiendo utilizar elementos visuales en la pantalla (botones táctiles) para encender y apagar un **LED** u otros dispositivos.  
El sistema se desarrolla en **Python**, corre sobre **Ubuntu** y se distribuye mediante **contenedor**, facilitando su despliegue y portabilidad.

## 🛠 Tecnologías y Componentes

- Raspberry Pi 4
- Nextion NX8048P050
- LED + Resistencia
- Ubuntu (Raspberry OS)
- Python 3
- Docker / Podman

## 🎯 Objetivo del Proyecto

Permitir que la pantalla Nextion actúe como interfaz de usuario para controlar un LED conectado a un pin GPIO de la Raspberry Pi, con comunicación serial entre la pantalla y la Pi, y ejecución del software dentro de un contenedor.

## 🧩 Arquitectura

Pantalla Nextion ⇆ (Serial UART) ⇆ Raspberry Pi 4 → GPIO → LED

## 📁 Estructura del Repositorio

nextion-pi-gpio-controller/
│
├── src/
│   ├── main.py              # Script principal
│   ├── serial_handler.py    # Comunicación serial con Nextion
│   ├── gpio_controller.py   # Control de GPIO
│
├── docker/
│   ├── Dockerfile           # Imagen contenedor
│   └── entrypoint.sh
│
├── nextion/
│   └── hmi_project.tft      # Proyecto para pantalla
│
└── README.md

## 🚀 Ejecución del proyecto

1. Clonar repositorio
git clone https://github.com/tuusuario/nextion-pi-gpio-controller.git
cd nextion-pi-gpio-controller

2. Construir la imagen
docker build -t nextion-gpio .

3. Ejecutar contenedor
docker run --privileged --device /dev/ttyAMA0 --device /dev/gpiomem nextion-gpio

## Autor

JuanD
