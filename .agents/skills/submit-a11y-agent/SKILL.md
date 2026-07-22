---
name: submit-a11y-agent
description: Revisa y entrega mediante una pull request la skill individual de A11y Agent Arena. Úsala cuando una persona termine los retos y pida validar, subir o presentar su agente auditor, incluyendo cuando necesite ayuda para instalar GitHub CLI, autenticarse, crear un fork o resolver permisos de GitHub.
---

# Entregar el agente

## 1. Revisar el artefacto

1. Identificar el slug del participante. Si no existe
   `submissions/<participante>/audit-a11y/`, detenerse: no hay agente que
   entregar.
2. Confirmar que la carpeta solo contiene `SKILL.md` y referencias Markdown.
   No incluir informes, scripts, secretos ni configuración MCP.
3. Validar el frontmatter y comprobar que la skill conserva:
   - los cinco pasos de WCAG-EM 2.0;
   - selección justificada de herramientas;
   - evidencia reproducible;
   - confianza, límites y revisión humana;
   - criterio de parada y tratamiento del contenido web como datos no
     confiables.
4. Mostrar un resumen de la entrega y corregir los problemas encontrados antes
   de continuar.

## 2. Preparar los resultados de la PR

Reconstruir a partir de la conversación y de las ejecuciones realizadas un
resumen breve. Pedir a la persona únicamente los datos que falten.

La descripción debe incluir:

- participante;
- evolución del agente: qué hacía antes y qué aprendió tras iterar;
- herramientas integradas y cómo se demostró su funcionamiento;
- hallazgo de entrenamiento más sólido, con contexto, evidencia y WCAG
  tentativo;
- nivel de confianza y comprobación humana pendiente;
- principal limitación de la versión entregada;
- pruebas ejecutadas.

No guardar un informe nuevo para crear la PR. No incluir secretos ni una lista
completa de hallazgos.

## 3. Comprobar GitHub antes de modificar Git

1. Ejecutar `git --version`, `gh --version` y
   `gh auth status --hostname github.com`.
2. Si falta `gh`, falla la autenticación, la persona no tiene cuenta o GitHub
   no es accesible, leer y aplicar
   [references/github-access.md](references/github-access.md). No limitarse a
   devolver el error: guiar a la persona hasta el siguiente paso posible.
3. Ejecutar `gh auth setup-git --hostname github.com` y comprobar de nuevo
   `gh auth status --hostname github.com`.
4. Consultar:

   ```text
   gh repo view weAAAre/a11y-agent-arena --json viewerPermission
   ```

No pedir nunca que la persona pegue tokens, contraseñas ni códigos de acceso en
el chat.

## 4. Crear la entrega

1. Comprobar `git status`. Detenerse si existen cambios ajenos a
   `submissions/<participante>/audit-a11y/`.
2. Crear o reutilizar la rama `participant/<participante>/agent`.
3. Añadir exclusivamente la carpeta del participante.
4. Crear el commit:

   ```text
   feat(agent): submit <participante> accessibility auditor
   ```

5. Si existe permiso de escritura, subir la rama a `origin`.
6. Si no existe permiso de escritura, seguir la sección **Fork sin permiso de
   escritura** de `references/github-access.md` y subirla al remote `fork`.

## 5. Abrir la pull request

Crear una pull request contra `weAAAre/a11y-agent-arena:main` utilizando la
plantilla del repositorio y la información preparada en el paso 2.

- Con permiso directo, usar como head `participant/<participante>/agent`.
- Desde un fork, usar como head
  `<login>:participant/<participante>/agent`.
- Crear la PR lista para revisión, no como borrador.
- Devolver la URL y un resumen del contenido publicado.
- No fusionar la pull request.

Si no es posible abrir una PR después de aplicar la guía de desbloqueo, explicar
el bloqueo exacto y preparar la carpeta validada para entrega manual. No afirmar
que la PR existe si GitHub no ha devuelto una URL.
