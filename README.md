# Plantilla TFG/TFM — Facultad de Informática (UMU)

Plantilla LaTeX para Trabajos Fin de Grado y Fin de Máster de la Facultad de Informática de la Universidad de Murcia, con la identidad corporativa de la UMU.

## Uso en Overleaf

1. Sube el proyecto como `.zip` (*New Project > Upload Project*).
2. En *Menu > Compiler* elige **LuaLaTeX**. Con pdfLaTeX (el valor por defecto de Overleaf) la compilación se detiene con un aviso.

El fichero `.latexmkrc` del proyecto ya configura LuaLaTeX y biber.

## Compilación local

Requiere **TeX Live 2024 o posterior** (o MiKTeX actualizado).

```sh
latexmk      # compila main.tex con LuaLaTeX y biber
latexmk -c   # borra los ficheros auxiliares
```

La lista de acrónimos se genera sola durante la compilación: no hace falta ejecutar `makeglossaries`.

## Primeros pasos

- Rellena los datos del trabajo al principio de `main.tex`: título, autor, tutores, departamentos (opcionales) y fecha. Los campos opcionales pueden dejarse vacíos (`{}`).
- Elige el tipo de trabajo con `[tfg]` o `[tfm]` en `\usepackage[tfg]{config/umu_style}`. Cambia la portada, la declaración de originalidad y el resto de textos.
- Añade la opción `colorenlaces` para que los enlaces salgan en color en la versión digital.
- Para la versión impresa a doble cara, cambia `oneside` por `twoside` en `\documentclass`.
- Comenta los `\input` de los preliminares opcionales que no uses: preámbulo, agradecimientos, dedicatoria y cita.

## Estructura

| Ruta | Contenido |
|---|---|
| `main.tex` | Documento principal: datos del trabajo y orden de los apartados. |
| `config/umu_style.sty` | Estilo de la plantilla (paquetes, colores, cabeceras, opciones). |
| `config/listing-styles.sty` | Estilos para código fuente por lenguaje. |
| `config/portada/` | Portada y subportada (no hace falta tocarlas). |
| `config/logos/` | Logotipos de la UMU y de la Facultad. |
| `preambulos/` | Preliminares: preámbulo, agradecimientos, dedicatoria, cita, declaración, resumen, abstract y extended abstract. |
| `capitulos/` | Capítulos del trabajo. |
| `anexos/` | Anexos y definición de acrónimos (`acronimos.tex`). |
| `bibliografia/bibliografia.bib` | Referencias en formato biblatex. |
| `figuras/` | Imágenes del documento. |

## Cómo se hace…

Los capítulos de ejemplo muestran cada uno de estos casos en su código fuente:

- **Citar:** `\cite{clave}` (capítulo 2). Solo aparecen en la bibliografía las referencias citadas.
- **Acrónimos:** `\gls{etiqueta}` (capítulo 1). La primera aparición se escribe completa y la lista final solo incluye los usados.
- **Referencias cruzadas:** `\cref{etiqueta}` escribe «la figura 3.1», «el capítulo 2», etc.
- **Figuras, subfiguras y tablas:** capítulo 3.
- **Código y ecuaciones:** capítulo 4, con `\begin{lstlisting}[style=Python]`.
- Los índices de figuras, tablas y listados solo aparecen si el documento tiene contenido de ese tipo.

Si los necesitas, `siunitx` (unidades y números) y `tcolorbox` (cajas) se pueden añadir con `\usepackage` en `main.tex`.

## Créditos y licencia

- José Manuel Requena Plens: autor original de la plantilla.
- Pablo José Rocamora Zamora: modificaciones y mejoras posteriores.
- Adrián Cánovas Rodríguez: versión con la nueva identidad corporativa.

Código bajo licencia MIT (ver `LICENSE`). Los logotipos de la Universidad de Murcia y de la Facultad de Informática son propiedad de sus titulares y no están cubiertos por esa licencia.

Contacto: adriancr@um.es
