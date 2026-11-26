---
title: Estilos LaTeX propios
author: Carlos Llamedo
date: 2026-11
---

# Estilos LaTeX propios

Paquetes de estilo para LaTeX (LuaLaTeX). Página, fuentes, títulos, encabezados, índices, notas y bibliografía.

- [`memoria.sty`](memoria.sty). Tesis sobre la clase `book`. Opciones y comandos en [`memoria`](docs/memoria.md).
- [`temas.sty`](temas.sty). Temas de oposición sobre la clase `article`: título e índice en la primera página y secciones seguidas.

## Dependencias

- Una distribución [TeX](https://ctan.org/starter) con [LuaTeX](https://www.luatex.org/download.html).
- Las fuentes por defecto de los estilos:
    1. _Serif_: [Arno Pro](https://fonts.adobe.com/fonts/arno) o [Source Serif 4](https://github.com/adobe-fonts/source-serif/releases/latest)
    2. _Sans_: [Cronos Pro](https://fonts.adobe.com/fonts/cronos) o [Source Sans 3](https://github.com/adobe-fonts/source-sans/releases/latest)
    3. Monoespaciada: [Source Code Pro](https://github.com/adobe-fonts/source-code-pro/releases/latest)
    4. Matemática: [STIX Two Math](https://github.com/stipub/stixfonts/releases/latest)

Los estilos no están limitados a estas fuentes. Si Arno Pro o Cronos Pro no están instaladas, se usan Source Serif 4 y Source Sans 3. Cualquier otra se elige con `\setmainfont` o, desde Pandoc, con `mainfont`, `sansfont`, `monofont` y `mathfont`.

## Instalación

LaTeX busca los paquetes en su árbol de archivos personal (TEXMFHOME, normalmente `~/.local/share/texmf/` o `~/Library/texmf/`, consúltese la documentación de la distribución LaTeX). Clona el repositorio dentro de él:

```bash
TEXMFHOME="$(kpsewhich -var-value TEXMFHOME)"
git clone https://github.com/carlos-llamedo/entorno-latex "$TEXMFHOME/tex/latex/"
```

## Uso

En LaTeX, como cualquier paquete:

```latex
\documentclass{book}
\usepackage[headscaps]{memoria}
```

Desde Pandoc, con la plantilla `pandoc.tex`:

```yaml
fontfamily: memoria
fontfamilyoptions:
  - headscaps=true
```

## Proyectos similares

- [`latex-custom-kjh`](https://github.com/kjhealy/latex-custom-kjh), los estilos LaTeX de Kieran Healy.

## Derechos

Este repositorio está bajo una [licencia MIT](LICENCE.md), Copyright © 2026 Carlos Llamedo.

El icono de versión es «git-fork», en su grosor _light_, de [Phosphor Icons](https://github.com/phosphor-icons/core), bajo licencia MIT, Copyright © 2023 Phosphor Icons.
