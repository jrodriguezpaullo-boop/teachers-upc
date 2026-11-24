# Teachers UPC (web)

Plataforma de calificación de docentes: el **diseño visual** (carpetas `templates/` y `static/`)
conectado a la **lógica del programa** (`service/`, `repository/`, `modelo/`, `utils/`).

## Primera vez (VS Code)

1. Instala Python y la extensión **Python** de VS Code.
2. **File > Open Folder** y elige esta carpeta.
3. En la terminal de VS Code:

   ```powershell
   python -m venv .venv
   .venv\Scripts\activate
   pip install -r requirements.txt
   ```
4. **Ctrl+Shift+P > Python: Select Interpreter** y elige el de `.venv`.

## Clave de Gemini (para el chat de IA)

Copia `.env.example` como `.env` y reemplaza el texto por tu propia `GEMINI_API_KEY`
(se obtiene gratis en https://aistudio.google.com/apikey). Sin ella, la página funciona
igual, solo que el chat de IA avisará que falta la clave.

## Ejecutar

- Presiona **F5** y elige **"Teachers UPC - Web (app.py)"**, o en la terminal: `python app.py`
- Abre **http://127.0.0.1:5000** en el navegador.

## Qué hace la página

- **Registrarse / Iniciar sesión** (usa `estudiantes.csv`).
- **Buscador** por nombre de docente o por curso, y botón **Ver todos**.
- **Ver perfil**: puntaje, opiniones, análisis de sentimiento y formulario para **publicar una opinión**.
- **Inteligencia Artificial**: chat con el asistente Gemini (`GEMINI_API_KEY` en `.env`).

## Fotos de los docentes

Copia las fotos a `static/imagenes/` con el nombre que aparece en la columna `foto` de `docentes.csv`
(`ana.jpg`, `luis.jpg`, ...). Si una foto no existe, se muestra un avatar con las iniciales.

## Versión de consola

`main.py` sigue funcionando igual que antes (opción "Plataforma Docentes - consola" en F5).

## Notas

- La primera vez que se analiza una opinión, `transformers` descarga el modelo
  `pysentimiento/robertuito-sentiment-analysis` (necesita internet). Si no carga, la página
  funciona igual pero sin análisis de sentimiento.
- Los datos viven en `docentes.csv`, `estudiantes.csv` y `opiniones.csv`.
