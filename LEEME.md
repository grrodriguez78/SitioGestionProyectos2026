# Sitio del curso · Gestión de Proyectos (UTPL) · Semanas 1 a 4

## Carpeta
```
index.html          página (no se edita durante el semestre)
css/estilo.css      diseño
js/app.js           próxima actividad, búsqueda, tareas, audio
datos/silabo.js     ÚNICO archivo que se edita: fechas, lecturas, tareas, audios
img/logo_utpl.jpg   logo
audio/              sus grabaciones convertidas a MP3
revision_silabo.md  comparación con el plan docente (paso 3)
pruebas.md          pruebas locales (paso 4)
```
Abra `index.html` con doble clic: funciona sin servidor y sin internet.

## Agregar sus grabaciones .wav

1. **Convierta cada WAV a MP3** (un WAV pesa unas 10 veces más; un minuto ≈ 10 MB en WAV y ≈ 0,5 MB en MP3 a 64 kbps).
   - Con Audacity: Archivo → Abrir → `Archivo > Exportar > Exportar como MP3`, calidad 64–96 kbps, mono.
   - Con ffmpeg: `ffmpeg -i semana1.wav -ac 1 -b:a 64k semana-1.mp3`
   - Todos de una vez (Windows PowerShell): `Get-ChildItem *.wav | % { ffmpeg -i $_.Name -ac 1 -b:a 64k ($_.BaseName + ".mp3") }`
   - Todos de una vez (macOS/Linux): `for f in *.wav; do ffmpeg -i "$f" -ac 1 -b:a 64k "${f%.wav}.mp3"; done`
2. **Nombres sin espacios ni tildes**: `semana-1.mp3`, `bienvenida.mp3`. GitHub Pages distingue mayúsculas.
3. **Copie los MP3** en la carpeta `audio/`.
4. **Regístrelos en `datos/silabo.js`** cambiando `audio: null` de la semana:
   ```js
   audio: {
     archivo: "audio/semana-1.mp3",
     titulo: "Mensaje del docente sobre la semana 1",
     transcripcion: "Buenos días. Esta semana iniciamos la Unidad 1..."
   },
   ```
   Para el audio de bienvenida, use `audioBienvenida` dentro de `curso`.
5. Abra `index.html` y compruebe que suena.

Notas: la **transcripción** es necesaria para estudiantes con discapacidad auditiva o sin audífonos (lección R4.5).
Si prefiere no convertir, el WAV también funciona (`archivo: "audio/semana-1.wav"`), pero carga lento en datos móviles;
GitHub rechaza archivos de más de 100 MB. El repositorio es público: no grabe datos personales de estudiantes.

## Publicar en GitHub Pages (paso 5)
1. Cree una cuenta en github.com y un repositorio **público**, por ejemplo `gestion-proyectos-utpl`.
2. «Add file → Upload files»: arrastre el **contenido** de esta carpeta (index.html debe quedar en la raíz). «Commit changes».
3. Settings → Pages → Source: «Deploy from a branch» → Branch `main`, carpeta `/ (root)` → Save.
4. Espere 1–2 minutos. La dirección será `https://<su-usuario>.github.io/gestion-proyectos-utpl/`.
5. Ábrala desde **otro dispositivo** (teléfono con datos móviles): revise logo, audios, enlaces y la lista de tareas. Haga una captura.

Para actualizar: edite `datos/silabo.js` en GitHub (ícono del lápiz) y guarde; Pages se republica solo.

## Enlazar desde el EVA (Moodle/Canvas)
Moodle: Añadir actividad o recurso → URL → pegue la dirección de GitHub Pages. Las entregas siguen en el EVA.
