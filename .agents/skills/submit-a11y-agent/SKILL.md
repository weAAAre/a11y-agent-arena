---
name: submit-a11y-agent
description: Revisa y entrega mediante una pull request la skill de un equipo de A11y Agent Arena. Úsala cuando el grupo termine los ejercicios y pida validar, subir o presentar su agente al Final Boss.
---

# Entregar el agente

1. Identificar el slug del equipo.
2. Revisar que `submissions/<equipo>/audit-a11y/` solo contenga `SKILL.md` y referencias Markdown.
3. Validar el frontmatter y comprobar que no contiene informes, scripts, configuración MCP ni secretos.
4. Revisar que la skill haga visibles los cinco pasos de WCAG-EM 2.0, la evidencia, los límites y la revisión humana.
5. Mostrar al equipo un resumen breve de la entrega.
6. Consultar `gh repo view weAAAre/a11y-agent-arena --json viewerPermission`.
7. Crear la rama `team/<equipo>/agent`.
8. Añadir exclusivamente la carpeta del equipo y crear el commit `feat(agent): submit <equipo> accessibility auditor`.
9. Si existe permiso de escritura, subir la rama a `origin`. Si no existe:
   - ejecutar `gh repo fork weAAAre/a11y-agent-arena --clone=false`;
   - obtener el login con `gh api user --jq .login`;
   - añadir o actualizar un remote `fork` apuntando al fork del usuario;
   - subir allí la rama.
10. Abrir una pull request contra `weAAAre/a11y-agent-arena:main`. Cuando proceda de un fork, indicar `--head <login>:team/<equipo>/agent`.
11. Incluir en la PR: equipo, estrategia del agente, especialidad y principal limitación.
12. Devolver la URL. No fusionar la pull request.

Detenerse si aparecen cambios ajenos al equipo o si GitHub CLI no está autenticado.
