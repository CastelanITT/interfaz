

![Inside a table data](https://github.com/user-attachments/assets/9d306968-6364-4265-9025-dfaef260b0ac)

## AWS Academy EC2 Ubuntu como Nodo ARM64 para Prácticas de Ensamblador

La plataforma **AWS Academy** permite a estudiantes y docentes acceder a instancias de cómputo en la nube. Una opción ideal para prácticas de lenguaje ensamblador es utilizar una **instancia EC2 con arquitectura ARM64**, basada en los procesadores **Graviton** de Amazon.

### Características principales:

- **Sistema operativo**: Ubuntu Server (ARM64)
- **Arquitectura de CPU**: ARMv8 (64 bits), compatible con prácticas de ensamblador moderno
- **Procesador**: Amazon Graviton2 o Graviton3 (dependiendo del tipo de instancia)
- **Casos de uso**: Ejecución y depuración de programas en lenguaje ensamblador para ARM64, experimentación con instrucciones SIMD, manejo de registros y memoria

### Requisitos básicos:

- Crear una instancia EC2 tipo `t4g.micro` o superior con Ubuntu ARM64
- Conectarse vía SSH para acceso al entorno de línea de comandos
- Instalar herramientas como `gcc-aarch64-linux-gnu`, `gdb-multiarch`, y `make` para desarrollo y pruebas

Este entorno ofrece un laboratorio escalable, económico y seguro para el aprendizaje de bajo nivel en arquitecturas ARM modernas.

- Bash Script
https://www.loom.com/share/e2e3345c83b34eb199c73a14cbef1623?sid=4322e54c-85e9-48a7-9f60-7ad4d414322b
- VSCODE con AWS
https://www.loom.com/share/08169eca9baf4a97bc0c8ed983bd10b9?sid=1bb7313a-f32a-4870-ac94-bfe94cb4c0de


```bash
# Para descargar y aplicarlo a el entorno
curl -O https://raw.githubusercontent.com/tectijuana/interfaz/refs/heads/main/Class-Sessions/u2/setup64.sh
sudo chmod +x  setup64.sh
sudo ./setup64.sh
```

NOTA: Recomiendo que la configuracion sea manual por esta vez  y valorar las funciones del script. Ya despues solo invocarlo pues conoce que esta configurando.
