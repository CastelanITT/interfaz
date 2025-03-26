![image](https://github.com/user-attachments/assets/0b8349da-3bce-4d35-8813-c10eed2618f8)



## FigJam del la unidad

https://www.figma.com/board/wymy14UHuIrxCcS2r2rJJd/ARM-32-Assembly?node-id=0-1&t=l9LQOhOQtWWfxdiR-1


![Screenshot 2025-03-13 at 10 44 42 p m](https://github.com/user-attachments/assets/815cdb0b-f23d-407f-84b3-78d86a11a39f)

# 1.- CONOCIENDO EL HARDWARE ARM CON RPI

# 📚 **Videos Raspberry Pi Compute Module 4 (Interfaz y configuración)**

## ▶️ **Parte 1:**
- [🔗 Ver video](https://www.loom.com/share/0f7c1fbd4e3b4602b631bd0c9002bb24?sid=b83e5c89-d7b3-4a1a-89e5-c89d7b34a1a8)

  ## ▶️ **Parte 2:**
- [🔗 Ver video](https://www.loom.com/share/4537c852e0114611b05b8da4a7b01bbb?sid=eeca147d-4906-4334-932d-5f896a9f2167))


## ▶️ **Parte 3:**
- [🔗 Ver video](https://www.loom.com/share/85098f4425514f1cb14ec20147d58619?sid=fb40e16f-9530-41fc-802a-e81c56b2b376)


---

## 🔌 **Cable Consola (Serial):**
- Asegúrate de conectar correctamente los pines del cable de consola (TX, RX, GND).
- **NO** conectar el cable de alimentación de 5V al Raspberry Pi.

---
## Tarjetas SD y RaspberryPI 4 
https://www.loom.com/share/bba1e08357784e5cb48e8a7ab2fb0931?sid=d80c0e43-34e6-441a-b2a6-cd1571efab12

✨ ¡Éxito en tus prácticas con Raspberry Pi!

---
# 2.- SETUP RaspberryPi 5 de 8Gb RAM, 512 GB M.2 almacenamiento

```bash
#!/bin/bash

###############################################################
# Script: Configuración rápida entorno desarrollo ARM64
# Propósito: Instala herramientas esenciales de desarrollo,
#            GEF y Oh My Zsh en sistemas ARM64 (Raspberry Pi).
# Autor: CHATGTP
# Fecha: 25 DE MARZO DEL 2025
###############################################################

# Anuncia visualmente inicio de la actualización usando figlet
#
#  Video acompañamiento: https://www.loom.com/share/e2e3345c83b34eb199c73a14cbef1623?sid=4322e54c-85e9-48a7-9f60-7ad4d414322b
#  Y como configurar el VSCode https://www.loom.com/share/08169eca9baf4a97bc0c8ed983bd10b9?sid=d2d3bb39-362d-47d7-a136-992da2921cb6
#    Solo que clientes macOS y Linux deben de poner permisos a la llave con $ chmod 400 llavesita.pem
# Corrida:
#    $ wget https://raw.githubusercontent.com/tectijuana/interfaz/refs/heads/main/Class-Sessions/u2/setup64.sh
#    $ chmod +x setup64.sh
#    $ ./setup64.sh
# 
#!/bin/bash

# =======================================================================
# 🚀 Instalación Herramientas ARM64 (AWS EC2 Debian)
# -----------------------------------------------------------------------
# Este script instala paquetes esenciales para desarrollo en ensamblador
# ARM64 y programación general.
# =======================================================================

# 🔄 Actualizamos primero el índice de paquetes disponibles
sudo apt-get update && sudo apt upgrade -y

# 📦 Instalamos las herramientas esenciales para desarrollo
sudo apt-get install -y \
  build-essential \
  gcc \
  g++ \
  binutils \
  gdb \
  lldb \
  cmake \
  git \
  curl \
  wget \
  clang \
  clang-format \
  valgrind \
  strace \
  vim \
  nano \
  tmux \
  screen \
  htop \
  tree \
  file \
  unzip \
  zip \
  asciinema \
  python3 \
  python3-pip \
  python3-dev \
  software-properties-common \
  jq \
  figlet \
  mc

# -----------------------------------------------------------------------
# 📌 Explicación de los paquetes instalados:
# -----------------------------------------------------------------------
# build-essential: Herramientas básicas (gcc, make, etc.).
# gcc y g++: Compiladores GNU para C y C++ (ARM64).
# binutils: Utilidades GNU (ensamblador 'as', linker 'ld').
# gdb y lldb: Depuradores (debuggers).
# cmake: Herramienta de compilación multiplataforma.
# git: Control de versiones para proyectos.
# curl y wget: Herramientas para descargas desde consola.
# clang y clang-format: Compilador LLVM y formateador de código.
# valgrind: Análisis avanzado de memoria.
# strace: Monitor de llamadas al sistema.
# vim y nano: Editores de texto.
# tmux y screen: Multiplexores de terminal.
# htop: Monitor del rendimiento del sistema.
# tree: Visualiza estructura de directorios.
# file: Identificación de tipos de archivo.
# unzip y zip: Herramientas para compresión.
# asciinema: Grabación de sesiones de terminal.
# python3, python3-pip, python3-dev: Entorno de desarrollo Python.
# software-properties-common: Manejo de repositorios adicionales.
# zsh: Shell avanzado alternativo a bash.
# jq: Procesamiento de JSON desde consola.
# figlet: Solo banners y avisos para el asciinema
# mc: midnight commandes es un file manager en consoka

echo "🎉 Instalando depurador extension GEF"

# Anuncia visualmente la instalación de GEF
figlet "Instalando GEF"

# Instalación automatizada de GEF (GDB Enhanced Features) desde repositorio oficial
bash -c "$(curl -fsSL https://gef.blah.cat/sh)"

# Anuncia visualmente la verificación de GEF
figlet "Verificando GEF"

# Verifica que GEF se instaló correctamente y muestra ayuda inicial
gdb -ex "gef help" -ex quit

echo "🎉 ¡Herramientas instaladas exitosamente!"

# Anuncia visualmente la instalación de Oh My Zsh
figlet "Instalando Oh My Zsh"

# Instalación automatizada de Oh My Zsh (framework para Zsh)
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
###############################################################
# Fin del script
###############################################################

```
3.- POR CUENTA INSTALAR COMPLEMENTO "GDB" CON GEF PARA EXTENDERLO

![gef](https://github.com/user-attachments/assets/b6f550cb-d080-43c7-90c9-82aa63bcef51)


_GEF (GDB Enhanced Features) es un complemento para GDB (GNU Debugger) que proporciona características avanzadas para depuración, especialmente en análisis de programas binarios, seguridad informática y desarrollo en ensamblador. Es una alternativa más ligera a herramientas como PEDA o Pwndbg._

### 📌 **Características principales de GEF**
- 🔍 **Mejora la interfaz de GDB** con comandos más intuitivos.
- 🛠️ **Extensiones para análisis de exploits**, como stack canaries, ASLR y protección RELRO.
- 🔢 **Visualización mejorada de registros, pila y memoria** en debugging de binarios.
- 📊 **Soporte para debugging en arquitecturas x86, x86-64, ARM, MIPS y otras**.
- 🔄 **Integración con otras herramientas de reversing**, como ROPgadget y Capstone.

Link https://github.com/hugsy/gef
---

### ✅ **¿Cómo instalar GEF? en sus cuentas remotas**

Para instalar GEF en Linux, usa:
```sh
wget -O ~/.gdbinit -q https://gef.blah.cat/py
```
Luego, abre GDB y GEF se activará automáticamente.

Si necesitas usarlo en depuración de código en **ensamblador ARM64**, GEF es útil para analizar registros y la ejecución de instrucciones en arquitecturas embebidas.

¿Quieres saber cómo usar GEF para debugging de código en ensamblador ARM? 🚀

## ▶️ **ENLACE E INSTALACION GEF:**
- https://www.loom.com/share/f44d5e8b85f84d2784e3c2855823b8c2?sid=37a865ae-f5d0-44af-860f-089d8e97d128


# Siguiente el uso del templete

[Siguiente, TEMPLETE](templete/readme.md)
