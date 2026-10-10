---
name: CV LaTeX Tailor
description: Adapta currículums en formato LaTeX a partir de un perfil maestro y una oferta de empleo, identificando brechas técnicas y consultando detalles omitidos para maximizar la afinidad.
---

## Objetivo

Generar un archivo `cv.tex` adaptado a una oferta laboral específica a partir del perfil maestro en `references/perfil.md` y la plantilla base en `templates/plantilla.tex`.

---

## Reglas fijas e inquebrantables

1. **Datos de contacto obligatorios:** En el bloque de cabecera o datos de contacto, incluir **siempre** el teléfono `+34 659 33 29 93` junto con el resto de datos de contacto del perfil.
2. **Sin resumen profesional:** **Eliminar y omitir por completo** cualquier sección, párrafo o bloque de tipo "Resumen ejecutivo", "Perfil profesional", "Sobre mí" o "Professional Summary". El contenido debe empezar directamente por la formación o la experiencia.
3. **Filtrado estricto de experiencia:** Descartar activamente cualquier experiencia laboral, rol o proyecto que no aporte valor técnico directo ni guarde relación con la vacante. Menos es más: incluir únicamente lo que sume puntos de afinidad.
4. **Límite estricto de 1 sola página:** El documento final **DEBE ocupar exactamente 1 página**. No se admite desborde a una segunda página en Overleaf. La cantidad de viñetas, la longitud de las líneas y los espaciados verticales deben ajustarse rigurosamente a esta restricción.

---

## Flujo de trabajo

### 1. Validación de la oferta laboral
1. Comprueba si el usuario ha suministrado la descripción, requisitos o enlace de la oferta de trabajo.
2. Si no se ha proporcionado, solicítala expresamente y no continúes con los pasos siguientes hasta recibirla.

### 2. Carga de recursos
1. Lee íntegramente el perfil maestro en `references/perfil.md`.
2. Lee la estructura, comandos y paquetes de la plantilla en `templates/plantilla.tex`.

### 3. Análisis de coincidencia (Gap Analysis) y selección
1. Extrae de la oferta:
   * Requisitos obligatorios y deseables.
   * Palabras clave técnicas (tecnologías, herramientas, protocolos, sistemas, metodologías).
2. Cruza estos requisitos con `references/perfil.md`:
   * Identifica qué experiencias y proyectos tienen impacto directo sobre los requisitos de la vacante.
   * **Marca para descarte** aquellas experiencias que no aporten valor relevante a la oferta.
   * Detecta brechas técnicas: requisitos de la oferta ausentes en el perfil o poco desarrollados.

### 4. Preguntas de alineación técnica (PASO OBLIGATORIO)
**Detén la ejecución antes de redactar el código LaTeX.** Formula entre 3 y 10 preguntas directas y concisas al usuario sobre las brechas detectadas:
1. Herramientas, tecnologías o servicios requeridos en la oferta no presentes en `perfil.md` con los que el usuario haya tenido contacto (homelab, proyectos personales, soporte o formación).
2. Metodologías, entornos o funciones requeridas donde pueda tener experiencia práctica aplicable.
3. Certificaciones, carnés, disponibilidad o idiomas requeridos que no consten explícitamente.

> **Regla estricta:** Espera siempre la respuesta del usuario a estas preguntas antes de proceder a la redacción del currículum.

### 5. Generación del documento LaTeX
Una vez recibidas las respuestas o la confirmación del usuario para avanzar:

1. **Estructura y contenido:**
   * **Contacto:** Inserta siempre el teléfono `+34 659 33 29 93`.
   * **Perfil:** Ocmite cualquier bloque de resumen personal o ejecutivo.
   * **Experiencia:** Incluye únicamente los puestos relevantes para la oferta, redactando entre 2 y 4 viñetas de alto impacto por puesto (acción + tecnología + resultado cuantificable).
   * **Proyectos / Habilidades:** Prioriza tecnologías coincidentes con las palabras clave de la vacante.
2. **Sintaxis y ajuste de página:**
   * Respeta los paquetes, dimensiones, comandos y estilos definidos en `templates/plantilla.tex`.
   * Escapa rigurosamente los caracteres reservados de LaTeX en el texto: `%`, `_`, `&`, `#`, `$`, `{`, `}`.
   * Modula la cantidad de viñetas y elementos para garantizar el **límite estricto de 1 página**.
3. **Entrega:**
   * Guarda el código generado en el archivo `cv.tex` (o muéstralo completo si el usuario solicita copiarlo directamente).
   * Indica al usuario que el código está listo para pegar y compilar en Overleaf junto con un breve resumen de las decisiones de adaptación tomadas y el porcentaje estimado de match obtenido.
