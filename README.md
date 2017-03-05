# Multi-files RevealJS presentation

## Principles

[RevealJS](http://lab.hakim.se/reveal-js/) is a really great HTML5 presentation tool.
One missing feature is to allow to split the presentation - generally in one `.html` file - into several files.

Thanks to the usage of [HTML Import]() feature, we allow to split the

## Make your own presentation

Simply fork this repository and start writing your presentation.

When adding one file, refer it in the `<head>` of your `index.html` like this:

```html
<link rel="import" href="./partials/01-intro.html" role="slide">
```

The `role="slide"` is important, so the JavaScript plugin will be able to find the list of files to load.
Note that the files loaded will be loaded in the order of their definition in the `index.html`.

The **import** feature is not always supported natively by browsers ([see here](http://caniuse.com/#feat=imports)), so [the webcomponentsjs polyfill](https://github.com/webcomponents/webcomponentsjs) is added in the `index.html`.

In the HTML file, the script will look for all `<section class="partial">` and then will add their content in the `<div id="slides">` node of the root `index.html`.


## Live reload

I've added a [live server](https://github.com/tapio/live-server) dependency in order to automatically reload the browser when you change files of your presentation.

You need [npm](https://www.npmjs.com/) to install the required dependencies, then run `npm install`. Finally, run `npm start` and your presentation will be visible on [http://localhost:8080](http://localhost:8080).

## Special Thanks

The original idea comes from my old colleague [Sylvain Cau](https://github.com/AshDevFr).
Thank you mate!
