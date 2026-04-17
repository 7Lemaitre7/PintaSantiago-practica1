# Mapeo de puertos
El mapeo de puertos es un mecanismo que permite redirigir el tráfico de red desde un puerto en el host (tu máquina local o servidor) hacia un puerto específico en un contenedor Docker.
Por ejemplo, supongamos que tienes un contenedor que ejecuta un servidor web en el puerto 80 dentro del contenedor, pero quieres acceder a ese servidor desde tu navegador en la máquina host. Puedes usar el mapeo de puertos para redirigir el tráfico del puerto 80 del contenedor al puerto 3000 en el host. De esta manera, cuando accedas a http://localhost:3000 en tu navegador, el tráfico se dirigirá al servidor web dentro del contenedor en el puerto 80.

![mapeo](mapeoPuertos.PNG)

### Para crear un mapeo de puertos (puerto host y puerto contenedor)
El mapeo de puertos se especifica al ejecutar un contenedor Docker utilizando la opción -p o --publish seguida de los puertos que deseas mapear
```
docker run -d --name <nombre contenedor> -p <puerto host>:<puerto contenedor> <nombre imagen>:<tag>
```

```
docker run -d --name prueba -p 3000:80 nginx:alpine
```

<img width="810" height="112" alt="image" src="https://github.com/user-attachments/assets/dca8ea78-1796-4146-94be-096e0a285246" />

Crear un contenedor a partir de la imagen nginx version alpine con el mapeo de puertos del ejemplo gráfico, host 3000 y contenedor 80
# COMPLETADO

# COLOCAR UNA CAPTURA DE PANTALLA  DEL ACCESO http://localhost:3000

<img width="1907" height="995" alt="image" src="https://github.com/user-attachments/assets/08a1d66e-4b86-450a-8dcc-9fba74e0bdde" />

### Para mapear más de un puerto

```
docker run -d --name <nombre contenedor> -p <puerto host 01>:<puerto contenedor 01> -p <puerto host 02>:<puerto contenedor 02> <nombre imagen>:<tag>
```

```
docker run -d --name rabbit-prod -p 5672:5672 -p 15672:15672 rabbitmq:management-alpine
```

<img width="1254" height="488" alt="image" src="https://github.com/user-attachments/assets/8802757d-ddb2-4cdb-b762-2424e2ec2a10" />

Crear un contenedor a partir de la imagen rabbitmq version management-alpine, para este mapeo de puertos usar en el host los mismos puertos del contenedor.
# COMPLETADO

### Usando una forma más semántica cuando se especifican puertos

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> <nombre imagen>:<tag> 
```
### Publicando todos los puertos
```
docker run -P -d --name <nombre contenedor> <nombre imagen>:<tag> 
```

-P: le indica a Docker que asigne automáticamente puertos aleatorios en tu host para todos los puertos expuestos por el contenedor.

**Recordar**
No puedes mapear puertos a un contenedor existente directamente después de su creación con Docker. El mapeo de puertos debe especificarse en el momento de crear y ejecutar el contenedor.

### Crear contenedor de Jenkins puertos contenedor: 8080 (interface web) y 50000 (comunicación entre nodos) imagen: jenkins/jenkins:alpine3.18-jdk11
# COMPLETADO

```
docker run -d --name mi-jenkins -p 8080:8080 -p 50000:50000 jenkins/jenkins:alpine3.18-jdk11
```

<img width="1299" height="497" alt="image" src="https://github.com/user-attachments/assets/6d0e11ed-e0aa-4149-b73b-d728074c927d" />

# COLOCAR UNA CAPTURA DE PANTALLA  DEL ACCESO http://localhost:8080

<img width="1919" height="995" alt="image" src="https://github.com/user-attachments/assets/1e4a98e8-5f24-404a-acdd-5bcc2ac05f84" />

### ¿Cómo obtener la contraseña solicitada?
Para obtener la contraseña solicitada es necesario ingresar al contenedor.

![Imagen](jenkins.PNG)

