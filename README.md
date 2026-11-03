# Roma Histórica — Audioguía Vaticano–Trastevere

MVP de PWA estática sin dependencias. Incluye 10 paradas (sin visita al interior de Castel Sant'Angelo), relatos iniciales, voz del navegador con pausa, imágenes consultadas a Wikimedia Commons con atribución, y enlaces a Google Maps para caminar.

## Abrir en VS Code / Codex
1. Descomprimir el ZIP y abrir la carpeta `roma-historica` en VS Code.
2. En terminal ejecutar `python -m http.server 8000` (o `npx serve .`).
3. Abrir `http://localhost:8000` en el ordenador. Para probar el móvil usar un despliegue HTTPS, por ejemplo Vercel.
4. Abrir Codex en VS Code para mejorar la aplicación. El contenido editable está en `data.js`.

## Avisos importantes
- Los guiones son una **primera versión** y todavía no alcanzan los 5–6 minutos por parada. Deben ampliarse y revisarse antes de grabar una audioguía definitiva.
- La voz integrada usa `speechSynthesis`: la calidad, disponibilidad offline y comportamiento con pantalla bloqueada dependen del móvil. NO son archivos MP3. Para versión final, generar MP3 por parada, guardarlos localmente y adaptar el reproductor a `<audio>`.
- La aplicación cachea sus ficheros esenciales; NO descarga automáticamente imágenes ni mapas para offline. Requiere conexión para Wikimedia Commons y posiblemente para la voz del sistema.
- Wikimedia Commons devuelve fotos por búsqueda; revisar manualmente que representen el monumento exacto y sus licencias, antes de publicación definitiva.
- Los enlaces a Google Maps abren un servicio externo; la navegación offline depende de Google Maps y de sus descargas previas.
- La ubicación del alojamiento no se envía a esta aplicación; el recorrido comienza en el puente y cada parada abre Google Maps mediante coordenadas aproximadas.

## Próximo prompt para Codex
«Convertí esta PWA de narración mediante speechSynthesis a un reproductor MP3 con archivos locales en `/audio/{slug}.mp3`, conservando texto y botones, agregando progreso, retroceder 15 segundos, velocidad, caché offline de todos los MP3 y una pantalla para confirmar que todos se han descargado. No modifiques el contenido histórico sin pedírmelo.»
