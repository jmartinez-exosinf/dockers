# 📝 ¿Por qué documentar tu Dockerfile?
El Dockerfile es el archivo que define cómo se construye una imagen Docker. Aunque es un archivo técnico, también debe ser legible y entendible para otros desarrolladores (¡o para ti mismo en el futuro!).

# ✅ Buenas prácticas para documentar tu Dockerfile

## 1. Usa comentarios (#) para explicar cada paso
```dockerfile
# Usamos una imagen base ligera de Node.js
FROM node:18-alpine

# Establecemos el directorio de trabajo
WORKDIR /app

# Copiamos los archivos de configuración primero para aprovechar el cache
COPY package*.json ./

# Instalamos dependencias
RUN npm install

# Copiamos el resto del código fuente
COPY . .

# Exponemos el puerto que usará la app
EXPOSE 3000

# Comando para iniciar la aplicación
CMD ["npm", "start"]
```

## 2. Explica decisiones técnicas
- ¿Por qué elegiste alpine?
- ¿Por qué copiaste primero los package.json?
- ¿Por qué usas CMD en lugar de ENTRYPOINT?

## 3. Incluye instrucciones en el README o comentarios adicionales
- Cómo construir la imagen:
```dockerfile
docker build -t mi-app .Mostrar más líneas
```

- Cómo correr el contenedor:
```dockerfile
docker run -p 3000:3000 mi-appMostrar más líneas
```

## 4. Documenta variables de entorno si usas ENV
```dockerfile
# Variable para definir el entorno de ejecución
ENV NODE_ENV=production
```

## 5. Agrega notas sobre seguridad o mantenimiento
- Por ejemplo, si estás instalando paquetes con apt-get, explica por qué y cómo se limpian los caches para reducir el tamaño.

---

# 🎯 Beneficios de documentar
- Facilita la colaboración.
- Reduce errores en builds y despliegues.
- Ayuda a nuevos desarrolladores a entender el entorno.
- Mejora la mantenibilidad del proyecto.
