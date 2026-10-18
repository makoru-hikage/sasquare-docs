# SASQUARE — LaTeX Source

The LaTeX source for the SASQUARE paper. To read the compiled output, open `sasquare.pdf`.

---

## Dependencies

### Debian / Ubuntu

```sh
sudo apt install \
  texlive-latex-recommended \
  texlive-latex-extra \
  texlive-bibtex-extra \
  texlive-pictures \
  biber \
  latexmk
```

> **Note:** `nicematrix` is included in `texlive-latex-extra`.  
> The bibliography backend is **biber** (not bibtex) — do not substitute.

### Arch Linux

```sh
sudo pacman -S \
  texlive-latex \
  texlive-latexrecommended \
  texlive-latexextra \
  texlive-bibtexextra \
  texlive-pictures \
  texlive-binextra \
  biber
```

> `latexmk` is bundled inside `texlive-binextra`.  
> `nicematrix` is inside `texlive-latexextra`.  
> `biblatex` (used as the bibliography package) is inside `texlive-bibtexextra`.

---

## Viewing the PDF

```sh
zathura sasquare.pdf
```

> Uses [Zathura](https://pwmt.org/projects/zathura/) with the `zathura-pdf-mupdf` backend.  
> Keyboard-driven, minimal, terminal-friendly.

---

## Compile

### One-shot build (recommended)

```sh
latexmk -pdf -interaction=nonstopmode sasquare.tex
```

### Watch mode (auto-recompile on save)

```sh
latexmk -pvc -pdf -interaction=nonstopmode sasquare.tex
```

> `-pvc` watches the file and recompiles automatically whenever you save.  
> Press `Ctrl+C` to stop.

---

## Clean build artifacts

```sh
latexmk -C
```

This removes all generated files including `sasquare.pdf`.  
To keep the PDF and only clean intermediates:

```sh
latexmk -c
```
