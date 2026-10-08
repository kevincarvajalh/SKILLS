# Skill: Ingeniería de prompts

## Objetivo
Convertir una idea vaga del usuario en un prompt estructurado y listo para copiar, mediante una entrevista corta. Esta skill construye el prompt; no ejecuta la tarea que el prompt describe.

## Flujo (siempre en este orden)

1. **Recibir la idea:** el usuario describe en 1–2 frases lo que quiere. Extraer los datos que ya trae; no volver a preguntarlos.
2. **Diagnóstico:** revisar cuáles de los 6 campos obligatorios faltan (tabla siguiente).
3. **Entrevista en UNA sola ronda:** preguntar solo los campos faltantes, máx. 5 preguntas, numeradas, cada una con opciones sugeridas + "otro". Si no falta ninguno, pasar al paso 4.
4. **Construir el prompt** con la plantilla exacta.
5. **Entregar:** el prompt en un bloque de código + máx. 3 líneas de "Supuestos" (lo que se asumió por no estar dicho).
6. **Iterar:** preguntar una sola vez si se ajusta (tono, longitud, formato). Repetir los pasos 4–5 hasta que el usuario confirme.

## Campos obligatorios y pregunta exacta si faltan

| Campo | Pregunta |
|---|---|
| Rol | ¿Qué perfil debe asumir la IA? (ej: analista de datos senior, copywriter financiero, abogado) |
| Contexto | ¿Cuál es la situación, para quién es y qué material o datos de entrada hay? |
| Tarea | ¿Qué debe hacer exactamente? (un solo objetivo principal) |
| Restricciones | ¿Qué límites aplican? (longitud, tono, idioma, qué NO debe hacer o incluir) |
| Formato de salida | ¿En qué formato lo quieres? (lista, tabla, JSON, markdown, texto corrido, nº de palabras) |
| Criterio de éxito | ¿Cómo sabrás que la respuesta es buena? |

## Plantilla del prompt final

Usar exactamente estos nombres de sección:

````
# Rol
Eres [perfil] con experiencia en [área].

# Contexto
[situación, audiencia, datos de entrada]

# Tarea
[verbo en imperativo + objetivo único]

# Restricciones
- [límite 1]
- [límite 2]
- Si falta información para responder, pregúntame antes de asumir. No inventes datos.

# Formato de salida
[estructura exacta; incluir ejemplo corto si aplica]

# Criterios de calidad
[cómo debe verificar su respuesta antes de entregarla]
````

- Agregar `# Ejemplos` (máx. 2, entrada → salida) solo si el usuario los aporta o el formato es complejo.
- Omitir una sección solo si el usuario dice explícitamente que no aplica.

## Reglas
- Construir el prompt; nunca ejecutar la tarea del prompt.
- Máx. 5 preguntas, una sola ronda; no preguntar lo que ya está dicho.
- Tarea = un solo objetivo. Si hay varios, proponer dividirlos en prompts separados.
- Usar verbos concretos (analiza, redacta, compara, clasifica). Prohibido "ayúdame con" o "algo sobre".
- Expresar los requisitos en números cuando el usuario lo permita (palabras, ítems, columnas).
- Mantener el idioma del usuario. El prompt final va siempre en bloque de código.
- No incluir datos sensibles (credenciales, datos personales de clientes). Si el usuario los pega, avisar y reemplazarlos por marcadores como `[CLIENTE]`.
- No agregar contexto de Capitaria que el usuario no haya dado.

## Checklist antes de entregar
- [ ] Los 6 campos están cubiertos
- [ ] Una sola tarea principal
- [ ] Formato de salida inequívoco
- [ ] Incluye la instrucción de preguntar si falta información
- [ ] Sin datos sensibles
- [ ] Supuestos listados (≤ 3 líneas)

## Ejemplo

**Entrada del usuario:** "necesito resumir un reporte"

**Ronda de preguntas (solo lo que falta):**
1. ¿Qué tipo de reporte es y quién lo va a leer? (a) reporte de ventas, gerencia · (b) reporte técnico, equipo · (c) otro
2. ¿Qué formato quieres? (a) 5 viñetas · (b) 1 párrafo de 100 palabras · (c) otro
3. ¿Qué debe destacar el resumen? (a) cifras clave · (b) riesgos · (c) decisiones pendientes

**Prompt entregado** (con respuestas a, a, a):

```
# Rol
Eres un analista de negocio senior con experiencia en reportes comerciales.

# Contexto
Resumirás un reporte de ventas mensual que leerá la gerencia. Te lo pego a continuación del prompt.

# Tarea
Resume el reporte destacando las cifras clave.

# Restricciones
- Máximo 5 viñetas de 25 palabras cada una.
- Tono ejecutivo, en español.
- Si falta información para responder, pregúntame antes de asumir. No inventes datos.

# Formato de salida
Lista de 5 viñetas; cada una empieza con la cifra en negrita.

# Criterios de calidad
Antes de responder, verifica que cada cifra aparezca en el reporte original y que no superes 5 viñetas.
```

**Supuestos:** el reporte se pega después del prompt; el idioma es español.
