# Retos 2 y 3 · Guía para continuar en casa

En clase empezaste a construir una skill de auditoría de accesibilidad. Ahora
vas a mejorarla dos veces:

1. En el **Reto 2**, conseguirás que el agente pueda utilizar un navegador.
2. En el **Reto 3**, comprobarás la interfaz con un lector virtual.

No necesitas saber programar ni conocer de memoria cómo se instala un MCP. Tu
trabajo consiste en pedírselo al agente, comprobar que lo ha hecho de verdad y
decidir qué debe aprender la skill.

Calcula aproximadamente 30 minutos para cada reto. Hazlos en orden.

## 1. Prepara tu copia

Abre este repositorio completo en el agente que quieras utilizar.

Elige un identificador personal corto, preferiblemente tu usuario de GitHub y
sin espacios. Por ejemplo: `ana-garcia`.

Empieza la conversación con algo parecido a esto:

```text
Mi identificador para A11y Agent Arena es <participante>.

Trabaja solamente en submissions/<participante>/audit-a11y/. Si todavía no
existe, créalo a partir del starter. No modifiques el starter ni las entregas
de otras personas.

Antes de cambiar nada, revisa mi skill actual y explícame brevemente qué sabe
hacer y qué le falta.
```

No tienes que copiar carpetas, editar archivos ni ejecutar comandos: debe
hacerlo el agente.

## Cómo trabajar con el agente

No intentes resolver cada reto con un único prompt enorme. Utiliza una
conversación corta:

1. **Pregunta:** pídele que explique qué propone hacer.
2. **Decide:** acepta el plan o pídele que cambie lo que no entiendas.
3. **Comprueba:** no aceptes «ya está instalado»; pide una demostración real.
4. **Compara:** pregunta qué ha podido descubrir ahora que antes no podía.
5. **Conserva:** pídele que guarde lo aprendido en la skill, no en un informe.

Si utiliza una palabra o herramienta que no conoces, pregúntale qué significa
antes de continuar.

---

## Reto 2 · Dale un navegador

### Qué tienes que conseguir

Tu agente debe ser capaz de utilizar el **MCP oficial de Playwright** para abrir
una web e interactuar con ella. Después debe incorporar esa capacidad a su
método de auditoría.

No basta con que el agente escriba un archivo de configuración o diga que la
instalación ha terminado. Tiene que demostrar que puede controlar realmente el
navegador.

### Paso 1 · Entender la limitación actual

Pide al agente que revise su skill y te responda:

> ¿Qué partes de una auditoría no puedes comprobar todavía sin controlar un
> navegador real?

No busques una respuesta perfecta. El objetivo es tener algo con lo que
comparar al terminar el reto.

### Paso 2 · Conseguir la nueva capacidad

Pide al agente que investigue cómo integrar el MCP oficial de Playwright en la
herramienta que estés utilizando y que realice la integración.

No le des tú los comandos. Debe averiguar el procedimiento adecuado para su
propio entorno. Si necesita que reinicies la aplicación, hazlo, vuelve a abrir
el repositorio y continúa la conversación.

### Paso 3 · Demostrar que funciona

Utiliza esta web como primer campo de pruebas:

<https://a11y-agent-arena-challenges.vercel.app/training-1/>

Pide una prueba sencilla pero observable: que abra la web con el MCP y realice
alguna navegación o interacción real. Tú decides qué demostración aceptar.

Si solo te enseña configuración, código o una explicación, todavía no has
superado este paso.

### Paso 4 · Poner a prueba el agente

Cuando el navegador funcione, pide al agente que ejecute su skill de auditoría
sobre estas dos webs:

- <https://a11y-agent-arena-challenges.vercel.app/training-1/>
- <https://a11y-agent-arena-challenges.vercel.app/training-2/>

No le digas qué errores debe buscar. Observa qué decide explorar, qué acciones
realiza y qué evidencia aporta.

### Paso 5 · Mejorar la skill

Pregunta al agente:

> ¿Qué has podido comprobar con el navegador que antes no podías demostrar?

Después, pídele que actualice tu `SKILL.md` con lo aprendido. Debe mejorar el
método de futuras auditorías, no guardar las respuestas de estas dos webs.

### Has terminado el Reto 2 si…

- Has visto una ejecución real del MCP de Playwright.
- El agente ha navegado o interactuado, no solo leído una página.
- Puedes explicar una diferencia entre la auditoría anterior y la nueva.
- La skill ha mejorado y no contiene el informe de entrenamiento.

---

## Reto 3 · Comprueba otra forma de leer la web

### Qué tienes que conseguir

Ahora añadirás un lector virtual al agente. Este lector permite observar cómo
un simulador interpreta el contenido y las interacciones de una página.

Utilizarás este paquete:

```text
@weaaare/mcp-virtual-screen-reader-auditor
```

Importante: es un **simulador**. No sustituye a NVDA, JAWS, VoiceOver ni a una
prueba con una persona usuaria.

### Paso 1 · Haz una predicción

Vuelve a Cita Clara:

<https://a11y-agent-arena-challenges.vercel.app/training-2/>

Elige cualquier interacción que cambie algo en la página. Antes de utilizar el
lector virtual, escribe qué crees que se escuchará y en qué orden.

No importa si te equivocas. Necesitamos la predicción para poder comparar.

### Paso 2 · Integra el lector virtual

Pide al agente que investigue cómo integrar el paquete en tu herramienta y que
lo deje preparado para usarlo.

De nuevo, no aceptes únicamente una instalación declarada. Pide al agente que
inicie una sesión real del lector virtual sobre Cita Clara.

### Paso 3 · Repite la interacción

Pide al agente que reproduzca con el lector virtual la misma interacción sobre
la que hiciste la predicción.

Debe mostrarte el registro de lo que el simulador ha interpretado. Si devuelve
una explicación sin utilizar la herramienta, pídele la evidencia de la sesión.

### Paso 4 · Compara

Compara tu predicción con el registro obtenido:

- ¿Qué coincidió?
- ¿Qué no apareció?
- ¿Qué ocurrió en un orden diferente?
- ¿Qué conclusión no podrías generalizar a todos los lectores de pantalla?

### Paso 5 · Mejora de nuevo la skill

Pide al agente que actualice `SKILL.md` para utilizar el lector virtual cuando
aporte información útil y para explicar correctamente sus límites.

La skill debe conservar el método aprendido, no el resultado concreto de Cita
Clara.

### Has terminado el Reto 3 si…

- Has visto una sesión real del lector virtual.
- Has comparado un registro con una predicción escrita antes de la prueba.
- El agente diferencia simulación, lector real y validación humana.
- La skill ha mejorado sin guardar el informe de entrenamiento.

---

## Si te bloqueas

- Si el agente dice que ha instalado algo, pero no lo utiliza, pídele:
  «demuéstramelo ejecutando una prueba real y enséñame el resultado».
- Si necesita reiniciarse para detectar un MCP, reinicia la aplicación, vuelve
  a abrir el repositorio y recuérdale en qué paso estabais.
- Si aparecen muchos errores técnicos, pide que investigue primero uno solo y
  que te explique la causa con palabras sencillas.
- Puedes pedir ayuda en Discord compartiendo el mensaje de error, pero no
  compartas claves, tokens ni otros secretos.

## Entrega tu agente

Cuando hayas terminado ambos retos, pega este prompt:

```text
Usa $submit-a11y-agent para revisar y entregar mi agente auditor individual.
Mi identificador es <participante>. Devuélveme la URL de la pull request y no
la fusiones.
```

El agente revisará tu carpeta y abrirá una pull request. `main` está protegida,
por lo que la PR quedará esperando revisión.

## Comparte el resultado en Discord

Publica solamente:

```text
Participante:
Pull request:
Hallazgo más sólido:
Evidencia que aporta el agente:
Mayor mejora de mi agente:
Principal limitación que conserva:
```

La próxima clase revelaremos las barreras que estaban preparadas, revisaremos
los falsos positivos y elegiremos el agente auditor individual más sólido.

No gana quien escriba la lista más larga. Gana quien pueda demostrar mejor lo
que afirma.
