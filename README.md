# latex-mermaid
LaTeX package to interface with mermaid (npm)

Source : https://github.com/Kochise/latex-mermaid

## installation

Get 'nvm' for Windows : https://github.com/coreybutler/nvm-windows/releases<br>
Uncompress/install it where you need.<br>

```batch
\>cd nvm
\nvm>nvm install 12.17.0
\nvm>nvm use 12.17.0
\nvm>node -v
v12.17.0
\nvm>npm install @mermaid-js/mermaid-cli

xcopy /c /h /e /r /q /y latex-mermaid <miktex>\texmfs\install\tex\latex\mermaid
start "" "<miktex>\miktex-portable.cmd"
```

Refresh the filename database.<br>
Update the package database.<br>
You should be ready to go.<br>

Alternatively, you can use https://github.com/Kochise/win_portable

## usage

See https://github.com/mermaid-js/mermaid-cli<br>

In your preamble :

```latex
\def\imagepath{./images}
\graphicspath{{\imagepath/}}
\usepackage[imagepath=\imagepath, theme={neutral}]{mermaid}
```

In your document :

```latex
% https://mermaid-js.github.io/mermaid-live-editor
%\begin{mermaid}[width]{caption}{refname}
\begin{mermaid}[8cm]{mermaid caption example}{mermaidexample}
graph TD
  A[Christmas] -->|Get money| B(Go shopping)
  B --> C{Let me think}
  C -->|One| D[Laptop]
  C -->|Two| E[iPhone]
  C -->|Three| F[fa:fa-car Car]
\end{mermaid}
```

## options

What is available through 'mermaid-cli' :

```
% Output the version number
-V, --version

% Theme of the chart, could be default, forest, dark or neutral. Optional. Default: default (default: default)
-t, --theme [theme]

% Width of the page. Optional. Default: 800 (default: 800)
-w, --width [width]

% Height of the page. Optional. Default: 600 (default: 600)
-H, --height [height]

% Input mermaid file. Required.
-i, --input <input>

% Output file. It should be either svg, png or pdf. Optional. Default: input + ".svg"
-o, --output [output]

% Background color. Example: transparent, red, '#F0F0F0'. Optional. Default: white
-b, --backgroundColor [backgroundColor]

% JSON configuration file for mermaid. Optional
-c, --configFile [configFile]

% CSS file for the page. Optional
-C, --cssFile [cssFile]

% JSON configuration file for puppeteer. Optional
-p, --puppeteerConfigFile [puppeteerConfigFile]

% Output usage information
-h, --help
```

Cannot be specified on a group basis, only in the preamble.<br>
Just add the requested parameters without the leading dash(es).<br>

```latex
\usepackage[b={transparent}]{mermaid}
```

or :

```latex
\usepackage[backgroundColor={#F0F0F0}]{mermaid}
```

Avoid :

```
i, input	: because used by the provided text
o, output	: because using the refname
width		: because used to specify the tex picture width, not the output width
```

## limitations

Your imagination.

## greetings

Based on https://github.com/dakusui/latex-ditaa<br>
Also interested into https://github.com/sile-typesetter/sile<br>
