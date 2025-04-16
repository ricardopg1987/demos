# Tutorial: Control de Versiones con Git y GitHub para un Proyecto HTML Simple

## Introducción

Este tutorial muestra cómo utilizar Git y GitHub para gestionar un proyecto simple de página web en HTML. Veremos desde la configuración inicial hasta la colaboración en equipo y resolución de conflictos.

## Índice
1. [Configuración inicial](#1-configuración-inicial)
2. [Creación del proyecto HTML](#2-creación-del-proyecto-html)
3. [Primeros pasos con Git](#3-primeros-pasos-con-git)
4. [Trabajando con GitHub](#4-trabajando-con-github)
5. [Trabajo en equipo y ramas](#5-trabajo-en-equipo-y-ramas)
6. [Resolución de conflictos](#6-resolución-de-conflictos)
7. [Flujo de trabajo avanzado](#7-flujo-de-trabajo-avanzado)
8. [Ventajas de Git y GitHub](#8-ventajas-de-git-y-github)

## 1. Configuración inicial

### Instalación de Git

Primero, necesitamos instalar Git en nuestro sistema:

**Windows**:
- Descargar el instalador desde [git-scm.com](https://git-scm.com/download/win)
- Seguir el asistente de instalación

**macOS**:
```bash
# Con Homebrew
brew install git

# O desde el instalador
# https://git-scm.com/download/mac
```

**Linux**:
```bash
# Ubuntu/Debian
sudo apt-get update
sudo apt-get install git

# Fedora
sudo dnf install git
```

### Configuración básica

Configuramos nuestra identidad en Git:

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu.email@ejemplo.com"
```

### Crear cuenta en GitHub

1. Visitar [github.com](https://github.com/)
2. Registrarse con un correo electrónico y contraseña
3. Verificar el correo electrónico

## 2. Creación del proyecto HTML

Crearemos una página web simple para gestionar con Git. 

### Estructura del proyecto

```
proyecto-web/
├── index.html
├── css/
│   └── estilos.css
└── js/
    └── script.js
```

### Código HTML (index.html)

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Página Web con Git</title>
    <link rel="stylesheet" href="css/estilos.css">
</head>
<body>
    <header>
        <h1>Bienvenido a Mi Página Web</h1>
        <nav>
            <ul>
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#acerca">Acerca de</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <section id="inicio">
            <h2>Página principal</h2>
            <p>Esta es una página web simple para demostrar el uso de Git y GitHub.</p>
        </section>
    </main>
    
    <footer>
        <p>&copy; 2025 - Proyecto demostración Git</p>
    </footer>
    
    <script src="js/script.js"></script>
</body>
</html>
```

### CSS básico (css/estilos.css)

```css
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: white;
    padding: 1rem;
}

nav ul {
    display: flex;
    list-style: none;
    padding: 0;
}

nav ul li {
    margin-right: 1rem;
}

nav a {
    color: white;
    text-decoration: none;
}

main {
    padding: 2rem;
}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 1rem;
}
```

### JavaScript básico (js/script.js)

```javascript
document.addEventListener('DOMContentLoaded', function() {
    console.log('La página se ha cargado correctamente');
});
```

## 3. Primeros pasos con Git

### Inicializar repositorio

Primero, creamos una carpeta para nuestro proyecto y nos posicionamos en ella:

```bash
mkdir proyecto-web
cd proyecto-web
```

Ahora inicializamos Git:

```bash
git init
```

Este comando crea un repositorio Git vacío en el directorio actual. Verás un mensaje como:
```
Initialized empty Git repository in /ruta/a/proyecto-web/.git/
```

### Creando archivos del proyecto

Crearemos los archivos de nuestro proyecto siguiendo la estructura mencionada anteriormente.

### Revisando el estado

Para ver qué archivos están pendientes de seguimiento, usamos:

```bash
git status
```

Veremos algo como:
```
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html
        css/
        js/

nothing added to commit but untracked files present (use "git add" to track)
```

### Añadiendo archivos al área de preparación

Añadimos los archivos para que Git los rastree:

```bash
git add index.html css/estilos.css js/script.js
```

O para añadir todos los archivos:

```bash
git add .
```

Verificamos nuevamente:

```bash
git status
```

Ahora veremos:
```
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   index.html
        new file:   css/estilos.css
        new file:   js/script.js
```

### Creando nuestro primer commit

Un commit es una "instantánea" de nuestro proyecto en un momento dado:

```bash
git commit -m "Primer commit: estructura básica del sitio web"
```

El resultado:
```
[main (root-commit) f7d2e3a] Primer commit: estructura básica del sitio web
 3 files changed, 75 insertions(+)
 create mode 100644 index.html
 create mode 100644 css/estilos.css
 create mode 100644 js/script.js
```

### Visualizando el historial

```bash
git log
```

Esto muestra la historia de commits:
```
commit f7d2e3a8d9e1c5b2a6f8d9e7c4b1a5f2d3e6a9b8 (HEAD -> main)
Author: Tu Nombre <tu.email@ejemplo.com>
Date:   Mar 15 10:30:15 2025 -0500

    Primer commit: estructura básica del sitio web
```

## 4. Trabajando con GitHub

### Crear un repositorio en GitHub

1. Inicia sesión en [GitHub](https://github.com/)
2. Haz clic en el botón "+" en la esquina superior derecha y selecciona "New repository"
3. Nombra tu repositorio "proyecto-web"
4. No inicialices el repositorio con README, .gitignore o licencia
5. Haz clic en "Create repository"

### Vinculando repositorio local con GitHub

Después de crear el repositorio en GitHub, enlazamos nuestro repositorio local:

```bash
git remote add origin https://github.com/tu-usuario/proyecto-web.git
```

### Subiendo cambios a GitHub

Subimos nuestros cambios al repositorio remoto:

```bash
git push -u origin main
```

Ahora podrás ver tu código en GitHub si visitas https://github.com/tu-usuario/proyecto-web

### Creando un README.md

Es buena práctica incluir un archivo README.md que explique el proyecto:

```bash
# Creamos el archivo README.md
echo "# Proyecto Web Demo
Un proyecto simple para demostrar el uso de Git y GitHub con HTML, CSS y JavaScript.

## Descripción
Este repositorio contiene una página web básica creada con fines educativos para aprender control de versiones." > README.md

# Añadimos y confirmamos el cambio
git add README.md
git commit -m "Añadir archivo README.md"

# Subimos el cambio a GitHub
git push
```

## 5. Trabajo en equipo y ramas

Las ramas (branches) permiten trabajar en funcionalidades sin afectar la rama principal.

### Creando una nueva rama

Imaginemos que queremos añadir una sección "Acerca de":

```bash
git checkout -b feature/seccion-acerca
```

Este comando crea una nueva rama y nos cambia a ella.

### Modificando el código en la nueva rama

Editamos el archivo index.html para añadir la sección "Acerca de":

```html
<!-- Añadimos después de la sección "inicio" -->
<section id="acerca">
    <h2>Acerca de</h2>
    <p>Somos un equipo apasionado por el desarrollo web y las buenas prácticas de código.</p>
    <p>Este proyecto demuestra cómo utilizar Git y GitHub para gestionar versiones de código.</p>
</section>
```

### Guardando los cambios

```bash
git add index.html
git commit -m "Añadir sección Acerca de"
```

### Publicando la rama en GitHub

```bash
git push -u origin feature/seccion-acerca
```

### Creando un Pull Request

1. Ve a tu repositorio en GitHub
2. Verás un mensaje sobre tu rama recién subida con un botón "Compare & pull request"
3. Haz clic en ese botón
4. Añade un título y descripción para tu Pull Request
5. Haz clic en "Create pull request"

### Revisando y mezclando el Pull Request

En un entorno real, otro miembro del equipo revisaría tus cambios. Para este ejemplo:

1. Ve a la página del Pull Request
2. Revisa los cambios en la pestaña "Files changed"
3. Haz clic en "Merge pull request" y luego "Confirm merge"

### Actualizando la rama principal local

```bash
git checkout main
git pull
```

## 6. Resolución de conflictos

Los conflictos ocurren cuando Git no puede combinar automáticamente los cambios.

### Simulando un conflicto

Imaginemos que dos desarrolladores modifican la misma línea:

Desarrollador 1 (tú en la rama main):
```bash
git checkout main

# Edita el título en index.html
# Cambia: <h1>Bienvenido a Mi Página Web</h1>
# Por: <h1>Bienvenido a Nuestro Proyecto Git</h1>

git add index.html
git commit -m "Actualizar título de la página"
git push
```

Desarrollador 2 (simulado en una nueva rama):
```bash
git checkout -b feature/nuevo-titulo

# Edita el mismo título pero diferente
# Cambia: <h1>Bienvenido a Mi Página Web</h1>
# Por: <h1>Aprende Git con nuestro ejemplo</h1>

git add index.html
git commit -m "Cambiar título principal"
git push -u origin feature/nuevo-titulo
```

### Creando y resolviendo el conflicto

Ahora intenta mezclar la rama:

```bash
git checkout main
git merge feature/nuevo-titulo
```

Verás un mensaje de error:
```
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```

Abre index.html y verás algo como:
```html
<header>
<<<<<<< HEAD
    <h1>Bienvenido a Nuestro Proyecto Git</h1>
=======
    <h1>Aprende Git con nuestro ejemplo</h1>
>>>>>>> feature/nuevo-titulo
    <nav>
        <!-- ... -->
    </nav>
</header>
```

Resuelve el conflicto editando el archivo:
```html
<header>
    <h1>Aprende Git con nuestro Proyecto</h1>
    <nav>
        <!-- ... -->
    </nav>
</header>
```

Guarda el archivo y completa la fusión:
```bash
git add index.html
git commit -m "Resolver conflicto de título"
git push
```

## 7. Flujo de trabajo avanzado

### Etiquetas (versiones)

Para marcar versiones importantes del proyecto:

```bash
git tag -a v1.0 -m "Primera versión estable"
git push origin v1.0
```

### Navegando en la historia

Para ver cómo estaba el proyecto en un commit anterior:

```bash
# Ver el historial
git log --oneline

# Ejemplo: 
# a1b2c3d Resolver conflicto de título
# e4f5g6h Cambiar título principal
# i7j8k9l Actualizar título de la página
# m0n1o2p Añadir sección Acerca de
# q3r4s5t Añadir archivo README.md
# u6v7w8x Primer commit: estructura básica del sitio web

# Volver a un commit específico
git checkout e4f5g6h

# Para volver al estado actual
git checkout main
```

### Archivo .gitignore

Crea un archivo .gitignore para excluir archivos que no quieres en el repositorio:

```
# .gitignore
node_modules/
.DS_Store
.vscode/
*.log
```

```bash
git add .gitignore
git commit -m "Añadir archivo .gitignore"
git push
```

## 8. Ventajas de Git y GitHub

### Ventajas de usar control de versiones (Git)

1. **Historial completo de cambios**: Puedes ver quién modificó qué, cuándo y por qué.
2. **Trabajo paralelo**: Múltiples desarrolladores pueden trabajar simultáneamente sin pisarse.
3. **Ramas**: Desarrollo de funcionalidades aisladas que no afectan al código principal.
4. **Recuperación**: Puedes volver a cualquier punto de la historia del proyecto.
5. **Responsabilidad**: Cada cambio está asociado a un autor, mejorando la rendición de cuentas.
6. **Experimentación segura**: Puedes probar ideas sin temor a dañar el proyecto.
7. **Resolución de conflictos**: Herramientas para manejar cambios contradictorios.

### Ventajas específicas de GitHub

1. **Colaboración remota**: Trabajo en equipo desde cualquier parte del mundo.
2. **Pull Requests**: Revisión de código y comentarios antes de integrar cambios.
3. **Issues**: Seguimiento de tareas, errores y mejoras.
4. **Wikis**: Documentación centralizada y mantenible.
5. **GitHub Pages**: Hospedaje gratuito para sitios web estáticos.
6. **Acciones de GitHub**: Automatización de pruebas y despliegues (CI/CD).
7. **Visibilidad**: Perfil profesional y portfolio para desarrolladores.
8. **Comunidad**: Participación en proyectos open source y aprendizaje colaborativo.
9. **Seguridad**: Detección de vulnerabilidades y dependencias obsoletas.
10. **Integración**: Conexión con herramientas de productividad y desarrollo.

## Conclusión

Git y GitHub son herramientas fundamentales para el desarrollo de software moderno. Permiten gestionar eficientemente los cambios en el código, facilitan la colaboración en equipo y proporcionan un entorno seguro para experimentar con nuevas ideas. Dominar estas herramientas mejorará significativamente tu flujo de trabajo y te preparará para trabajar en proyectos de cualquier tamaño.
