# Imagen
### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen>

docker pull hello-world

<img width="915" height="223" alt="image" src="https://github.com/user-attachments/assets/29dc148e-e77c-4009-8f60-4cdc876f7561" />

```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>

docker pull hello-world:latest

<img width="916" height="180" alt="image" src="https://github.com/user-attachments/assets/cf17d9c8-bdb7-4b5a-9254-fbb649a566b7" />

```

Descargar la imagen **hello-world**
# COMPLETADO

**¿Qué es nginx?**

Es un software de infraestructura de alto rendimiento que funciona como servidor web, proxy inverso, balanceador de carga y caché HTTP. Su principal ventaja competitiva es una arquitectura basada en eventos que le permite gestionar miles de conexiones simultáneas con un consumo mínimo de recursos, optimizando la velocidad y la escalabilidad de cualquier aplicación en la red.

# COMPLETADO

Descargar la imagen  **nginx** en la versión **alpine**

<img width="915" height="367" alt="image" src="https://github.com/user-attachments/assets/195ca11d-638d-474a-8dc8-f69b315a67bf" />

# COMPLETADO

### Listar imágenes

```
docker images

<img width="690" height="108" alt="image" src="https://github.com/user-attachments/assets/44f0d993-8e53-4475-88e7-fd5dfb760d9a" />

```

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO 

**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>

<img width="795" height="764" alt="image" src="https://github.com/user-attachments/assets/410cfd78-dc46-490c-b103-62bcecae4e7a" />

docker inspect <nombre imagen>:<tag>

<img width="592" height="878" alt="image" src="https://github.com/user-attachments/assets/0840f609-b2a4-4422-a2c9-1c02cf8c1965" />

```

Inspeccionar la imagen hello-world 

```
docker inspect hello-world

<img width="598" height="574" alt="image" src="https://github.com/user-attachments/assets/72ec9d5b-97f0-46ae-8d30-de433be0aa0f" />

```

# COMPLETADO

**¿Con qué algoritmo se está generando el ID de la imagen**

El algoritmo con el que se genera el ID es SHA256 ó SHA-256, incluso aparece como prefijo con el comando inspect.

<img width="789" height="110" alt="image" src="https://github.com/user-attachments/assets/e2626df0-8c87-4870-97bf-d42d56bb401c" />

# COMPLETADO

### Filtrar imágenes

```
docker images | grep <termino a buscar>

<img width="704" height="106" alt="image" src="https://github.com/user-attachments/assets/526d8fa3-ce0a-47fd-aede-f651a5bf678a" />

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>

<img width="736" height="71" alt="image" src="https://github.com/user-attachments/assets/a667fdbd-45f3-49a1-bdf2-20a8a61a9297" />

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

Se volvió a instalar la imagen hello-world:latest

<img width="744" height="69" alt="image" src="https://github.com/user-attachments/assets/b9976fbc-8bf1-456d-8cc8-098cd8b20bd0" />

```
