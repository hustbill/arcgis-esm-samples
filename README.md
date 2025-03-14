# @arcgis/core

The samples in this repo extend those [provided by Esri](https://github.com/Esri/jsapi-resources/tree/master/esm-samples). The samples integrate the [@arcgis/core](https://www.npmjs.com/package/@arcgis/core) build of the ArcGIS API for JavaScript with various frameworks, module bundlers and build tools. [Here](https://www.esri.com/arcgis-blog/products/js-api-arcgis/developers/ssr-esm/) is the accompying blog post.

## Get started

Install the modules into your project:

```js
npm install @arcgis/core
```

Then use `import` statements to load individual modules.

```js
import EsriMap from '@arcgis/core/Map';
import MapView from '@arcgis/core/views/MapView';

const map = new EsriMap({
  basemap: "topo-vector"
});

const view = new MapView({
  container: "viewDiv",
  map: map
});
```

## Copy assets

Make sure to copy the API’s assets, which includes styles, images, fonts, and localization files from the `@arcgis/core/assets` folder to your build directory. A simple way to accomplish this is to configure an NPM script that runs during your build process. For example, use npm to install [`ncp`](https://www.npmjs.com/package/ncp) and configure a script in package.json to copy the assets folder. Here’s a React example:

```json
// package.json
{
  "scripts": {
    "copy": "ncp ./node_modules/@arcgis/core/assets ./public/assets",
    "postinstall": "npm run copy",
    ...
  },
}
```

## Configure CSS

The final step is to set up the CSS. Choose a theme and then configure your code to copy the theme files from @arcgis/core/assets/esri/themes/ into your project. Here’s a React example:

```js
// React - index.js
import '@arcgis/core/assets/esri/themes/dark/main.css';
```
