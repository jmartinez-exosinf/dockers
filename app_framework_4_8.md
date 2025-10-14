# 🐳 Tutorial: Crear y Ejecutar una Aplicación .NET Framework 4.8 en Contenedores Windows con Docker Desktop

---

## 📁 Paso 1: Publicar la Aplicación desde Visual Studio

1. Abre tu proyecto en Visual Studio.
2. Haz clic derecho sobre el proyecto y selecciona **Publicar**.
3. Elige **Carpeta** como destino de publicación.
4. Selecciona una ruta de publicación, por ejemplo: `C:\MiApp\publish`.
5. Haz clic en **Publicar**.

Esto generará una carpeta `publish/` con todos los archivos necesarios para ejecutar tu aplicación en IIS.

---

## 📄 Paso 2: Crear el archivo Dockerfile

1. Crea un archivo llamado `Dockerfile` (sin extensión) en la raíz del proyecto o junto a la carpeta `publish/`.
2. Agrega el siguiente contenido:


# Imagen base con IIS y .NET Framework 4.8
```cmd
FROM mcr.microsoft.com/dotnet/framework/aspnet:4.8
```

# Establece el directorio de trabajo en IIS
```cmd
WORKDIR /inetpub/wwwroot
```

# Copia los archivos publicados de tu aplicación
```cmd
COPY publish/ .
```cmd

# Exponer el puerto HTTP
```cmd
EXPOSE 80
```

📝 Explicación de cada línea

- FROM: Usa una imagen oficial de Microsoft con IIS y .NET Framework 4.8.
- WORKDIR: Define el directorio donde IIS espera los archivos de la aplicación.
- COPY: Copia los archivos publicados desde la carpeta publish/ al contenedor.
- EXPOSE: Expone el puerto 80 para que la aplicación sea accesible vía HTTP.

🔧 Paso 3: Construir la imagen Docker

Abre PowerShell o CMD en el directorio donde se encuentra el Dockerfile.

Ejecuta el siguiente comando:

```cmd
docker build -t icmtools .
```

Asegúrate de que el punto (.) al final del comando indica el contexto de construcción actual.

🚀 Paso 4: Ejecutar el contenedor

Ejecuta el siguiente comando para iniciar el contenedor:

```cmd
docker run -d -p 8080:80 icmtools
```
