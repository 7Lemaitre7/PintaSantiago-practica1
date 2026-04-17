# Operaciones con contenedores

### Ejecutar un comando en un contenedor de Docker en ejecución
```
docker exec <nombre contenedor> <comando> <argumentos opcionales>
```

# COMPLETAR
### ¿Para qué se usa el comando ls?

<img width="337" height="300" alt="image" src="https://github.com/user-attachments/assets/9515931f-800e-4968-8047-c65a62543d51" />

El comando ls sirve para listar el contenido de un directorio en sistemas. Su función es mostrarte qué archivos y carpetas hay en tu ubicación actual o en una ruta específica. Es altamente personalizable mediante opciones: por ejemplo, ls -l muestra detalles técnicos como permisos y tamaño, mientras que ls -a revela archivos ocultos. Básicamente, es el comando fundamental para "ver" y navegar por el sistema de archivos desde la terminal.

### ¿Para qué sirve el argumento -l junto al comando ls?

El argumento -l activa el formato largo, que muestra detalles técnicos de cada archivo en lugar de solo su nombre. Proporciona una lista organizada en columnas con los permisos, el propietario, el tamaño y la fecha de modificación. Es esencial para saber quién tiene acceso a un archivo y cuándo fue editado por última vez.

### Usar el contenedor de jenkins creado previamente y ejecutar el comando ls con el argumento -l

<img width="404" height="354" alt="image" src="https://github.com/user-attachments/assets/f8413cb8-d416-48e3-9c85-9cf604a2ad97" />

# COMPLETADO
# COLOCAR UNA CAPTURA DE PANTALLA

### Para ejecutar un shell interactivo en un contenedor de Docker especificado.
El comando **docker exec** te permite acceder a la sesión shell de un contenedor en ejecución, estarás dentro del contenedor y podrás ejecutar comandos como si estuvieras en una terminal normal. 
Para saber qué comando utilizar para abrir una terminal dentro de un contenedor, es útil conocer la imagen base del contenedor, ya que diferentes imágenes pueden usar diferentes shells o comandos para abrir una terminal. Puedes verificar la documentación de la imagen del contenedor en Docker Hub o en el repositorio de la imagen para obtener información específica sobre cómo abrir una terminal en esa imagen.
- Para imágenes basadas en Debian o Ubuntu, puedes probar con bash.
- Para imágenes basadas en Alpine Linux, puedes probar con sh.
![Imagen](jenkins-i.PNG)
```
docker exec -i <nombre contenedor> <programa o comando>
```
-i: mantiene abierta la entrada estándar (stdin) del contenedor. Esto significa que puedes enviar datos al proceso que se está ejecutando en el contenedor a través de la terminal local. *Sin embargo, esto no asigna un terminal al contenedor, por lo que no podrás ver la salida del proceso de forma interactiva.*

### Ejecutar una de las siguientes instrucciones
```
docker exec -i <nombre contenedor> /bin/bash 
```
ó
```
docker exec -i <nombre contenedor> bash 
```

<img width="384" height="62" alt="image" src="https://github.com/user-attachments/assets/9b3b97e9-08da-4c5b-8946-ee20c17a4035" />

**Considerar**
- /bin/bash: Al especificar la ruta completa del shell, Docker buscará el ejecutable /bin/bash en el sistema de archivos del contenedor y lo ejecutará. Esto es útil cuando quieres asegurarte de que se está utilizando un shell específico que está ubicado en una ubicación conocida en el sistema de archivos del contenedor. 
- bash: Al especificar solo el nombre del shell, Docker buscará el comando bash en las rutas del sistema (por lo general, en las rutas definidas en la variable de entorno PATH) del contenedor y lo ejecutará. Esto asume que bash está disponible en alguna de las rutas del sistema definidas en el contenedor.

Mostrar el contenido del archivo /etc/shells, que contiene una lista de shells válidos en el sistema.

docker exec -it jenkins cat /etc/shells


Ejecutar
```
echo "Hola mundo"
```

<img width="391" height="96" alt="image" src="https://github.com/user-attachments/assets/9c29e352-4a71-4402-ab3a-90e5e4b50968" />

Ejecutar
```
whoami
```

<img width="383" height="80" alt="image" src="https://github.com/user-attachments/assets/9c965fd6-f155-44e2-8e11-d72f6270c936" />

<img width="392" height="57" alt="image" src="https://github.com/user-attachments/assets/b94abf8f-85ca-4a37-b80c-3f4d887bf21c" />

<img width="379" height="89" alt="image" src="https://github.com/user-attachments/assets/4c5ea624-f999-4c56-9206-377dd3695506" />

# COLOCAR UNA CAPTURA DE PANTALLA

**Si se visualiza el mensaje command not found, considerar**
El problema se debe a que no se ha asignado un terminal de salida al contenedor al ejecutar el comando. Cuando usas docker exec -i jenkins-server /bin/bash en Windows, el comando se ejecuta pero no hay un terminal asignado para mostrar la salida del comando.


### Para ejecutar un shell interactivo bidireccional en un contenedor de Docker especificado.
Ejecutar un shell interactivo bidireccional en un contenedor de Docker significa abrir una sesión de shell en el contenedor que permite la interacción bidireccional entre la terminal local y el contenedor. Es decir, puedes enviar comandos desde tu terminal local al contenedor y recibir la salida de esos comandos de vuelta en tu terminal local, al igual que si estuvieras trabajando directamente en la terminal del contenedor.

![Imagen](jenkins-it.PNG)
```
docker exec -i-t <nombre contenedor> <programa o comando>
```
ó
```
docker exec -it <nombre contenedor> <programa o comando>
```

### Ahora puedes acceder al contenedor de jenkins y obtener la contraseña ubicada en /var/jenkins_home/secrets/initialAdminPassword

<img width="852" height="75" alt="image" src="https://github.com/user-attachments/assets/dd13e572-86e9-4a68-b6b2-e985e048ab7f" />

# COMPLETAR

### Colocar una captura de pantalla de la ventana que aparece después de colocar la contraseña.

**Para este punto no es necesario continuar con la instalación de Jenkins**


### Para ver los logs de un contenedor

```
docker logs -n <cantidad de líneas> <nombre o id del contenedor> 
```

```
docker logs mi-jenkins
```

<img width="924" height="799" alt="image" src="https://github.com/user-attachments/assets/8a06dd23-c514-455f-9df0-ff02b849e1d3" />

-t: para incluir la fecha y la hora

