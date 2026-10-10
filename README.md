# CV LaTeX (OpenCode Skill)

Skill para [OpenCode](https://opencode.ai) diseñada para adaptar ofertas de empleo específicas usando el perfil profesional del usuario. 
Genera un CV en formato `.tex` usando la plantilla **LaTeX** de *Jake's Resume*.

Compara los requisitos de la vacante frente a tu historial profesional, detecta brechas técnicas, formula preguntas para maximizar las posibilidades y genera un archivo LaTeX.

> [!TIP]
> Se recomienda instalar un compilador de LaTeX cómo: **tectonic**, **latexmk** o **pdflatex**.

---

## Vincular la *skill* con **OpenCode**

```bash
# Creamos el directorio de skills (si no esta creado)
mkdir -p ~/.config/opencode/skills

# Creamos el enlace simbólico hacia este repositorio
ln -s ./ (o la ruta en donde hayas clonado este repositorio) ~/.config/opencode/skills/cv-latex
```

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
