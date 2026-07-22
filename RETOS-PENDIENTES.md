# Continuación individual · A11y Agent Arena

Estos retos no tienen un prompt oficial. El objetivo es aprender a dirigir un
agente: decidir qué pedirle, cuestionar sus decisiones y transformar lo
aprendido en un método reutilizable.

Utiliza tu usuario de GitHub o un alias como identificador. Tu único artefacto
de entrega debe quedar en:

```text
submissions/<participante>/audit-a11y/
```

Trabaja mediante prompts. No edites la skill ni ejecutes comandos manualmente.
No guardes los informes de entrenamiento: conserva únicamente el método.

## Reto 2 · Dale un navegador

### Misión

Consigue que tu agente pueda utilizar el MCP oficial de Playwright y convierta
esa capacidad en una mejora real de su método de auditoría.

Una configuración escrita no demuestra que la integración funcione. Decide
qué prueba observable vas a exigirle.

### Campo de pruebas

- <https://a11y-agent-arena-challenges.vercel.app/training-1/>
- <https://a11y-agent-arena-challenges.vercel.app/training-2/>

### Condiciones de éxito

- Existe una ejecución real del navegador, no solo una instalación declarada.
- El agente deja de tratar la web como una única captura estática.
- La skill aprende cuándo necesita explorar navegación, estados o procesos.
- Los resultados importantes pueden reproducirse a partir de evidencia.
- El agente distingue lo observado de lo que todavía debe comprobarse.

### Antes de continuar

Responde para ti:

1. ¿Qué podía afirmar tu agente antes de tener navegador?
2. ¿Qué puede demostrar ahora que antes solo suponía?
3. ¿Qué sigue sin demostrar una captura del árbol de accesibilidad?

Actualiza la skill a partir de esas respuestas. No conserves el informe.

## Reto 3 · Otra forma de leer

### Misión

Añade al agente una segunda perspectiva sobre cómo se expone e interpreta una
interfaz. Antes de integrar nada, elige una interacción dinámica de Cita Clara
y escribe tu predicción: qué información aparecerá y en qué orden.

El sensor que debes investigar está publicado como:

```text
@weaaare/mcp-virtual-screen-reader-auditor
```

### Campo de pruebas

- <https://a11y-agent-arena-challenges.vercel.app/training-2/>

### Condiciones de éxito

- El agente demuestra una sesión e interacción reales con el sensor.
- Obtiene un registro observable y lo compara con tu predicción previa.
- La skill decide cuándo esta perspectiva aporta evidencia relevante.
- El agente contrasta señales cuando distintas herramientas no cuentan la
  misma historia.
- Sus conclusiones expresan con precisión qué representa el simulador y qué no.

### Antes de entregar

Responde para ti:

1. ¿Qué parte de tu predicción era una suposición?
2. ¿Qué evidencia nueva cambió el método del agente?
3. ¿Qué conclusión seguiría necesitando tecnología asistiva real o una persona?

Actualiza la skill a partir de esas respuestas. No conserves el informe.

## Entrega

Cuando consideres que el agente está preparado, esta parte sí puede delegarse
de forma explícita:

```text
Usa $submit-a11y-agent para revisar y entregar mi agente auditor individual.
Mi identificador es <participante>. Devuélveme la URL de la pull request y no
la fusiones.
```

`main` está protegida. La pull request quedará abierta hasta su revisión.

## Qué compartir en Discord

No publiques una lista completa. Comparte el hallazgo que mejor demuestre el
comportamiento de tu agente y explica brevemente:

- qué barrera cree haber encontrado;
- qué evidencia la sostiene;
- qué cambió en el agente después de los dos retos;
- qué limitación importante conserva.

La próxima clase contrastaremos las respuestas, descubriremos los falsos
positivos y elegiremos el agente auditor individual más sólido.
