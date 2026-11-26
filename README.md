# 📚 Template de Manuales de Materias en LaTeX

Repositorio central de plantillas, estilos y recursos en **LaTeX** para la redacción, compilación y mantenimiento de los manuales de cátedra y guías técnicas de las materias, con exportación a **PDF** y formato editable (**DOC / DOCX**).

---

## 📐 Descripción del Proyecto

El objetivo de este repositorio es unificar el formato visual, tipográfico y estructural de los manuales de las materias de **impatrq**, facilitando la colaboración entre docentes y becarios y asegurando entregables consistentes y listos para distribución.

### Características Principales:
* **Identidad Visual Unificada:** Encabezados, pies de página, carátulas, tablas, bloques de código y recuadros técnicos estandarizados.
* **Soporte Técnico y Científico:** Entornos preparados para fórmulas matemáticas, diagramas en bloques/esquemas, tablas de especificaciones y referencias cruzadas.
* **Salida Multi-Formato:** Compilación limpia a **PDF** mediante motores LaTeX (`pdflatex` / `xelatex` / `latexmk`) y flujo de conversión a **DOC / DOCX** cuando se requiera edición en procesador de texto.
* **Modularidad:** Separación del documento principal (`main.tex`), preámbulo/estilos y capítulos o anexos por materia.

---

## 📂 Estructura Sugerida del Repositorio

```text
Template_Manuales_Materias_Latex/
├── template/               # Plantilla base (main.tex, preámbulo, estilos .sty y carátula)
├── chapters/               # Secciones o módulos reutilizables (introducción, prácticas, anexos)
├── assets/                 # Imágenes, logos institucionales, diagramas y figuras
├── scripts/                # Scripts de compilación (PDF / Pandoc a DOCX) y limpieza
├── docs/                   # Guía de estilo, ejemplos de uso y notas de formato
└── README.md               # Documentación principal del repositorio
```

---

## 🛠️ Compilación y Generación de Formatos

### 1. Generación de PDF
Desde la carpeta correspondiente al manual o plantilla:

```bash
latexmk -pdf main.tex
```

*(Si usás `xelatex` por fuentes o caracteres especiales)*:

```bash
latexmk -xelatex main.tex
```

Para limpiar archivos auxiliares de compilación (`.aux`, `.log`, `.toc`, `.out`, etc.):

```bash
latexmk -c
```

### 2. Conversión a DOC / DOCX
Cuando necesites generar un borrador o versión editable en formato Word a partir del fuente LaTeX:

```bash
pandoc main.tex -s -o manual.docx
```

> 💡 **Nota:** Revisá siempre tablas complejas, ecuaciones extensas y figuras flotantes en el `.docx` resultante, ya que ciertos paquetes de LaTeX requieren ajustes manuales al convertir a formato de procesador de texto.

---

## 🌿 Estructura de Ramas

Este repositorio sigue una convención de dos ramas principales:

| Rama | Propósito |
| :--- | :--- |
| `main` | Plantillas y manuales validados y validados para uso. Nunca se pushea directo. Solo acepta merges vía PR aprobada por un docente. |
| `develop` | Rama de integración de mejoras, correcciones y nuevas secciones. Cualquier becario puede hacer merge vía PR sin requerir aprobación. |

Las ramas de trabajo se crean a partir de `develop` con nombres descriptivos:
* `feature/nombre-del-cambio` *(ej. `feature/caratula-materia`)*
* `fix/descripcion-del-ajuste` *(ej. `fix/margenes-tablas`)*
* `docs/lo-que-se-documenta` *(ej. `docs/guia-compilacion-docx`)*

---

## 🔄 Flujo de Trabajo

`[rama feature]` → PR → `[develop]` → PR (aprobación docente) → `[main]`

1. **Creá tu rama desde `develop`:**
   ```bash
   git checkout develop
   git pull origin develop
   git checkout -b feature/mi-mejora-latex
   ```
2. **Trabajá en tu rama y commiteá con mensajes descriptivos:**
   ```bash
   git commit -m "feat: agrega plantilla base para manual de laboratorio"
   ```
3. **Abrí una *Pull Request* hacia `develop` cuando terminés.**
4. **Una vez integrado en `develop` y compilado sin errores, un docente abre la PR hacia `main`.**

> ⚠️ **Nunca pushear directamente a `main` ni a `develop`.** Siempre trabajar desde ramas propias y abrir PR.

---

## 📋 Convención de Commits

Usamos una convención simple basada en prefijos:

| Prefijo | Cuándo usarlo |
| :--- | :--- |
| `feat:` | Nueva plantilla, paquete, entorno o sección agregada |
| `fix:` | Corrección de errores de compilación, formato o maquetación |
| `docs:` | Cambios en documentación o guías de uso |
| `refactor:` | Reorganización de archivos `.tex` / `.sty` sin cambiar el resultado visual |
| `chore:` | Limpieza de temporales, actualización de scripts o ajustes menores |

---

## 👥 Equipo

| Rol | Responsabilidades en GitHub |
| :--- | :--- |
| **Docentes** | Aprueban PRs hacia `main`, administran la organización y validan los manuales |
| **Becarios** | Crean ramas, desarrollan/ajustan plantillas y contenidos, abren PRs hacia `develop` y participan en revisiones |

---

## 🔗 Recursos

* [Organización en GitHub (impatrq)](https://github.com/impatrq)
* [Repositorio del proyecto](https://github.com/impatrq/Template_Manuales_Materias_Latex)
* [Tablero del laboratorio (GitHub Projects)](https://github.com/orgs/utn-fra-lse/projects/2)
* [Repositorio de gestión operativa](https://github.com/utn-fra-lse/gestion) *(issues, documentación, inventario)*
