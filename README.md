🏥 **MyVaccine Web Application**
 
📝 **Descripción**
 
MyVaccine es una aplicación web desarrollada en **.NET 7,** diseñada para gestionar la administración y el registro de vacunas. La aplicación y su base de datos SQL Server se despliegan usando **contenedores Docker,** lo que permite empaquetar todo el proyecto y ejecutarlo de forma consistente.
 
❗ **Problema**
 
El registro y seguimiento de vacunas requiere una base de datos persistente y una API funcional. Al trabajar con una computadora portátil de poca memoria RAM, ejecutar Docker + SQL Server + Flutter al mismo tiempo genera dificultades de rendimiento.
 
💡 **Solución**
 
**Utilizamos  ``` docker compose up ```  para levantar dos contenedores:**
 
1. El contenedor de la **API .NET MyVaccine**

2. El contenedor de **SQL Server 2019**
 
Docker se encarga de construir la imagen de la API, crear la red, descargar las dependencias y ejecutar los servicios.
 
📦 **Comandos utilizados**

```
docker compose up
flutter pub get
flutter run
```

📸 **Evidencias**
 
**1. Docker construyendo la imagen de la API**
 
Docker descarga las capas de .NET SDK, copia los archivos del proyecto y construye la imagen de MyVaccine.

<img width="1366" height="768" alt="doker construyendo la imagen de tu bakend  NET" src="https://github.com/user-attachments/assets/3f9944d7-f743-4c6b-8ef9-4a5795bfb5b2" />



**2. Docker crea los contenedores**
 
Se observa que la imagen de la API queda marcada como **Built,** se crea la red y se crean los dos contenedores. También aparece el primer error: SQL Server necesita mínimo 2 GB de RAM.

<img width="1366" height="734" alt="evidencia de memoria" src="https://github.com/user-attachments/assets/f51c9f7f-f179-49dd-ba64-128f52903db2" />

 
**3. El backend de .NET levanta correctamente**
 
La API MyVaccine logra arrancar, se muestra el mensaje:

```
Application started. Press Ctrl+C to shut down. 
 Now listening on: http://[::]:80
```

✅ **El backend funcionó exitosamente**

<img width="1366" height="768" alt="muestra de finalizacion encendida App" src="https://github.com/user-attachments/assets/c75f96b1-9c7a-48fd-bc99-159d2d078ac8" />


**4. Flutter falla al compilar**
 
Al intentar ejecutar la app Flutter para conectarse con la API, la computadora se satura de memoria y aparece:

 ```Failed to compile application.```

❌ **No se logró levantar la interfaz Flutter por falta de RAM**

<img width="1358" height="730" alt="flutter_fallo_compilacion por falta de ram" src="https://github.com/user-attachments/assets/54c90f4a-b881-410c-8407-dcec24f59ae0" />


**5. Contenedor activo en Docker Desktop**
 
Esta captura confirma que el contenedor de MyVaccine quedó ejecutándose dentro de Docker, consumiendo memoria de la máquina.

<img width="1366" height="768" alt="contenedor_activo_docker_desktop png" src="https://github.com/user-attachments/assets/9ea68fb0-e0dd-4579-9f7e-eafbc2dfc268" />




 
⚠️ **Dificultad encontrada**
 
Mi laptop tiene poca memoria RAM. Aunque el backend .NET en Docker logró ejecutarse, la aplicación Flutter no alcanzó a compilarse porque el consumo de memoria fue muy alto.



 
👤 **Datos del estudiante**

Juan David Moya Corrales

CC: 1045526408

Curso: Optativa I

Código del curso: 650202015 -1
