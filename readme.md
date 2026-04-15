[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/lX5aAGcE)
# Laboratorio 1: Lo que callamos los ingenieros 🤓 (Introducción a Git)

Bienvenido/a a tu **primer laboratorio de Git**.  
En este ejercicio aprenderás los comandos básicos de Git (`add`, `commit`, `push`, `branch`, `merge`) usando creatividad.

La idea es que imagines que estás escribiendo **un diario de un ingeniero** en archivos de texto, y Git será tu herramienta para guardar cada paso de tu "diario oculto".

IMPORTANTE: Leer detenidamente las instrucciones del laboratorio.

---

## 📝 Información del Estudiante

**Completa la siguiente información antes de comenzar:**

- **Nombre completo:** [Escribe tu nombre completo aquí]
- **Número de estudiante:** [Tu número/código de estudiante]
- **Carrera:** [Tu carrera/programa académico]
- **Fecha de inicio:** [Fecha en que comenzaste el laboratorio]

> **📋 Instrucción**: Edita este archivo README.md y completa tu información personal arriba. Esto debe ser tu **primer commit** del laboratorio.

---

## Objetivos
- Aprender a crear commits y subirlos a GitHub.  
- Practicar cómo se usan ramas en Git.  
- Realizar un **merge** entre ramas.  
- Ver cómo GitHub Actions puede **autocalificar** tu trabajo.  

---

## 🛠️ Requisitos
- Tener una cuenta en [GitHub](https://github.com).  
- Tener Git instalado en tu computadora.
- Visual Studio Code (última versión)

---

## 🔑 Configuración de Token de GitHub (Importante)

GitHub requiere autenticación para realizar operaciones como `push`. Sigue estos pasos para crear un **token de acceso personal clásico**:

### 1. Crear el Token
1. Ve a GitHub y haz clic en tu **foto de perfil** (esquina superior derecha)
2. Selecciona **Settings** (Configuración)
3. En el menú lateral izquierdo, busca **Developer settings** 
4. Haz clic en **Personal access tokens** → **Tokens (classic)**
5. Haz clic en **Generate new token** → **Generate new token (classic)**

### 2. Configurar el Token
- **Note**: Escribe algo descriptivo como "Laboratorio Git - Desarrollo Web"
- **Expiration**: Selecciona **90 days** (o el tiempo que necesites)
- **Scopes**: Marca las siguientes casillas:
  - ✅ **repo** (acceso completo a repositorios)
  - ✅ **workflow** (actualizar archivos de GitHub Actions)

### 3. Generar y Guardar
1. Haz clic en **Generate token**
2. **⚠️ MUY IMPORTANTE**: Copia el token inmediatamente y guárdalo en un lugar seguro
3. **🔴 CRÍTICO**: **NO podrás verlo de nuevo** una vez que salgas de la página

> **🚨 ATENCIÓN ESTUDIANTES**: 
> 
> **GUARDA ESTE TOKEN EN UN LUGAR SEGURO Y NO LO PIERDAS**
> 
> - 📝 **Guárdalo en**: Un archivo de texto seguro, administrador de contraseñas, o nota protegida
> - 🔄 **Lo necesitarás para**: Este laboratorio Y TODOS los laboratorios futuros del curso
> - ⏰ **Si lo pierdes**: Tendrás que crear uno nuevo y reconfigurar todo
> - 🎯 **Recomendación**: Anótalo también en papel como respaldo
> 
> **Este token es tu "llave" para subir código a GitHub durante todo el semestre**

### 4. Usar el Token
Cuando Git te pida credenciales:
- **Username**: Tu nombre de usuario de GitHub
- **Password**: Pega tu token (NO tu contraseña de GitHub)

> 💡 **Tip**: Algunos sistemas pueden guardar las credenciales automáticamente después del primer uso.
> ⭐ **Recordatorio Final**: Este mismo token lo usarás en TODOS los laboratorios del curso. ¡No lo pierdas!

---

## Instrucciones

### 1. Clonar este repositorio
Abre tu terminal y ejecuta:

```bash
git clone <url-de-tu-repo>
cd <nombre-del-repo>
```

### 2. Completar información personal (PRIMER COMMIT)
1. Abre el archivo `readme.md` en tu editor de código
2. Completa tu información en la sección "📝 Información del Estudiante"
3. Guarda el archivo y ejecuta:

```bash
git add readme.md
git commit -m "Agregar información personal del estudiante"
git push origin main
```

### 3. Crear tu archivo secreto
Dentro del repositorio, crea un archivo llamado diario.txt con el siguiente contenido:

```
Día 1: Hoy aprendí a usar Git.
```

Guarda el archivo y luego ejecuta:
```bash
git add diario.txt
git commit -m "Añadir Día 1 en mi diario secreto"
git push origin main
```

### 4. Escribir nuevas entradas al diario
```
Día 2: Hice mi primer commit y push a GitHub.
```

Haz otro commit y push:
```bash
git add .
git commit -m "Añadir Día 2 en mi diario secreto"
git push origin main
```

### 5. Tu lado oculto en otra rama
Crea una rama llamada recuerdos:
```bash
git branch recuerdos
git checkout recuerdos
```

Dentro de esa rama, crea un archivo llamado recuerdos.txt con el contenido:

```bash
Recuerdo: Mi primer branch.
```

Haz commit y push:
```bash
git add recuerdos.txt
git commit -m "Añadir recuerdos secretos"
git push origin recuerdos
```

### 6. Uniendo multiversos (merge)
Regresa a la rama principal y combina tus recuerdos:
```bash
git checkout main
git merge recuerdos
git push origin main
```
## ✅ Calificación

Cada vez que hagas push, el repositorio revisará automáticamente si:
	•	Completaste tu información personal en el README.md
	•	Existe diario.txt con Día 1 y Día 2.
	•	Existe recuerdos.txt con la palabra Recuerdo.
	•	Se realizó el merge correctamente.

**Puntuación: 10/10 puntos**

Si todo está bien verás un visto (✔️) verde en la pestaña Actions de tu repositorio.
Si falta algo o tienes un error, verás una ❌ y un mensaje que te dirá qué corregir.

---

## 🔧 Solución de Problemas

### Error común: "fatal: not a git repository"
Si ves este error, asegúrate de estar en el directorio correcto del repositorio clonado.

### Error: "Permission denied" o "Authentication failed"
- Verifica que hayas configurado tu **token de GitHub** correctamente (ver sección anterior)
- Si usas HTTPS, asegúrate de usar tu token como contraseña, NO tu contraseña de GitHub
- Considera usar SSH si prefieres no escribir credenciales cada vez

### Error: "remote: Support for password authentication was removed"
Este error significa que estás intentando usar tu contraseña de GitHub en lugar del token. Solución:
1. Usa el **token de acceso personal** que creaste
2. Cuando Git pida credenciales, usa tu token como contraseña

### Los tests fallan
1. Revisa que hayas creado los archivos con los nombres exactos: `diario.txt` y `recuerdos.txt`
2. Verifica que el contenido incluya las frases exactas mencionadas en las instrucciones
3. Asegúrate de haber hecho el merge de la rama `recuerdos` a `main`

---

## 📚 Recursos Adicionales

- [Documentación oficial de Git](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Visualizador interactivo de Git](https://learngitbranching.js.org/)

---
## 👨🏻‍🏫 Información del docente

Si requieres contactarte con el docente puedes hacerlo a través de los siguientes canales

- 💬 UISEK - Google mail o chat: pablo.perez@uisek.edu.ec
- 💬 Pontificia Universidad Católica del Ecuador (PUCE) - Microsoft Teams o Outlook: paperez@puce.edu.ec