# 🐳 Tip Docker: Usa `.dockerignore` para excluir archivos innecesarios

Cuando construyes una imagen Docker, por defecto se incluye todo el contenido del directorio donde está el `Dockerfile`. Esto puede hacer que tu imagen sea **más pesada** si tienes archivos como:

```git
- `.git/`
- `node_modules/`
- Archivos `.log`
- Carpetas de compilación como `bin/` y `obj/`
- Archivos temporales o de configuración local
```

---

## ✅ ¿Cómo solucionarlo?

Crea un archivo llamado `.dockerignore` en el mismo directorio que tu `Dockerfile` y agrega lo siguiente:

```dockerignore
.git
*.log
node_modules
bin/
obj/
*.md
```

Esto le dice a Docker que ignore esos archivos al construir la imagen, lo que mejora el rendimiento y reduce el tamaño.

## 🧪 Beneficios

- Imágenes más ligeras.
- Construcción más rápida.
- Menor riesgo de incluir archivos sensibles o innecesarios.
