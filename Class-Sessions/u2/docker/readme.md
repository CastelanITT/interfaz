![Screenshot 2025-03-30 at 7 51 51 p m](https://github.com/user-attachments/assets/dd746913-d08b-4acb-b002-114ad08b683e)


## Creación de la imagen
```bash
docker build --platform linux/arm64 -t compilador_arm64:latest .
```

## Corrida de Alphine ARM64 en docker con las herramientas comentadas en setup64.sh
```bash
docker run --platform linux/arm64 -it --rm compilador_arm64:latest
```
_Si deseas limpiar completamente tu entorno Docker (contenedores, imágenes, volúmenes y redes no usadas), ten en cuenta que estas acciones son irreversibles. Asegúrate de que no necesitas nada de lo que vas a borrar. Aquí te presento algunos comandos:_

```bash
Detén todos los contenedores en ejecución:
  docker stop $(docker ps -q)
1.Borra todos los contenedores (tanto los detenidos como los que se hayan detenido):
  docker rm $(docker ps -a -q)
3. Borrar todas las imágenes
  docker rmi $(docker images -q)
4. Borrar todos los volúmenes
  docker volume rm $(docker volume ls -q)
5. Borrar redes no usadas
   docker network prune -f
6. Usar Docker System Prune (opción más general)
```

Para borrar contenedores detenidos, imágenes no referenciadas y redes no utilizadas:
```bash
  docker system prune -a --volumes
```
Este último comando es muy completo, ya que con la opción -a elimina todas las imágenes no utilizadas (no solo las dangling) y con --volumes también borra los volúmenes.
