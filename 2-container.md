# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```

```
docker create --name srv-web nginx:alpine
```

<img width="599" height="56" alt="image" src="https://github.com/user-attachments/assets/f26bc5aa-5239-4637-ae9a-4e747c465ada" />

Crear el contenedor  **srv-web** usando la imagen nginx version alpine
# COMPLETADO

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world
# COMPLETAR

### Listar los contenedores ejecutándose o no

```
docker ps -a
```

<img width="952" height="75" alt="image" src="https://github.com/user-attachments/assets/8543c9ea-5d1d-4f7d-8b5d-0fc18b38f51b" />

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```

```
docker start srv-web
```

<img width="342" height="53" alt="image" src="https://github.com/user-attachments/assets/549e6922-407b-4d55-a7fa-87e22c212888" />

Iniciar el contenedor srv-web 
# COMPLETAR

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

<img width="994" height="66" alt="image" src="https://github.com/user-attachments/assets/23c999f3-ceba-43a7-9c71-b94cf7efd955" />

### Para detener un contenedor

```
docker stop <nombre contenedor>
```

```
docker stop srv-web
```

<img width="649" height="139" alt="image" src="https://github.com/user-attachments/assets/e7aecba9-b457-4386-afd8-933fcbd066bc" />


### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](dockerRun.PNG)

```
docker run --name srv-web2 nginx:alpine
```

<img width="900" height="559" alt="image" src="https://github.com/user-attachments/assets/694ee0eb-3775-4113-a2b9-32f6dd371d46" />

<img width="1522" height="128" alt="image" src="https://github.com/user-attachments/assets/0a243ad9-44ef-4351-b288-7941b47e6a16" />

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine
# COMPLETADO

**¿Qué sucede luego de la ejecución del comando?**

Al ejecutar el comando, se crea y despliega el contenedor srv-web2 basado en nginx. Debido a que se ejecutó en modo interactivo y no en segundo plano (sin el flag -d), la terminal permanece vinculada al contenedor mostrando los logs de actividad en tiempo real. 

# COMPLETADO 

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```

```
docker run -d --name srv-web3 nginx:alpine
```

<img width="918" height="120" alt="image" src="https://github.com/user-attachments/assets/56be49af-c454-44fe-b5da-e7fd3a08a0cd" />

<img width="1631" height="126" alt="image" src="https://github.com/user-attachments/assets/431be8c3-f473-4f33-b0c1-a9f29191ceed" />

Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine
# COMPLETAR

### Para eliminar un contenedor

Contenedor creado a partir de la imagen hello-world con nombre generado de manera aleatoria.

<img width="1817" height="213" alt="image" src="https://github.com/user-attachments/assets/c3eefadb-5140-4ec4-b536-8d09d8a4f0da" />

```
docker rm <nombre contenedor>
```

```
docker rm optimistic
```
<img width="1705" height="299" alt="image" src="https://github.com/user-attachments/assets/95d91a86-71ce-4387-8632-81240fb2c4f2" />

Eliminar el contenedor que se creó a partir de la imagen hello-world 
# COMPLETADO

Verificar que el contenedor que se eliminó
# COMPLETADO

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```

```
docker rm -f srv-web3
```
Ejecución de eliminación forzada

<img width="525" height="74" alt="image" src="https://github.com/user-attachments/assets/15373ebc-9aea-4df9-817b-94f0f41959ee" />


Eliminación comprobada

<img width="1669" height="135" alt="image" src="https://github.com/user-attachments/assets/364cf56e-54d1-480c-9e0d-206a8cec7e39" />

Eliminar el contenedor **srv-web3** 
# COMPLETADO

Verificar que el contenedor que se eliminó
# COMPLETADO

### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 

```
docker inspect srv-web
```

<img width="1764" height="808" alt="image" src="https://github.com/user-attachments/assets/f7dfcf5a-1fc4-45e9-b318-40d9103c2a23" />

# COMPLETADO
