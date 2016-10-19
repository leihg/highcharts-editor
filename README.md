Highcharts Editor
===

*Stand-alone and embeddable chart editor for Highcharts*

![screenshots/customize.png](screenshots/customize.png)

## Introduction

`highcharts-editor` is a lightweight chart editor for highcharts that can be embedded into existing frameworks and libraries, or used stand-alone.
It requires no back-end service to operate.

## Features
	
  * Light on dependencies: requires only Highcharts, FontAwesome, and (optionally) two Google Fonts
  * Lightweight: weighs in at ~140kb non-gzipped
  * 100% client-side
  * Outputs embeddable HTML, JavaScript, and JSON
  * Optional wizard-style interface
  * Highly configurable
  * Plug-in system

## Installing and Building

**Pre-built**

You can find pre-built stable releases [here](https://github.com/highcharts/highcharts-editor/releases).

**Package Managers**

The editor is pushed to NPM and Bower under `highcharts-editor`.

**Cloning and building the repository**

	git clone https://github.com/highcharts/highcharts-editor
	cd highcharts-editor
	npm install
	gulp

**Build options**
  * `gulp`: Builds distribution packages for the editor and the bundled integrations and plugins
  * `gulp electron`: Builds Electron packages for Windows/Linux/OSX
  * `gulp with-advanced`: Builds packages for the advanced editor which exposes all API settings

**Notice for windows users:** You need [7zip](http://www.7-zip.org/) installed and added to your path for `gulp electron` to work!

This will put a built version in the `dist` folder.

## Test Server

If extending/modifying the editor code itself (or adding themes etc.), use the bundled
express server. This server uses the source files directly without minifying/concatenating which
makes it easier to debug and test things. It also bakes the Less files for each request.

Run `node bin/www` to start it, then head to `http://127.0.0.1:3005`.

## Embedding Hello World

	<!DOCTYPE html>
	<html>
		<head>
      <link href="highcharts-editor.min.css" type="text/css" rel="stylesheet"/>
      <script src="highcharts-editor.min.js" type="text/javascript" charset="utf-8"></script>
		</head>
		<body>
		</body>
		<script>
			//Create an editor widget and attach it to the document body      
			highed.Editor(document.body).on('ChartChange', function (data) {
          //Do something with the modified chart here.
      });
		</script>
	</html>

## Integrations

A number of example integrations are included in the editor:
  * [TinyMCE](https://github.com/highcharts/highcharts-editor/wiki/TinyMCE)
  * [Wordpress](https://github.com/highcharts/highcharts-editor/wiki/Wordpress)
  * [Electron](https://github.com/highcharts/highcharts-editor/wiki/Native-OSX-Windows-Linux)
  * [CKEditor](https://github.com/highcharts/highcharts-editor/wiki/CKEditor)

## API Reference & General Documentation

  * [API reference](https://github.com/highcharts/highcharts-editor/wiki/API)
  * [Full documentation](https://github.com/highcharts/highcharts-editor/wiki)
  * [Using plug-ins](https://github.com/highcharts/highcharts-editor/wiki/Plugins)
  * [Enabling the advanced editor](https://github.com/highcharts/highcharts-editor/wiki/Enable-Advanced-Customization)
  * [Customizing available editable properties](https://github.com/highcharts/highcharts-editor/wiki/Choosing-Options)
  * [Adding custom templates](https://github.com/highcharts/highcharts-editor/wiki/Custom-Templates)
  * [Disabling editor features](https://github.com/highcharts/highcharts-editor/wiki/Disable-Features)

Documentation can also be generated offline by running `js-skald` in the project root, which outputs the API reference
in the `docs/`.

`js-skald` is a simple doc generator that outputs markdown files and JSON trees representing the code.
It can be installed by running `npm install -g js-skald`. 

## License

The editor is licensed under [MIT](LICENSE).

Note that the use of Highcharts itself (which the editor depends on) falls under the [Highcharts License](https://github.com/highcharts/highcharts/blob/master/license.txt).
