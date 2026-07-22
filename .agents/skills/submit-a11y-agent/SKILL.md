---
name: submit-a11y-agent
description: Revisa y entrega mediante una pull request la skill individual de A11y Agent Arena. Úsala cuando una persona termine los retos y pida validar, subir o presentar su agente auditor.
---

# Entregar el agente

1. Identificar el slug del participante. Si su carpeta todavía no existe, detenerse:
   no hay un agente construido que entregar.
2. Revisar que `submissions/<participante>/audit-a11y/` solo contenga `SKILL.md` y referencias Markdown.
3. Validar el frontmatter y comprobar que no contiene informes, scripts, configuración MCP ni secretos.
4. Revisar que la skill haga visibles los cinco pasos de WCAG-EM 2.0, la evidencia, los límites y la revisión humana.
5. Mostrar a la persona un resumen breve de la entrega.
6. Consultar `gh repo view weAAAre/a11y-agent-arena --json viewerPermission`.
7. Crear la rama `participant/<participante>/agent`.
8. Añadir exclusivamente la carpeta del participante y crear el commit `feat(agent): submit <participante> accessibility auditor`.
9. Si existe permiso de escritura, subir la rama a `origin`. Si no existe:
   - ejecutar `gh repo fork weAAAre/a11y-agent-arena --clone=false`;
   - obtener el login con `gh api user --jq .login`;
   - añadir o actualizar un remote `fork` apuntando al fork del usuario;
   - subir allí la rama.
10. Abrir una pull request contra `weAAAre/a11y-agent-arena:main`. Cuando proceda de un fork, indicar `--head <login>:participant/<participante>/agent`.
11. Incluir en la PR: participante, estrategia del agente, especialidad y principal limitación.
12. Devolver la URL. No fusionar la pull request.

Detenerse si aparecen cambios ajenos al participante o si GitHub CLI no está autenticado.
