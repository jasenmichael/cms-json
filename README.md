# cms-json

A lightweight CMS loading and saving its data from/to a json file

[![Build][travis-image]][travis-url]
[![Dependencies][dependencies-badge]][dependencies]
[![Dev dependencies][dev-dependencies-badge]][dev-dependencies]
[![NPM Downloads][downloads-image]][downloads-url]
[![MIT][license-badge]][LICENSE]
[![Node.js version][nodejs-badge]][nodejs]

![cms-json: A lightweight CMS loading and saving its data from/to a json file](https://cdn.pbrd.co/images/GNhDob9.png)

## Install

```bash
npm install -g cms-json
```

## Playground

You can give cms-json a shot in the [playground](http://headlessify.com.s3-website-us-east-1.amazonaws.com/).
It runs the CMS with a default JSON and Schema files. The Save functionality is disabled, but you can export
your work via the 'Export' button.

## Quick Start

```bash
cms-json
```

Then open your browser at:

    http://localhost:3000

## Why do I need this?

In a small IT company, the question of how and by whom your website can be updated is a recurrent
one.

I have explored many solutions, from pure HTML sites controlled by the dev team, using fancy
web frameworks, to sites generated by the marketing/product team using pure wysiwyg tools like
Adobe Muse, not to mention heavy stuff like Wordpress or Drupal.

I finally came up with that very simple feature set:

* The **Content** part of my site is stored as a JSON file
* It can be edited **by tech or non tech people** via a **very simple UI**
* It is embedded in the web site / web app by **developers**, and exploited **with the technology they like**
* It can be **stored in Git**, so that in case of conflicts, it can be solved as with any other source files
* Last but not least, it can be run as **an npm module**. No Apache, no nginx, no PHP, no database, just simplicity of use.

Although tons of CMS products exist on the market, I didn't find any one fulfilling the
constraints above.

## Usage

```
Usage: cms-json {OPTIONS}

Standard Options:

    --schema, -s   JSON schema file.
                   Default is data/schema.json.

    --data, -d     JSON data file.
                   Default is data/data.json.

    --port, -p     Server port.
                   Default is 3000.

```
[downloads-image]: https://img.shields.io/npm/dm/cms-json.svg
[downloads-url]: https://npmjs.org/package/cms-json
[travis-image]: https://img.shields.io/travis/amelki/cms-json/master.svg?label=build
[travis-url]: https://travis-ci.org/amelki/cms-json
[dev-dependencies-badge]: https://david-dm.org/amelki/cms-json/dev-status.svg
[dev-dependencies]: https://david-dm.org/amelki/cms-json?type=dev
[dependencies-badge]: https://david-dm.org/amelki/cms-json/status.svg
[dependencies]: https://david-dm.org/amelki/cms-json
[license-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[license]: https://github.com/amelki/json-pretty-html/blob/master/LICENSE
[nodejs-badge]: https://img.shields.io/badge/node->=%206.9-blue.svg
[nodejs]: https://nodejs.org/dist/latest-v6.x/docs/api/
[npm-badge]: https://img.shields.io/badge/npm->=%203.10.8-blue.svg
[npm]: https://docs.npmjs.com/

## What's new

v0.1.1

* The 'model' files are now standard JSON Schema Draft 6 files. See http://json-schema.org/.
* Added a 'Developer' mode, to add/edit/delete nodes and fields. This mode is activated by default.
Switching to 'Author' mode disables all schema editing features.
* On a side note, I migrated the entire code base to Typescript.

v0.1.3

* Show JSON data and schema on the right and sync with editor
* Improved author view (removed useless dev stuff)
## API

<a name="run"></a>

### run([options]) ⇒ <code>\*</code>
Run an Express server embedding a simple UI for editing the content of the given dataFile.

**Kind**: global function  
**Returns**: <code>\*</code> - The express app  

| Param | Type | Description |
| --- | --- | --- |
| [options] | <code>Object</code> |  |
| [options.dataFile] | <code>Object</code> | A JSON file with the content. This parameter is mandatory. 		The	content authored from the web site will be saved with that path name. 		The structure of this JSON file must match the model. 		See an example here: https://github.com/amelki/cms-json/blob/master/default/data.json |
| [options.modelFile] | <code>Object</code> | A JSON schema file representing the model to support/ease authoring via the UI. This parameter is mandatory. 		See an example here: https://github.com/amelki/cms-json/blob/master/default/schema.json |
| [options.port] | <code>Object</code> | The server port. 3000 by default |

