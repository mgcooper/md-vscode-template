# Markdown editor environment for vscode

This is a markdown editor environment template for vscode. The idea is to have an environment for composing documents in `md` format and then convert to `docx`, `html`, or `pdf` using the `vscode-pandoc` extension. The setup mainly follows [this tutorial](https://thisdavej.com/build-an-amazing-markdown-editor-using-visual-studio-code-and-pandoc/).

## Setup

- Clone this repo  
- Install pandoc [however you want](https://pandoc.org/installing.html)

- Install vscode-pandoc extension
  
    - Press F1 to open the VS Code Command Palette
    - Type ext install vscode-pandoc and press enter to find the extension
    - Press Enter or click the cloud icon to install it (I used the one by Doug Finke)
    - Restart Visual Studio Code if prompted

- Install markdown linter

    - Press F1 to open the VS Code Command Palette
    - Type ext install markdownlint and press enter to find the extension
    - Press Enter or click the cloud icon to install it
    - Restart Visual Studio Code if prompted

- Edit the `css/`, `.markdownlint.json`, and `.vscode/settings.json` files to your liking. I followed the tutorial and used [this css style sheet](https://benjam.info/panam/styling.css) from [here](https://benjam.info/panam/) as a starting point and then changed the code font color to black and removed the italics for level 2 subheading.

- Test it out using `test.md` (see next section).

- Optional: let vscode know to render your md preview using your preferred css style by adding this to `settings.json`, either in the Workspace settings (as it is in this repo) or in your User settings:

    ```json
    "markdown.styles": [
        "css/style.css"
    ],
    ```
- Note: the vscode preview rendered code with yellow font so I added a color attribute to the code container in style.css. 

## Usage

Place cursor anywhere in an open md file, press `command+k` (then release), then press `p`, and options to convert the md file to docx/html/pdf should appear in the vscode command palette. The converted file is saved in the same directory as the `md` file.

## More

Pandoc enables the conversion md to html, docx, pdf, etc. It must be installed and accessible to the vscode python interpreter.

The markdown helper extension was recommended in the [tutorial](https://thisdavej.com/build-an-amazing-markdown-editor-using-visual-studio-code-and-pandoc/) because it makes tables easier, but I chose not to install it because reviews are poor. It seems to be outdated. Instead I installed the highest rated extension Markdown All in One. I did not investigate options to integrate that extension with this environment.

Install Code Spell Check extension or similar.

`/markdownlint.json` enables us to customize the rules used by the markdownlint extension.  
`/css/style.css` is used by html generated by pandoc.  
`/.vscode/settings.json` is the workspace version of the global vscode settings.json file.  
`/.vscode/extensions.json` I think this was auto generated by the `vscode-pandoc` extension.  

[also see this](https://pierrepaci.medium.com/enhance-your-markdown-experience-using-vscode-3caf489888b8)