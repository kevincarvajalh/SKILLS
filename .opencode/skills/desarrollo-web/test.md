# Skill: Testing web con Playwright MCP

## Objetivo
Probar la aplicación web de forma metódica usando el MCP de Playwright: navegar, interactuar como usuario real, detectar bugs y generar un reporte con evidencias.

## Pasos

1. **Preguntar la URL** de la app a probar (ej: `localhost:3000` o URL de deploy)
2. **Navegar** a la URL con las herramientas del MCP de Playwright
3. **Explorar la página:** capturar snapshot/estructura para conocer los elementos disponibles (botones, formularios, links)
4. **Probar interacciones como usuario real:**
   - Rellenar formularios (inputs, selects, checkboxes)
   - Hacer clic en botones y links
   - Verificar que las acciones produzcan el resultado esperado
5. **Detectar bugs:**
   - Errores de consola del navegador
   - Elementos que no responden al clic
   - Textos/estados que no aparecen tras una acción
   - Validaciones que no funcionan
6. **Tomar screenshots** como evidencia de cada prueba (especialmente de bugs)
7. **Generar reporte final:** tabla de pruebas pasadas ✅ / fallidas ❌ con descripción del bug y screenshot asociado

## Reglas
- Usar siempre las herramientas del MCP de Playwright para interactuar con el navegador
- Cada bug detectado debe tener screenshot como evidencia
- El reporte final debe ser claro y accionable para el equipo de desarrollo
