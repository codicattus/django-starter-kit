# Django Starter Kit

**Django Starter Kit** es una plantilla base para crear proyectos **Django** rápidamente en un entorno de desarrollo **contenedorizado** con **Docker** y **Devcontainers** (VSCode).

Está pensada para aprender o iniciar proyectos de forma sencilla, sin configuraciones complicadas.

---

## Características principales

-  **Python 3.13**
-  **Django 5.2.7**
-  **SQLite** como base de datos por defecto (sin configuración adicional)
-  **Docker** y **Devcontainers** para un entorno de desarrollo idéntico en cualquier máquina
-  **Bind mount** del código fuente local (`src/`) dentro del contenedor → los cambios se reflejan al instante
-  Estructura limpia y minimalista, ideal para empezar nuevos proyectos

---

##  Requisitos previos

Antes de usar esta plantilla asegúrate de tener instalado:

- [Docker](https://www.docker.com/)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Extensión Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

---

##  Cómo usar este template

1. **Clona** el repositorio:

   ```bash
   git clone https://github.com/codicattus/django-starter-kit nombre-de-tu-proyecto
   cd nombre-de-tu-proyecto

2. Copia el archivo .env.example a .env:
    ```bash
    cp .env.example .env

3. Edita el archivo .env para ajustar cualquier valor necesario, como claves secretas, puertos, usuarios o contraseñas.

4. Elimina el archivo .gitkeep (solo es necesario para mantener la carpeta src en el repositorio)

    ```bash
    rm src/.gitkeep

5. Abre el proyecto en VSCode y selecciona
→ “Reopen in Container” (F1 -> Dev Containers: Reopen in Container)
(esto construirá automáticamente el entorno con Docker).

6. Abre una terminal dentro de VSCode (puedes comprobar las versiones de Python y Django instaladas) y crea un nuevo proyecto Django.

    ```bash
    python -m django startproject mysite .

7. Crea la base de datos y arranca el servidor:

    ```bash
    python manage.py migrate
    python manage.py runserver 0.0.0.0:8000

8. Accede a tu navegador:
    [http://localhost:8000]

---
### Estructura del proyecto

El código fuente del proyecto Django se guarda dentro de la carpeta `src/`.

Si deseas crear un nuevo proyecto Django a partir de esta plantilla, 
simplemente clona de nuevo el repositorio con otro nombre de carpeta:

```bash
git clone https://github.com/codicattus/django-starter-kit mi_nuevo_proyecto
``` 
Así mantendrás separados tus proyectos y cada uno tendrá su propio entorno `src/`.

El directorio src/ está montado en el contenedor como volumen (bind mount), de modo que los cambios que hagas en tu código local se reflejan inmediatamente dentro del entorno Docker.

---

## Ideal para

- Iniciar proyectos Django de forma rápida

- Clases y talleres de desarrollo web

- Prototipos o entornos de aprendizaje reproducibles

## Consejos

- Puedes cambiar fácilmente a PostgreSQL o MySQL modificando el docker-compose.yml.

- Si quieres añadir dependencias, usa requirements.txt dentro del contenedor.

- Este entorno está pensado para desarrollo, no producción.

## Licencia

MIT License © 2025

#### Desarrollado como entorno base para cursos y proyectos de aprendizaje con Django + Docker.