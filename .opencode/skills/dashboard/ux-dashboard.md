# Skill: UX de dashboard

## Objetivo
Diseñar cualquier dashboard para decidir rápido: la conclusión se ve en 5 segundos y un no-experto la entiende. Primero se entrega una propuesta de diseño; el código viene después.

## Flujo
1. **Entender** (preguntar solo lo que falte, máx. 3): quién lo usa, qué decisión toma y qué datos hay.
2. **Proponer el diseño ANTES de escribir código**, con:
   - Titular de conclusión: una frase con lo que dicen los datos.
   - Boceto de disposición en texto, indicando qué va en cada zona.
   - Por cada elemento: pregunta que responde · visual recomendado y por qué · dato que usa.
   - Dónde va el acento de color y qué gradiente aplica.
3. **Esperar** aprobación o ajustes.
4. **Construir** en un único HTML (sin framework) siguiendo `diseno-dashboard` (paleta, fuente, tokens).
5. **Antes de entregar:** ¿puedo quitar algo sin perder la decisión? Si sí, quítalo.

## Jerarquía
- Arriba y más grande: el dato que responde la pregunta. Denominadores y contexto, pequeños.
- Toda cifra clave con referencia: meta, periodo anterior o estado (bien / mal / alerta).
- Orden de lectura: conclusión → KPIs → tendencia o comparación → detalle.
- Un dato, un lugar. Pocos elementos (guía: ~5 KPIs, ~4 gráficos); el resto en detalle bajo demanda.

## Qué visual usar (por la pregunta)
- ¿Cuánto hay? → KPI grande con variación.
- ¿Cómo evoluciona? → línea.
- ¿Quién gana o pierde? → barras horizontales ordenadas.
- ¿Qué parte del total? → barra apilada al 100 % (pie solo con ≤ 3 partes).
- ¿Cómo se distribuye? → histograma.
- ¿Cuál exacto? → tabla ordenada.
- Pocos datos (≲ 8 puntos o muestras pequeñas) → número o lista con el n, no gráfico. Sin barras vacías ni tarjetas a medio llenar.
- Evitar: 3D, doble eje, gauges sin meta.

## Color y claridad
- El acento (verde) marca una sola cosa: lo que importa. El resto, neutro.
- Gradiente solo en elementos de énfasis (barra, botón), nunca de relleno.
- Lenguaje de negocio; cada cifra con unidad y periodo.
- Sin probabilidades, intervalos ni porcentajes extra si nadie los pidió.
- "Cómo se mide" en un ⓘ o plegable, no en un párrafo visible.
- Contemplar estados: sin datos, cargando, error.
