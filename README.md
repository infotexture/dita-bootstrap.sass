# DITA Bootstrap Sass

<a href="https://www.dita-ot.org"><img src="https://www.dita-ot.org/images/dita-ot-logo.svg" align="left" height="55" width="80"></a>

<a href="https://sass-lang.com"><img src="https://sass-lang.com/assets/img/logos/logo.svg" align="right" width="55"></a>

_DITA Bootstrap Sass_ is a [DITA Open Toolkit plug-in](https://www.dita-ot.org/plugins) that allows you to extend the [DITA Bootstrap](https://infotexture.github.io/dita-bootstrap/) HTML output via [Syntactically Awesome Style Sheets][Sass].

<!-- MarkdownTOC levels="2,3" -->

- [Installation](#installation)
  - [Installing DITA-OT](#installing-dita-ot)
  - [Installing the plug-in](#installing-the-plug-in)
  - [Installing Node.js](#installing-nodejs)
- [Usage](#usage)
  - [Generating a CSS theme from Sass](#generating-a-css-theme-from-sass)
  - [Using the generated theme](#using-the-generated-theme)
- [License](#license)

<!-- /MarkdownTOC -->

## Installation

The _DITA Bootstrap Sass_ plug-in has been tested with [DITA-OT 4.x](http://www.dita-ot.org/download). Use the latest version for best results.

### Installing DITA-OT

1.  Download the latest distribution package from the project website at
    [dita-ot.org/download](https://www.dita-ot.org/download).
2.  Extract the contents of the package to the directory where you want to install DITA-OT.
3.  **Optional**: Add the absolute path for the `bin` directory to the _PATH_ system variable.

    This defines the necessary environment variable to run the `dita` command from the command line.

See the [DITA-OT documentation](https://www.dita-ot.org/4.0/topics/installing-client.html) for detailed installation instructions.

### Installing the plug-in

- Run the plug-in installation commands:

```console
dita install https://github.com/jason-fox/fox.jason.extend.css/archive/master.zip
dita install https://github.com/infotexture/dita-bootstrap/archive/master.zip
dita install https://github.com/infotexture/dita-bootstrap.sass/archive/master.zip
```

### Installing Node.js

<a href="https://nodejs.org/"><img src="https://simpleicons.org/icons/nodedotjs.svg" align="right" width="70" height="70" align="right" width="55" height="55"></a>

The _DITA Bootstrap Sass_ plug-in uses the [Node.js](https://nodejs.org/) JavaScript runtime to generate the `theme.css` file. Node.js must therefore be present for the index to be generated successfully.

To download and install a copy, follow the instructions for your operating system on the [download page](https://nodejs.org/en/download/).

## Usage

### Generating a CSS theme from Sass

To generate a CSS theme from your custom Sass source files, follow the instructions in the [sass/override.scss](./sass/override.scss) file and use the `sass-bootstrap` transformation:

```console
PATH_TO_DITA_OT/bin/dita -f sass-bootstrap -i PATH_TO_DITAMAP
```

A `theme.css` file will be generated in the `sass` folder. To preview the results of your customizations, open the [sass/index.html](./sass/index.html) file in a web browser.

### Using the generated theme

To use a pregenerated Sass theme as CSS in the HTML Bootstrap output, run the `html5-bootstrap` transformation and pass the `bootstrap.sass` parameter to the `dita` command:

```console
PATH_TO_DITA_OT/bin/dita -f html5-bootstrap -o out -i PATH_TO_DITAMAP \
  --bootstrap.sass=yes
```

## License

[Apache 2.0](LICENSE) © 2023 · infotexture · Jason Fox

[Sass]: https://sass-lang.com
