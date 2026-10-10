# CV LaTeX (OpenCode Skill)

Skill para [OpenCode](https://opencode.ai) diseñada para adaptar ofertas de empleo específicas usando el perfil profesional del usuario. Genera un CV en formato `PDF` usando una plantilla LaTeX.
Compara los requisitos de la vacante frente a tu historial profesional, detecta brechas técnicas, formula preguntas para maximizar las posibilidades, genera el archivo `.tex` y luego el `.pdf` en caso de que se cumplan los requisitos.

> **Nota:** 
> Se recomienda instalar un compilador de LaTeX cómo: **tectonic**, **latexmk** o **pdflatex**.

---

## Estructura del repositorio

```text
.
├── SKILL.md                  # Definición y flujo de trabajo del agente
├── templates/
│   └── plantilla.tex         # Plantilla LaTeX (Jake's Resume)
├── references/
│   ├── perfil.md             # Historial técnico y profesional completo en formato MarkDown
│   └── perfil.example.md     # Estructura de ejemplo
├── .gitignore
└── README.md
