# 📦 Mini Tutorial: Compartir una Imagen Docker como Archivo `.tar`

Este tutorial te guía paso a paso para exportar una imagen Docker como archivo `.tar`, compartirla y cargarla en otro equipo.

---

## ✅ Paso 1: Exportar la imagen Docker

Desde PowerShell o CMD, ejecuta:

docker save -o icmtools.tar icmtools

- icmtools: es el nombre de tu imagen Docker.
- icmtools.tar: es el archivo que se generará y que puedes compartir.

## 📤 Paso 2: Compartir el archivo
Puedes enviar el archivo icmtools.tar por:

- USB
- Red local
- Correo electrónico (si no es muy pesado)
- Servicios en la nube como OneDrive, Google Drive, etc.

## ✅ Paso 3: Importar la imagen en otro equipo
En el equipo destino, abre PowerShell o CMD y ejecuta:
docker load -i icmtools.tar

Esto cargará la imagen en el Docker local del equipo receptor.

## 🧪 Paso 4: Verificar que la imagen se cargó correctamente
Ejecuta el siguiente comando para verificar:

docker images

Deberías ver icmtools en la lista de imágenes disponibles.
