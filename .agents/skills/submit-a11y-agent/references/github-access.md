# Desbloquear la entrega en GitHub

Leer solo cuando falle la preparación o la publicación de la pull request.

## No existe una cuenta de GitHub

1. Pedir a la persona que abra <https://github.com/signup>.
2. Esperar a que cree la cuenta y verifique el correo.
3. Continuar con la autenticación. No solicitar credenciales en el chat.

## GitHub CLI no está instalado

Detectar el sistema operativo y explicar qué se va a instalar. Solicitar
confirmación antes de ejecutar una instalación en el sistema.

### macOS con Homebrew

```text
brew install gh
```

### Windows con WinGet

```text
winget install --id GitHub.cli --source winget
```

Después, cerrar la ventana completa de Windows Terminal y abrir una nueva para
actualizar `PATH`.

### Linux

Seguir la sección oficial de la distribución en
<https://github.com/cli/cli/blob/trunk/docs/install_linux.md>. No utilizar Snap.

Al terminar, comprobar:

```text
gh --version
```

## GitHub CLI no está autenticado

Ejecutar:

```text
gh auth login --hostname github.com --git-protocol https --web
```

Pedir a la persona que complete el flujo en su navegador. Después ejecutar:

```text
gh auth setup-git --hostname github.com
gh auth status --hostname github.com
```

No utilizar `--with-token` y no pedir que se copie un token en el chat.

## Fork sin permiso de escritura

1. Obtener el usuario autenticado:

   ```text
   gh api user --jq .login
   ```

2. Crear el fork sin clonar otra copia:

   ```text
   gh repo fork weAAAre/a11y-agent-arena --clone=false
   ```

   Si ya existe, continuar con ese fork.

3. Construir la URL HTTPS con el login obtenido:

   ```text
   https://github.com/<login>/a11y-agent-arena.git
   ```

4. Si existe un remote `fork`, actualizarlo. Si no existe, añadirlo:

   ```text
   git remote set-url fork https://github.com/<login>/a11y-agent-arena.git
   git remote add fork https://github.com/<login>/a11y-agent-arena.git
   ```

   Ejecutar solo una de las dos instrucciones según el estado real.

5. Subir la rama:

   ```text
   git push -u fork participant/<participante>/agent
   ```

6. Abrir la PR contra el repositorio original indicando el fork:

   ```text
   gh pr create --repo weAAAre/a11y-agent-arena --base main --head <login>:participant/<participante>/agent --title "feat(agent): submit <participante> accessibility auditor" --body-file <archivo-descripcion>
   ```

Crear `<archivo-descripcion>` como archivo temporal con los resultados exigidos
por la skill. No añadirlo al repositorio.

## Alternativa mediante la web

Si la persona tiene cuenta y navegador, pero no puede instalar `gh`:

1. Abrir <https://github.com/weAAAre/a11y-agent-arena/fork> y crear el fork.
2. En el fork, crear la rama `participant/<participante>/agent` desde `main`.
3. Subir a esa rama únicamente el contenido de
   `submissions/<participante>/audit-a11y/` y crear el commit.
4. Volver al repositorio original, abrir **Pull requests → New pull request →
   compare across forks**.
5. Elegir `weAAAre/a11y-agent-arena:main` como base y el fork y rama personales
   como comparación.
6. Completar la plantilla con los resultados y crear la pull request.
7. Copiar su URL y devolverla al chat del agente.

## GitHub no es accesible

Si la red o una política del dispositivo impide acceder a GitHub:

1. Mantener intacta la carpeta validada del participante.
2. Indicar su ruta exacta y enumerar los archivos que contiene.
3. Explicar que no se ha creado una PR.
4. Pedir que se comparta esa carpeta por el canal alternativo indicado por el
   instructor para publicarla cuando vuelva a existir acceso.

## Referencias oficiales

- Instalación de GitHub CLI: <https://github.com/cli/cli#installation>
- Autenticación: <https://cli.github.com/manual/gh_auth_login>
- Creación de forks: <https://cli.github.com/manual/gh_repo_fork>
- Pull requests desde forks:
  <https://docs.github.com/en/pull-requests/how-tos/create-pull-requests/creating-a-pull-request-from-a-fork>
