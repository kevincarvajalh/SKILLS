# Skill: Diseño de dashboard interno Capitaria

## Objetivo
Construir interfaces de dashboard interno con la identidad visual Capitaria 2026. Usar siempre los valores exactos de esta skill (colores, fuentes, tamaños). No inventar colores, fuentes ni gradientes.

## Colores

Definir como variables CSS y usar solo estas:

```css
:root {
  --verde: #43B649;        /* acento: CTA, KPI clave, estado activo */
  --verde-2: #34A773;      /* solo en gradiente y hover */
  --negro: #0A0A0A;        /* fondo principal */
  --carbon: #222223;       /* cards y superficies sobre negro */
  --gris-claro: #F1F1F1;   /* fondo en modo claro */
  --blanco: #FFFFFF;       /* texto sobre fondo oscuro */
  --gris-medio: #888888;   /* texto secundario, metadata */
  --texto-cuerpo-dark: #CCCCCC;
  --texto-cuerpo-light: #444444;
  --texto-light: #111111;  /* texto principal sobre gris claro */
}
```

- **Modo por defecto: oscuro** (fondo `--negro`, cards `--carbon`, texto `--blanco`). Variante clara: fondo `--gris-claro`, texto `--texto-light`.
- **Proporción por vista:** 60% negro · 20% blanco/gris claro · 12% grises · 8% verde.

### Gradientes permitidos (máx. 1 por vista)
| Nombre | Valor | Uso |
|---|---|---|
| Acento Verde | `linear-gradient(90deg, #43B649, #34A773)` | Botones, barras de acento, separadores |
| Hero Premium | `linear-gradient(135deg, #0A0A0A, #1A2E1A)` | Solo header o portada |
| Overlay Foto Dark | `linear-gradient(180deg, rgba(0,0,0,0), rgba(0,0,0,0.85))` | Texto sobre imagen |

## Tipografía

- **Fuente:** `"DIN Next LT Pro", Arial, sans-serif` (Arial solo como fallback; es válida para uso interno).
- **Escala permitida (px):** 48 · 36 · 28 · 22 · 18 · 15 · 13 · 11

| Nivel | Peso | Tamaño | Tracking | Color | Uso en dashboard |
|---|---|---|---|---|---|
| H1 | 900 Black | 32–48 | -0.02em | `--blanco` / `--negro` | Cifras KPI grandes, título de página |
| H2 | 700 Bold | 20–28 | -0.01em | `--blanco` / `--negro` | Título de sección, cifras KPI secundarias |
| H3 | 400–700 | 14–18 | 0 | `--blanco` / `--texto-light` | Título de card, subtítulos |
| P | 400 | 13–16 | 0 | `--texto-cuerpo-dark` / `--texto-cuerpo-light` | Texto de tablas, descripciones |
| Small | 300 Light | 11–13 | +0.02em | `rgba(255,255,255,0.4)` / `rgba(0,0,0,0.4)` | Metadata, fecha de actualización, fuente de datos |
| Tag | 700 | 9–11 | +0.10em | `--verde` | Categorías, tabs, etiquetas (MAYÚSCULAS) |
| CTA | 700 | 11–14 | +0.08em | `--verde` | Botones, links de acción ("Ver más →") |

### Límites por bloque (card / sección)
- Máx. 2 fuentes (DIN Next + Arial de fallback).
- Máx. 3 tamaños tipográficos distintos.
- Máx. 2 colores de texto (blanco o negro + verde de acento).
- Verde solo en 1–2 palabras de un título, en Tag y en CTA. Nunca en párrafos ni texto corrido.

## Composición
- Margen mínimo del contenedor: 20 px. Separación mínima entre elementos: 16 px.
- Barra de acento verde sobre el título de sección: 2 px de alto × 24–32 px de ancho (`--verde` o gradiente Acento).
- Cards: fondo `--carbon` sobre `--negro`, sin sombras ni glow.
- Una idea por card. Usar el espacio negativo, no rellenar por defecto.
- Jerarquía de lectura: logo → título → subtítulo → datos → CTA.
- Estados (activo, alerta, etc.): resolver con verde + grises. No inventar rojo/ámbar; si se necesitan, pedir aprobación a dirección creativa.

## Logo
- Versión principal (blanco + isotipo verde) sobre fondos oscuros; versión positiva (negro + isotipo verde) sobre fondos claros.
- Ubicación: top-left del header o sidebar.
- Ancho mínimo: 45 px. Zona segura alrededor = altura de la "X" del isotipo, sin elementos dentro.
- Sidebar colapsado o favicon (menos de 32 px): solo isotipo (flecha) en `--verde`.
- Incluir el tagline "TRADERS ONLY" salvo que el logo sea menor a 45 px de ancho.
- Prohibido: distorsionar, cambiar colores, rotar, cambiar la tipografía, agregar sombra, glow, outline o degradado, reordenar elementos.

## Reglas
- Verde como acento (máx. ~8% del área); nunca fondo 100% verde.
- Sin efectos neon, brillos, glows ni estética crypto-hype.
- Sin gradientes múltiples en una misma vista.
- Sin colores fuera de la paleta.
- Sin animaciones decorativas; solo las que comuniquen algo (carga, cambio de estado).
- Texto sobre imagen siempre con overlay oscuro (mínimo 60%).

## Checklist antes de entregar
- [ ] Solo colores de la paleta, definidos como variables CSS
- [ ] Fuente DIN Next LT Pro con fallback Arial
- [ ] Tamaños dentro de la escala (48·36·28·22·18·15·13·11)
- [ ] Máx. 3 tamaños y 2 colores de texto por bloque
- [ ] Verde solo como acento (título, Tag, CTA, barra) y ≤ 8% del área
- [ ] Máx. 1 gradiente por vista
- [ ] Logo con zona segura, tagline y versión correcta según fondo
- [ ] Márgenes ≥ 20 px y separación ≥ 16 px

## Ejemplo de referencia
`ejemplo-dashboard.html` (misma carpeta) es una implementación completa con datos ficticios en modo oscuro y claro (botón para alternar). Usa Barlow solo como sustituto visual mientras no esté cargada DIN Next LT Pro; en producción la fuente es DIN Next con fallback Arial.

## Qué mostrar
Antes de aplicar el estilo, definir qué mostrar con `ux-dashboard.md`.
