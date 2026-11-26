# Command Editor

**Escribe como te salga. Revisa cómo quedó. Da luz verde cuando esté listo.**

Command Editor es una skill que ordena lo que le quieres pedir a un agente de IA sin quitarle tu voz. Te devuelve la solicitud revisada y espera tu confirmación antes de hacer la tarea.

## De «acomódame este desmadre» a una instrucción clara

**Tú escribes**

> /Command Editor Checa el PDF que subí, dime qué fechas tengo que apuntar y ponme en qué página salen. Si alguna no se lee, dime cuál.

**Command Editor te devuelve**

> **Tu input optimizado**
>
> Checa el PDF que subí y dime qué fechas tengo que apuntar. Pon la página junto a cada fecha. Si alguna fecha no se lee, dime en qué página aparece.
>
> **Ajustes** · Aclaré que cada fecha debe llevar su página.
>
> ¿Procedo con esta instrucción?

Si te late, responde **«Sí, procede»**. Si algo quedó distinto de lo que querías, corrígelo antes de dar luz verde.

## Instálala en Codex

```bash
npx skills add elapostrof/command-editor --skill command-editor -a codex -g
```

En Windows, si PowerShell bloquea `npx`, usa `npx.cmd` al inicio del mismo comando.

## Cuándo usarla

- **Ya sabes qué quieres, pero lo escribiste todo revuelto.** La skill organiza el pedido manteniendo el idioma, el tono y el alcance.
- **La petición depende de algo que ya platicaste.** Aprovecha el contexto del mismo chat y señala cualquier suposición que cambie el resultado.
- **Falta un dato que cambia por completo la tarea.** Te hace una pregunta concreta antes de redactar la versión final.

Escribe `/Command Editor` seguido de tu borrador, o selecciona `command-editor` con el selector de skills de tu agente.

Creada por [dongatobélico](https://github.com/elapostrof).
