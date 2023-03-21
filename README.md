## LaTeX Thisis template

This is a diploma thesis template for students studying at the faculty of Computer Science, Constructor University. The template is based on the SPbSU math-mech thesis [template](https://www.papeeria.com/p/73174b63d0ffee4d37da4abda3647095?withLastOpenedFile=false). 

## To run in vscode with LaTeX workshop plugin:
Download the [multi-command](https://marketplace.visualstudio.com/items?itemName=ryuta46.multi-command) plugin. 

Update `settings.json` file, by adding this property: 
```json
"latex-workshop.latex.build.forceRecipeUsage": false,
"latex-workshop.latex.recipes":[
        {
            "name": "latexmk",
            "tools": [
                "latexmk"
            ]
        },
        {
            "name": "latexmk (latexmkrc)",
            "tools": [
                "latexmk_rconly"
            ]
        },
        {
            "name": "latexmk (lualatex)",
            "tools": [
                "lualatexmk"
            ]
        },
        {
            "name": "latexmk (xelatex)",
            "tools": [
                "xelatexmk"
            ]
        },
        {
            "name": "pdflatex -> bibtex -> pdflatex * 2",
            "tools": [
                "pdflatex",
                "bibtex",
                "pdflatex",
                "pdflatex"
            ]
        },
        {
            "name": "Compile Rnw files",
            "tools": [
                "rnw2tex",
                "latexmk"
            ]
        },
        {
            "name": "Compile Jnw files",
            "tools": [
                "jnw2tex",
                "latexmk"
            ]
        },
        {
            "name": "Compile Pnw files",
            "tools": [
                "pnw2tex",
                "latexmk"
            ]
        },
        {
            "name": "tectonic",
            "tools": [
                "tectonic"
            ]
        },
        {
            "name": "lualatex -> bibtex -> lualatex * 2",
            "tools": [
                "lualatexmk",
                "bibtex",
                "lualatexmk",
                "lualatexmk"
            ]
        },
    ]
```
And `keybindings.json` file by adding this property:
```json
{
    {
        "key": "cmd+e",
        "when": "resourceExtname == .tex",
        "command": "extension.multiCommand.execute",
        "args": {
            "sequence": [
                {
                    "command": "latex-workshop.recipes", 
                    "args": "lualatex -> bibtex -> lualatex * 2"
                }, 
                {
                    "command": "latex-workshop.refresh-viewer"
                }
            ]
        }
    },
}
```
After that, you can use `cmd+e` to build and refresh the pdf viewer.