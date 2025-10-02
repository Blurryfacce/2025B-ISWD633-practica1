# Imagen
### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
<img width="725" height="202" alt="image" src="https://github.com/user-attachments/assets/b4c2b8f2-cea2-4a9d-98af-4bd10b431ae2" />

```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
<img width="886" height="183" alt="image" src="https://github.com/user-attachments/assets/ce99e70f-1d67-4a7d-88e2-08ca8da25b64" />

```

Descargar la imagen **hello-world**
# COMPLETAR

**¿Qué es nginx**
Nginx es un software de código abierto que funciona como servidor web, proxy inverso, balanceador de carga y caché de contenido, destacando por su alto rendimiento y eficiencia en el manejo de múltiples conexiones simultáneas gracias a su arquitectura basada en eventos. 
# COMPLETAR 

Descargar la imagen  **nginx** en la versión **alpine**
# COMPLETAR

### Listar imágenes

```
<img width="886" height="304" alt="image" src="https://github.com/user-attachments/assets/15bbf297-591e-406e-892c-38b0fd8760bc" />

```

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO 

**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>

<img width="886" height="367" alt="image" src="https://github.com/user-attachments/assets/716c7be9-5b22-43ec-8783-942c6986e245" />
<img width="886" height="566" alt="image" src="https://github.com/user-attachments/assets/c59b66f5-1eea-4313-af9a-e340d2d25aa0" />


```

Inspeccionar la imagen hello-world 
# COMPLETAR

**¿Con qué algoritmo se está generando el ID de la imagen**
SHA256
# COMPLETAR

### Filtrar imágenes

```
docker images | grep <termino a buscar>
<img width="741" height="102" alt="image" src="https://github.com/user-attachments/assets/253868ca-3c34-4626-a225-6536fa9152d5" />


```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>

<img width="886" height="213" alt="image" src="https://github.com/user-attachments/assets/814ab536-776f-4c72-840d-3ac04ced4d66" />

```

Eliminar la imagen hello-world 
# COMPLETAR

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

```
docker run hello-world

<img width="886" height="573" alt="image" src="https://github.com/user-attachments/assets/026bc245-d109-4630-afd7-3f602f8b4b52" />

```

