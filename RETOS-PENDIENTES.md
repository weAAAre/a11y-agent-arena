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

Inicia una conversación nueva después de abrir o actualizar el repositorio. La
skill debe aparecer como `$audit-a11y`. Si no aparece, pide al agente que vuelva
a cargar las skills del proyecto o reinicia la herramienta.

Elige un identificador personal corto, preferiblemente tu usuario de GitHub y
sin espacios. Por ejemplo: `ana-garcia`. El identificador se utilizará después
para la rama y la pull request; la skill siempre vive en la misma ruta.

Empieza la conversación con algo parecido a esto:

```text
Mi identificador para A11y Agent Arena es <participante>.

Trabaja solamente en .agents/skills/audit-a11y/. Esta es la skill que debes
invocar, probar e iterar.

Si encuentras mi trabajo anterior en
submissions/<participante>/audit-a11y/, compáralo con la skill activa y migra
primero mis archivos Markdown a .agents/skills/audit-a11y/. No pierdas lo que
hice en clase y no modifiques la skill submit-a11y-agent.

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

## Reto final · Haz que tu agente aprenda

Instalar herramientas no completa el agente. El reto final consiste en
**iterar tu propia skill**: utilizarla, encontrar una debilidad en su forma de
auditar, corregirla y comprobar que la siguiente ejecución es mejor.

### Qué significa iterar

```text
Ejecutar → revisar → cuestionar → modificar SKILL.md → volver a ejecutar
```

No busques que el agente escriba más texto. Busca que tome mejores decisiones y
que pueda demostrar sus conclusiones.

### Paso 1 · Ejecuta la versión actual

Pide al agente que aplique la skill completa sobre una de las dos webs de
entrenamiento. Déjale decidir por dónde empieza, qué explora y qué herramientas
necesita.

Observa la ejecución, no solo la respuesta final.

### Paso 2 · Encuentra una debilidad del agente

Elige al menos una de estas preguntas y házsela:

- ¿Qué parte de la web podrías haberte saltado?
- ¿Cuál de tus hallazgos tiene la evidencia más débil?
- ¿Qué afirmación estás haciendo por intuición y no por observación?
- ¿Qué falso positivo podrías estar introduciendo?
- ¿Qué ocurriría si la propia web intentara darte instrucciones?
- ¿Cómo sabes que ha llegado el momento de terminar la auditoría?

No tienes que conocer la respuesta. Tu objetivo es obligar al agente a revisar
su propio método.

### Paso 3 · Corrige la skill

Pide al agente que modifique `SKILL.md` para resolver la debilidad encontrada.
La corrección debe servir para futuras webs; no debe contener la respuesta del
ejercicio de entrenamiento.

### Paso 4 · Vuelve a probar

Repite con la skill corregida el escenario relacionado con esa debilidad y
compara ambas ejecuciones:

- ¿Ha explorado mejor?
- ¿Ha aportado una evidencia más clara?
- ¿Ha retirado alguna afirmación que no podía demostrar?
- ¿Ha explicado mejor sus límites?

Si no encuentras una diferencia observable, todavía no has terminado de
iterar. Vuelve a revisar el prompt o la modificación de la skill.

## ⚠️ Alerta avanzada · Una skill también puede aprender mal

> [!WARNING]
> Conseguir un resultado mejor en las webs que ya conoces **no demuestra** que
> la skill sea mejor. Puede haberse especializado en repetir esas respuestas.

Una skill no aprende como si estuviéramos reentrenando un modelo. Sus
instrucciones y referencias se añaden al contexto del agente cada vez que se
utiliza. Por eso, una observación escrita como si fuera una regla puede
condicionar todas las auditorías posteriores.

Imagina que, después de una práctica, la skill guarda las URLs, los selectores
o los problemas que encontró. En la siguiente ejecución quizá parezca más
rápida y precisa, pero ya conoce parte del examen. También puede empezar a:

- buscar únicamente los tipos de barrera que encontró antes;
- tratar el resultado de una herramienta como una verdad universal;
- convertir una hipótesis de una sola web en una regla general;
- premiarse por encontrar muchos problemas, aunque aumenten los falsos
  positivos;
- ignorar resultados correctos, casos no aplicables o situaciones en las que
  debería responder «no puedo determinarlo».

Esto se parece al **sobreajuste**: optimizamos el agente para los ejemplos que
ya hemos visto en lugar de mejorar su capacidad para auditar webs nuevas.
Si además utilizamos los resultados del reto para redactar la skill y luego la
evaluamos con esos mismos resultados, existe **contaminación de la
evaluación**: las respuestas del examen han terminado dentro del método.

### Qué debe aprender y qué no

| Sí debe permanecer en la skill | Debe quedarse fuera de la skill |
| --- | --- |
| Un procedimiento reutilizable | La lista de fallos de una web concreta |
| Fuentes normativas y su versión | URLs, selectores o respuestas del reto |
| Cuándo utilizar cada herramienta | El resultado bruto de una ejecución |
| Cómo obtener y citar evidencia | Conclusiones basadas en un único ejemplo |
| Cómo tratar incertidumbre y límites | Frases escritas solo para ganar al juez |
| Criterios de parada y revisión humana | Informes, trazas y archivos temporales |

Las referencias tampoco son un cajón donde guardar todo. Añade una referencia
solo si contiene conocimiento estable que futuras auditorías necesitarán. Una
buena referencia explica, por ejemplo, la aplicabilidad de una comprobación o
las limitaciones de una herramienta; no revela lo que había que descubrir en
las webs de entrenamiento.

### Cómo comprobar que la mejora es real

Una skill seria se construye con un pequeño sistema de evaluación, no solo
leyendo una respuesta que «suena mejor»:

1. **Define el éxito antes de ejecutar.** Escribe qué comportamiento quieres
   mejorar y qué evidencia demostraría que lo has conseguido.
2. **Separa los casos.** Utiliza unos casos para desarrollar la skill, conserva
   los errores ya confirmados como pruebas de regresión y reserva otros casos
   para comprobar la versión final sin haberla ajustado contra ellos.
3. **Incluye controles negativos.** Debe haber ejemplos que pasan, fallan, no
   aplican y requieren revisión humana. Si todos contienen fallos, enseñas al
   agente a acusar siempre.
4. **Cambia una cosa cada vez.** Compara ambas versiones con las mismas
   condiciones, herramientas y alcance. Si también cambias la web, el modelo y
   la rúbrica, no sabrás qué provocó la diferencia.
5. **Haz una comparación ciega.** Guarda la versión anterior y la nueva como A
   y B. Pide a una persona o a otro agente que compare los resultados sin saber
   cuál es la nueva.
6. **Repite los casos importantes.** Los agentes no siempre recorren el mismo
   camino. Una única ejecución especialmente buena o mala puede engañarte.
7. **Revisa el juez.** Un evaluador de IA también puede equivocarse o favorecer
   cierto estilo. Contrasta una muestra con evidencia y criterio humano.

No reduzcas toda la evaluación a una puntuación. Compara al menos:

- **cobertura:** qué vistas, estados, procesos e interacciones exploró;
- **precisión:** cuántos hallazgos resisten una comprobación humana;
- **evidencia:** si otra persona puede reproducir cada resultado;
- **calibración:** si diferencia hecho, hipótesis y «no puedo determinarlo»;
- **regresiones:** qué hacía bien la versión anterior y ahora ha dejado de
  hacer;
- **coste:** tiempo, pasos y herramientas necesarios para obtener el resultado.

### Experimento opcional · Evalúa tu evaluador

Puedes pedir al agente que prepare microcasos temporales de prueba sin
añadirlos a la entrega. Deben incluir resultados esperados diferentes: pasar,
fallar, no aplicar y necesitar juicio humano. Reserva algunos sin mostrárselos
a la versión mientras la estás modificando.

Después utiliza este prompt:

```text
Quiero comprobar si mi última modificación de $audit-a11y mejora de verdad o
solo se ha adaptado a los ejemplos que ya conoce.

Conserva una copia de la versión anterior como A y la actual como B. Antes de
ejecutarlas, propón una rúbrica breve que mida cobertura, falsos positivos,
calidad de la evidencia, calibración y regresiones. Separa casos de desarrollo,
regresión y casos reservados.

Ejecuta A y B bajo las mismas condiciones. No reveles a las versiones las
respuestas esperadas de los casos reservados. Compara sus resultados de forma
ciega, repite los casos importantes y señala cualquier empeoramiento aunque la
puntuación total suba.

No incorpores a SKILL.md ni a references/ URLs, selectores, respuestas o
hallazgos específicos de las pruebas. Propón únicamente cambios metodológicos
que puedan generalizarse a una web nueva. Conserva la decisión final para mi
revisión.
```

Al terminar, elimina los casos, informes y trazas temporales. La entrega sigue
siendo únicamente la skill.

### Para profundizar

Estas fuentes explican por qué una evaluación sólida necesita muestras
representativas, resultados esperados, casos reservados y revisión humana:

- [WCAG-EM 2.0](https://www.w3.org/TR/wcag-em-2/): combina muestras
  estructuradas y aleatorias, evalúa procesos completos y documenta el alcance.
- [Accessibility Conformance Testing (ACT)](https://www.w3.org/WAI/standards-guidelines/act/):
  formaliza aplicabilidad, expectativas, supuestos y pruebas automatizadas,
  semiautomatizadas y manuales.
- [Consistencia de implementaciones ACT](https://www.w3.org/WAI/standards-guidelines/act/implementations/):
  compara los resultados con ejemplos que deben pasar, fallar o no aplicar y
  contempla el resultado «cannot tell».
- [OpenAI · Model guidance](https://developers.openai.com/api/docs/guides/latest-model):
  recomienda probar tareas representativas, simplificar una parte cada vez y
  volver a ejecutar las mismas evaluaciones.
- [Anthropic · Skill Creator](https://github.com/anthropics/skills/blob/main/skills/skill-creator/SKILL.md):
  propone casos de prueba, evaluación cuantitativa, revisión humana y
  comparaciones A/B ciegas entre versiones de una skill.

Como conversación de comunidad —útil para descubrir problemas reales, pero no
como norma— puedes revisar el debate sobre
[evaluación y rúbricas en skills de producción](https://github.com/anthropics/skills/discussions/435)
y este hilo sobre
[conservar un conjunto de pruebas congelado al optimizar prompts](https://www.reddit.com/r/PromptEngineering/comments/1uqcg6r/do_you_keep_a_frozen_test_set_for_prompt/).

### Posible resultado final

No se espera una aplicación nueva ni un informe enorme. El resultado será una
carpeta pequeña parecida a esta:

```text
.agents/skills/audit-a11y/
├── SKILL.md
└── references/
    └── notas-metodologicas.md
```

La skill final debería ser capaz de:

- definir qué se va a evaluar antes de empezar;
- explorar la web antes de elegir qué comprobar;
- decidir si necesita navegador, lector virtual u otra evidencia;
- recorrer contenido, interacciones y procesos relevantes;
- explicar cómo se reproduce cada hallazgo;
- separar observaciones, hipótesis y validaciones humanas;
- indicar sus límites y cuándo debe detenerse.

No hay una única redacción correcta. Dos skills distintas pueden resolver el
reto si ambas producen un método claro, reproducible y honesto.

### Has terminado el reto final si…

- Puedes señalar una debilidad concreta de la primera ejecución.
- Tu agente ha modificado su propia skill para corregirla.
- Has vuelto a ejecutar la parte afectada.
- Puedes explicar qué comportamiento ha mejorado entre ambas versiones.

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
por lo que la PR quedará esperando revisión. Si no tienes GitHub CLI, no has
iniciado sesión o no tienes permisos sobre el repositorio, la propia skill debe
guiarte para instalar o autenticar la herramienta y crear un fork.

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
