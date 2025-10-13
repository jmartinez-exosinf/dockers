📄 Crear el archivo Dockerfile
Crea un archivo llamado Dockerfile (sin extensión) en la raíz del proyecto o junto a la carpeta publish/.
✨ Contenido del Dockerfile

Imagen base con IIS y .NET Framework 4.8
```cmd
FROM mcr.microsoft.com/dotnet/framework/aspnet:4.8
```

Establece el directorio de trabajo en IIS
```cmd
WORKDIR /inetpub/wwwroot
```

Copia los archivos publicados de tu aplicación
```cmd
COPY publish/ .
```

Exponer el puerto HTTP
```cmd
EXPOSE 80
```

📝 Explicación de cada línea

FROM: Usa una imagen oficial de Microsoft con IIS y .NET Framework 4.8.
WORKDIR: Define el directorio donde IIS espera los archivos de la aplicación.
COPY: Copia los archivos publicados desde la carpeta publish/ al contenedor.
EXPOSE: Expone el puerto 80 para que la aplicación sea accesible vía HTTP.
