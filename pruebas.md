# Pruebas locales (paso 4)

Fecha: 5 de octubre de 2026 · Navegador: Chromium (automatizado) · Para simular otra fecha: `index.html?hoy=2026-10-20T10:00`

| Prueba | Cómo | Resultado |
|---|---|---|
| Teléfono 375 px | Anchura de documento vs. ventana | 375 = 375, sin desplazamiento lateral ✔ |
| Texto al 200 % | `html{font-size:200%}` a 375 px | 375 = 375, sin solapamientos ✔ |
| Teclado | Tab desde el inicio | Saltar al contenido → menú → próxima actividad → Buscar una lectura → Contactar → cronograma ✔ · foco visible en dorado ✔ |
| Próxima actividad | `?hoy=2026-10-05T10:30` | «Lunes, 5 de octubre de 2026, 11:00 · Clase…» ✔ |
| Fin de sesiones semana 4 | `?hoy=2026-10-27T13:30` | «Ya no hay sesiones esta semana» ✔ |
| Después del periodo | `?hoy=2026-11-10T10:00` | «Las semanas 1 a 4 ya terminaron. Consulte el EVA» ✔ |
| Buscar lectura | «prince» / «semana 2» | 1 y 4 resultados ✔ |
| Lista de tareas | Marcar y recargar | La marca persiste; «Borrar mis marcas» reinicia ✔ |
| Audio | MP3 de prueba en `audio/` | Reproductor carga (3 s) ✔ |
| Sin conexión | Fuente de Google bloqueada | Usa fuente del sistema; nada se rompe ✔ |
| Enlaces externos | — | ☐ Pendiente: comprobar desde su computador (el entorno de prueba no tiene acceso a esos dominios). Lista: standishgroup.com, youtu.be/6SjDZTmQrUE y los 5 REA |
| Prueba de 30 s con un colega | Buscar la lectura de la semana 2 | ☐ Pendiente |
