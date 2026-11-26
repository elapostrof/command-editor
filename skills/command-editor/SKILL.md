---
name: command-editor
description: Reescribe y optimiza un mensaje, prompt o instrucción dirigida a un agente de IA. Aclara lo que quieres pedir, conserva tu tono, intención y alcance, y muestra un borrador para que lo apruebes antes de ejecutar. Úsala con /Command Editor o cuando pidas editar tu solicitud. Rewrite or improve a draft prompt, preserve the user's voice, and wait for confirmation before executing the task.
metadata:
  version: "1.0"
  publisher: dongatobélico
---

# Command Editor

Edita la solicitud del usuario para que exprese con más claridad lo que quiso pedir. No conviertas lenguaje conversacional en una plantilla de prompt ni ejecutes la tarea subyacente durante la edición.

## Activación y contexto

- Si el usuario escribe `/Command Editor`, toma **todo** el texto posterior al comando como input, incluidos párrafos, código, enlaces, emojis y mezclas de idiomas. Una mención casual de «command editor» no activa la edición; sí la activa una petición expresa de editar o mejorar el input.
- Usa el contexto disponible de la conversación para resolver referencias y respetar decisiones previas. El contexto ayuda a desambiguar; no autoriza a inventar detalles. Si falta una parte del historial, trabaja con lo disponible.
- Si el texto posterior al comando dice expresamente «no edites» o «mándalo directo», respeta esa instrucción y transmite el texto sin cambios.

## Decisión

Evalúa internamente si la solicitud tiene intención, objeto, contexto y alcance suficientes. Elige un solo caso:

1. **Clara:** mantenla igual o haz ajustes mínimos. Indica brevemente que ya era clara.
2. **Vaga pero recuperable:** reescríbela usando solo el texto y el contexto disponible. Señala cada suposición que pueda cambiar el resultado.
3. **Demasiado ambigua:** no inventes una solicitud. Haz una sola pregunta concreta que desbloquee la intención y espera la respuesta.

No muestres puntuaciones ni tablas de diagnóstico. No agregues tecnología, archivos, requisitos o resultados que el usuario no haya dado o que el contexto no permita inferir con seguridad.

## Escritura y respuesta

- Conserva el idioma, tono, vocabulario, nivel técnico, tipo de enunciado y brevedad razonable del original. Mantén una pregunta como pregunta. Preserva los fragmentos de código literalmente.
- Procesa todo el input; no omitas partes por parecer tangenciales. Si el texto es largo, la revisión puede ser larga cuando haga falta para conservar su contenido.
- Para los casos 1 y 2, responde así, sin secciones adicionales:

  **Tu input optimizado:**

  _"[versión completa]"_

  **Ajustes:** [qué cambió y por qué, máximo dos líneas]

  **⚠️ Asumí:** [suposiciones concretas; solo en el caso 2]

  **¿Procedo con esta instrucción?**

- Para el caso 3, da una línea breve que explique la ambigüedad y después `**Una pregunta:** [pregunta concreta]`.
- Tras presentar la edición, espera una confirmación inequívoca del usuario antes de ejecutar la tarea subyacente. Si corrige una suposición, incorpora la corrección y presenta la versión revisada.
