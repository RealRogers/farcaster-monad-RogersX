# Guía de Sincronización de Repositorios

## Misión: Sincronizar Repositorios

### Objetivo
Conectar tu trabajo local a un nuevo Fork en GitHub y subir tus cambios.

## Paso 1: Crear el Fork en GitHub

1. Ve a la página del [repositorio original](https://github.com/monad-developers/monad-miniapp-template) en GitHub.
2. Haz clic en el botón "Fork" en la esquina superior derecha.
3. Espera a que se cree el fork en tu cuenta.
4. Una vez creado, ve a la configuración del repositorio (Settings).
5. Cambia el nombre del repositorio a `farcaster-monad-RogersX`.
6. Haz clic en "Rename" para confirmar.

## Paso 2: Configurar el Repositorio Local

1. Abre una terminal en la raíz de tu proyecto.
2. Inicializa el repositorio Git (si no está ya inicializado):
   ```bash
   git init
   ```
3. Verifica el estado actual de Git:
   ```bash
   git status
   ```
4. Añade todos los archivos al área de preparación:
   ```bash
   git add .
   ```
5. Haz tu primer commit:
   ```bash
   git commit -m "Primer commit con mis cambios iniciales"
   ```

## Paso 3: Configurar los Remotos

1. Añade el repositorio original como "upstream":
   ```bash
   git remote add upstream https://github.com/monad-developers/monad-miniapp-template.git
   ```

2. Añade tu fork como "origin":
   ```bash
   git remote add origin https://github.com/tu-usuario/farcaster-monad-RogersX.git
   ```
   (Reemplaza `tu-usuario` con tu nombre de usuario de GitHub)

3. Verifica la configuración de los remotos:
   ```bash
   git remote -v
   ```
   Deberías ver:
   ```
   origin  https://github.com/tu-usuario/farcaster-monad-RogersX.git (fetch)
   origin  https://github.com/tu-usuario/farcaster-monad-RogersX.git (push)
   upstream  https://github.com/monad-developers/monad-miniapp-template.git (fetch)
   upstream  https://github.com/monad-developers/monad-miniapp-template.git (push)
   ```

## Paso 4: Subir los Cambios a GitHub

1. Asegúrate de que todos tus cambios estén confirmados:
   ```bash
   git status
   ```

2. Si hay cambios sin confirmar, haz un commit:
   ```bash
   git add .
   git commit -m "Descripción de los cambios realizados"
   ```

3. Sube los cambios a tu fork (primera vez):
   ```bash
   git push -u origin main
   ```
   (Usa `master` en lugar de `main` si esa es tu rama principal)

## Flujo de Trabajo para Futuros Cambios

1. Sincroniza tu rama principal con los cambios del repositorio original:
   ```bash
   git checkout main
   git fetch upstream
   git merge upstream/main
   ```

2. Crea una nueva rama para tus cambios:
   ```bash
   git checkout -b nombre-de-tu-rama
   ```

3. Realiza y confirma tus cambios:
   ```bash
   git add .
   git commit -m "Descripción de los cambios"
   ```

4. Sube la rama a tu fork:
   ```bash
   git push -u origin nombre-de-tu-rama
   ```

5. Crea un Pull Request desde tu fork al repositorio original si deseas contribuir tus cambios.

## Solución de Problemas Comunes

### Si recibes un error de autenticación:
1. Configura tus credenciales de Git:
   ```bash
   git config --global user.name "Tu Nombre"
   git config --global user.email "tu@email.com"
   ```
2. Usa un token de acceso personal en lugar de contraseña.

### Si hay conflictos al hacer merge:
1. Resuelve los conflictos manualmente en los archivos marcados.
2. Añade los archivos resueltos:
   ```bash
   git add .
   ```
3. Completa el merge:
   ```bash
   git commit -m "Resuelve conflictos de merge"
   ```
