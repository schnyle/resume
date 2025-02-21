# Resume

## LaTeX Workshop VS Code Extension
https://github.com/James-Yu/LaTeX-Workshop/wiki

Use the LaTeX Workshop VS Code extension to build and compile .text files as .pdf documents. The extension requires a compatible LatTeX distribution in the system PATH. TeX Live is strongly recommended.
```
sudo pacman -S texlive // large, ~2.6 GiB
```

Include in PATH
```
sudo ln -s /usr/bin/pdflatex /usr/local/bin // for example
```

Configure VS Code to use pdflatex:
1. Open VS Code Settings
2. Search for "latex-workshop.latex.recipe.default"
3. Change it from "first" to "lastUsed"
4. Search for "latex-workshop.latex.tools" and add the following:
``` json
{
    "latex-workshop.latex.recipe.default": "lastUsed",
    "latex-workshop.latex.recipes": [
        {
            "name": "pdflatex",
            "tools": [
                "pdflatex"
            ]
        }
    ],
    "latex-workshop.latex.tools": [
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ]
        }
    ]
}
``