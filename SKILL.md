---
name: CV LaTeX Tailor
description: Adapta y compila currículums en formato LaTeX y PDF a partir de un perfil maestro y una oferta de empleo, identificando brechas técnicas y consultando detalles omitidos para maximizar la afinidad.
---

## Objetivo

Generar un currículum vitae adaptado a una oferta laboral específica a partir del perfil maestro en `references/perfil.md` y la plantilla base en `templates/plantilla.tex`, compilando opcionalmente el resultado a `.pdf`.

---

## Flujo de trabajo

### 1. Validación de la oferta laboral
1. Comprueba si el usuario ha suministrado la descripción, requisitos o enlace de la oferta de trabajo.
2. Si no se ha proporcionado, solicítala expresamente y no continúes con los pasos siguientes hasta recibirla.

### 2. Carga de recursos
1. Lee íntegramente el historial y perfil maestro en `references/perfil.md`.
2. Lee la estructura, paquetes y comandos de la plantilla en `templates/plantilla.tex`.

### 3. Análisis de coincidencia (Gap Analysis)
1. Extrae de la oferta:
   * Requisitos obligatorios y deseables.
   * Palabras clave técnicas (tecnologías, herramientas, protocolos, sistemas).
   * Habilidades metodológicas y blandas requeridas.
2. Cruza estos requisitos con `references/perfil.md` y clasifica:
   * **Puntos fuertes:** Experiencias y competencias directas ya reflejadas.
   * **Brechas o puntos ausentes:** Requisitos clave de la oferta que no figuran en el perfil o están redactados de forma muy genérica.

### 4. Preguntas de alineación técnica (PASO OBLIGATORIO)
**Detén la ejecución antes de escribir el archivo `.tex`.** Formula entre 3 y 10 preguntas directas y concretas al usuario sobre las brechas detectadas:
1. Herramientas, tecnologías o servicios de la oferta no presentes en `perfil.md` con los que el usuario haya tenido contacto (homelab, proyectos personales, soporte o formación).
2. Metodologías, flujos de trabajo o arquitecturas requeridas donde pueda tener experiencia práctica aplicable.
3. Certificaciones, carnés, disponibilidad o idiomas requeridos que no consten explícitamente.

> **Regla estricta:** Espera siempre la respuesta del usuario a estas preguntas antes de proceder al paso 5.

### 5. Generación del documento LaTeX
Una vez recibidas las respuestas o la confirmación del usuario para avanzar:

1. **Adaptación estratégica del contenido:**
   * Prioriza y reordena la experiencia (siempre respetando el orden crónologico), proyectos y tecnologías según la relevancia para la oferta, si hay experiencias o datos irrelevantes quitalos para no sobrecargar el CV.
   * Incorpora orgánicamente las respuestas aportadas por el usuario en el paso 4.
   * Redacta las viñetas con foco en logros e impacto: verbo de acción + contexto técnico + resultado cuantificable o mejora.
2. **Buenas prácticas de LaTeX:**
   * Respeta los paquetes, dimensiones, comandos y estilos definidos en `templates/plantilla.tex`.
   * Escapa rigurosamente los caracteres especiales en el texto: `%`, `_`, `&`, `#`, `$`, `{`, `}`.
   * Controla la densidad del texto para ajustarse estrictamente a la extensión deseada (mantener el documento en 1 sola página salvo indicación contraria).
3. **Escritura:** Guarda el resultado como `cv.tex` (o con el nombre que especifique el usuario).

### 6. Compilación a PDF y limpieza
1. Inspecciona si el sistema dispone de herramientas de compilación ejecutando comprobaciones en el entorno:
   * Comprobar `tectonic` (`which tectonic`).
   * Comprobar `latexmk` (`which latexmk`).
   * Comprobar `pdflatex` (`which pdflatex`).
2. **Si existe compilador:**
   * **Con Tectonic:** Ejecuta `tectonic cv.tex`.
   * **Con Latexmk:** Ejecuta `latexmk -pdf -interaction=nonstopmode cv.tex`.
   * **Con Pdflatex:** Ejecuta `pdflatex -interaction=nonstopmode cv.tex` (dos pasadas para resolver referencias si aplica).
   * **Limpieza:** Elimina los artefactos temporales si se utilizó `latexmk` o `pdflatex` (`.aux`, `.log`, `.out`, `.fls`, `.fdb_latexmk`).
   * Confirma la generación de `cv.pdf` e indica el porcentaje estimado de match obtenido.
3. **Si no hay compilador:**
   * Informa al usuario de que `cv.tex` está generado y listo para compilar en Overleaf o localmente siguiendo las instrucciones del `README.md`.
