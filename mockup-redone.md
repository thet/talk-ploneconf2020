<!-- .slide: data-background="lime" -->
# $ whoami


<!-- .slide: data-background="lime" -->
- Johannes Raggam
- Graz / Austria


<!-- .slide: data-background="lime" -->
<img alt="Syslab Logo" title="Syslab.com" style="width: 60%; height: auto" src="./resources/logos/Logo_SYSLAB_ohneClaim_white_1c.svg" />


<!-- .slide: data-background="lime" -->
- Plone Foundation Member
- Former Plone Framework Team Member
- BlueDynamics Alliance Member
- Buschenschanksprint Organizer


<!-- .slide: data-background="lime" -->
- [https://github.com/thet](https://github.com/thet)
- [https://twitter.com/thetetet](https://twitter.com/thetetet)


<!-- .slide: data-background="lime" -->
<!-- - [https://thet.github.io/talk-ploneconf2020](https://thet.github.io/talk-ploneconf2020) -->

- [https://github.com/thet/talk-ploneconf2020](https://github.com/thet/talk-ploneconf2020)




<!-- .slide: data-background="yellow" -->
# Overview


<!-- .slide: data-background="yellow" -->

History

The new Mockup <!-- .element: class="fragment" -->

Patternslib Showcase <!-- .element: class="fragment" -->

The new Resource Registry <!-- .element: class="fragment" -->

Outlook <!-- .element: class="fragment" -->




<!-- .slide: data-background="DeepPink" -->
# History


<!-- .slide: data-background="DeepPink" -->
## Mockup


<!-- .slide: class="full" data-background="DeepPink" -->

<video controls src="./resources/screencasts/mockup-history-gitg-5-edit.webm" />


<!-- .slide: class="full" data-background="DeepPink" -->

<video controls src="./resources/screencasts/syslab-rok.webm" />


<!-- .slide: class="full" data-background="DeepPink" -->

<video controls src="./resources/screencasts/mockup-history-plone-release.webm" />


<!-- .slide: class="full" data-background="DeepPink" -->

<video controls src="./resources/screencasts/mockup-resourceregistry-plone4-edit.webm" />




<!-- .slide: data-background="Cyan" -->
# The new Mockup /1


<!-- .slide: data-background="Cyan" -->

- Described in [PLIP 3211](https://github.com/plone/Products.CMFPlone/issues/3211)


<!-- .slide: data-background="Cyan" -->

## Based on latest Patternslib


<!-- .slide: data-background="Cyan" -->

- Well maintained

- Used in many industry projects

- Web Component like library


<!-- .slide: data-background="Cyan" -->

- [https://patternslib.com/](https://patternslib.com/)

- [https://github.com/patternslib/Patterns](https://github.com/patternslib/Patterns)




<!-- .slide: data-background="Yellow" -->
# Patternslib showcase


<!-- .slide: data-background="Yellow" -->

- [https://patternslib.com/](https://patternslib.com/)

- [https://github.com/patternslib/Patterns](https://github.com/patternslib/Patterns)


<!-- .slide: class="full" data-background="Yellow" -->

<video controls src="./resources/screencasts/pat-patterns.webm" />


<!-- .slide: data-background="Yellow" -->

```html [|2]
<input
    class="pat-date-picker"
    type="date" />
```


<!-- .slide: class="full" data-background="Yellow" -->

<video controls src="./resources/screencasts/pat-date-picker.webm" />


<!-- .slide: data-background="Yellow" -->

```html [|2]
<form
    class="pat-autosubmit"
    action="./@@test-action"
    method="POST">
</form>
```


<!-- .slide: class="full" data-background="Yellow" -->

<video controls src="./resources/screencasts/pat-auto-submit.webm" />


<!-- .slide: data-background="Yellow" -->

```html
<div
    class="pat-tiptap"
    data-pat-tiptap="collaboration-server: wss://demos.yjs.dev;
                     collaboration-document: patternslib-demo">
</div>
```


<!-- .slide: class="full" data-background="Yellow" -->

<video controls src="./resources/screencasts/pat-tiptap.webm" />




<!-- .slide: data-background="Cyan" -->
# The new Mockup /2


<!-- .slide: data-background="Cyan" -->

## Modernized Code Base


<!-- .slide: data-background="Cyan" -->

- ES6+ syntax and features

- ES6 module system

- Dynamic imports

- Modern Toolchain: Webpack, Babel, Jest, ...


<!-- .slide: data-background="Cyan" -->

## ES6+ Syntax


<!-- .slide: data-background="Cyan" -->

- Default parameters

- Variable scope ``let``, ``const``

- ``async`` / ``await``

- Arrow functions ``() => {}``

- Parameter destructuring, spread syntax, template literals, Optional chaining, ...


<!-- .slide: data-background="Cyan" -->

## ES6 module system


<!-- .slide: data-background="Cyan" -->

- Old - RequireJS:

```js
define([
    "pat-base",
    "pat-parser"
], function(Base, Parser) {

});
```


<!-- .slide: data-background="Cyan" -->

- New - ES6 imports/exports

```js
import Base from "../../core/base";
import Parser from "../../core/parser";

export default Base.extend({

});
```


<!-- .slide: data-background="Cyan" -->

- RequireJS is abandoned

- RequireJS incompatible with modern JS

- No RequireJS dependency paths


<!-- .slide: data-background="Cyan" -->

## Dynamic Imports


<!-- .slide: data-background="Cyan" -->

- Normal imports:

```js
import Base from "../../core/base";
import Masonry from "masonry-layout";
import ImagesLoaded from "imagesloaded";

export default Base.extend({
    name: "masonry",
    trigger: ".pat-masonry",

    init($el, opts) {
        // ...
    },
});
```


<!-- .slide: data-background="Cyan" -->

- Dynamic imports:

```js
import "regenerator-runtime/runtime"; // needed for ``await`` support
import Base from "../../core/base";

export default Base.extend({
    name: "masonry",
    trigger: ".pat-masonry",

    async init($el, opts) {
        Masonry = await import("masonry-layout");
        Masonry = Masonry.default;
        ImagesLoaded = await import("imagesloaded");
        ImagesLoaded = ImagesLoaded.default;

        // ...
    },
});
```


<!-- .slide: data-background="Cyan" -->

- Webpack can "split chunks" from the bundle

- Dynamic imported libs are seperate files

- Can massively reduce the bundle size


<!-- .slide: data-background="Cyan" -->

Without dynamic imports

```Bash [4]
ploneintranet.prototype 5.1.0
Patternslib 3
3.5 MB bundle.js
1.5 MB bundle.min.js
0.7 MB chunks
```

With dynamic imports

```Bash [4]
ploneintranet.prototype master
Patternslib 4
1.1 MB bundle.js
0.4 MB bundle.min.js
4.2 MB chunks
```


<!-- .slide: data-background="Cyan" -->

Bundle insight

```Bash
$ yarn build:stats
$ npx webpack-bundle-analyzer stats.json
```


<!-- .slide: data-background="Cyan" data-background-image="./resources/imgs/patternslib-bundle-analyzation.png" -->


<!-- .slide: data-background="Cyan" -->

## Testing


<!-- .slide: data-background="Cyan" -->

- [Jest](https://jestjs.io/)

- [jsDOM](https://github.com/jsdom/jsdom/)


<!-- .slide: class="full" data-background="Yellow" -->

<video controls src="./resources/screencasts/patternslib-jest.webm" />


<!-- .slide: data-background="Cyan" -->

## Bundling


<!-- .slide: data-background="Cyan" -->

- Webpack.

- No more Grunt.

- No need to query the resource registry.

- No RequireJS dependency definitions.


<!-- .slide: data-background="Cyan" -->

- Bundle analyzation tools

- Code splitting

- Tree Shaking

- Module Federation (more on that later)


<!-- .slide: data-background="Cyan" -->

## Documentation


<!-- .slide: data-background="Cyan" -->

- Remove own React 0.10 based documentation generator

- Use 11ty


<!-- .slide: data-background="Cyan" -->

- Compatible to Jekyll

- Markdown docs

- Interactable live examples


<!-- .slide: data-background="Cyan" -->

## Even more:

- Babel transpiling

- Yarn package management

- ESLint

- Prettier




<!-- .slide: data-background="DeepSkyBlue" -->
# The new Resource Registry


<!-- .slide: data-background="DeepSkyBlue" -->

- Described in [PLIP 3211](https://github.com/plone/Products.CMFPlone/issues/3211)


<!-- .slide: data-background="DeepSkyBlue" -->

## Simplification


<!-- .slide: data-background="DeepSkyBlue" -->

- Only bundles

- No more resources and "resource bundles"


<!-- .slide: data-background="DeepSkyBlue" -->

- Bundling standard tools (default: Webpack)

- No more TTW bundling

Note:
You can use the bundler of your choice.
As genious as it was, TTW bundling via rjs and less.js are not possible anymore.
This feature will be removed


<!-- .slide: data-background="DeepSkyBlue" -->

## Cache Busting Improvements


<!-- .slide: data-background="DeepSkyBlue" -->

- Resource refresh at restart

- Button to refresh resources

Note:
As it was in Plone 4, a restart should automatically invalidate the caches and generate new caching URLs for all bundles.




<!-- .slide: data-background="Blue" -->
# Outlook


<!-- .slide: data-background="Blue" -->

## Current status


<!-- .slide: data-background="Blue" -->

- Code restructuring done.

- Webpack, Babel, Jest configured.

- Some patterns ported.

- Some tests pass.


<!-- .slide: class="full" data-background="Blue" -->

<video controls src="./resources/screencasts/mockup-es6-jest.webm" />


<!-- .slide: class="full" data-background="Blue" -->

<video controls src="./resources/screencasts/mockup-es6-11ty.webm" />


<!-- .slide: data-background="Blue" -->

## Finalizing at upcoming sprints


<!-- .slide: data-background="Blue" -->

- Prefer patterns from patternslib.

- Port the rest to ES6.

- Make tests pass.


<!-- .slide: data-background="Blue" -->

## Playwright testing


<!-- .slide: data-background="Blue" -->

- Browser automation

- Like Cypress, Selenium, Robot

- Based on async/await


<!-- .slide: data-background="Blue" -->

## Webpack Module Federation


<!-- .slide: data-background="Blue" -->

- Webpack 5

- Depend on code modules defined other bundles

- Possible solution for adding JS via addons without code duplication




<!-- .slide: data-background="Black" -->




<!-- .slide: data-background="Purple" data-background-image="./resources/imgs/thats_all_folks.svg" -->

