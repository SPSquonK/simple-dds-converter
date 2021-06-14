# Simple DDS Converter

*Because I could not find any DDS parser in Javascript for my files, I built a*
*bad one.*

Simple DDS Converter:
- *Simple* to use (you do not need a PhD in NodeJS / Javascript / Web
Development to use it)
- That can only parses very *simple* DDS file (ie the ones that are storing in
a plain matrice the color of the pixels = the ones that do not have any kind
of compression strategy)
- Has only been "tested" for A1R5G5B5 encoded files

If your kind of DDS files is supported by it, you should consider using
[parse-dds](https://www.npmjs.com/package/parse-dds) instead.

## Basic usage

- Install: `npm install sdds`

- A simple script that converts the `wooden_sword.dds` file into png:
    - `$ npm install pngjs`
    - Put the example code in the `convert_wooden_sword.js` file
    - `$ node convert_wooden_sword.js`

`convert_wooden_sword.js` content:
```js
const fs = require('fs');
const sdds = require('sdds');
const PNG = require("pngjs").PNG;

// Read the dds file
const ddsFile = fs.readFileSync('wooden_sword.dds');
// Build a pngjs image from it
const png = sdds(ddsFile);
// Write in a file the new image
fs.writeFileSync('wooden_sword.png', PNG.sync.write(png));
```


## License

MIT License
