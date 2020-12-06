<!-- .slide: data-background="lime" -->
# $ whoami


<!-- .slide: data-background="lime" -->
- Johannes Raggam
- Graz / Austria


<!-- .slide: data-background="lime" -->
<img alt="Syslab Logo" title="Syslab.com" style="width: 60%; height: auto" src="./resources/logos/Logo_SYSLAB_ohneClaim_white_1c.svg" />


<!-- .slide: data-background="lime" -->
<img alt="programmatic Logo" title="programmatic.pro" class="antiantialias" style="width: 60%; height: auto" src="./resources/logos/programmatic-logo-w-200.png" />


<!-- .slide: data-background="lime" -->
<img alt="BlueDynamics Logo" title="bluedynamics.com" style="width: 60%; height: auto" src="./resources/logos/bdan-logo4.svg" />


<!-- .slide: data-background="lime" -->
- Plone Foundation Member
- Former Plone Framework Team Member


<!-- .slide: data-background="lime" -->
- [https://github.com/thet](https://github.com/thet)
- [https://twitter.com/thetetet](https://twitter.com/thetetet)


<!-- .slide: data-background="lime" -->
- TODO
- [https://thet.github.io/talk-ploneconf2020](https://thet.github.io/talk-ploneconf2020)
- [https://github.com/thet/talk-ploneconf2020](https://github.com/thet/talk-ploneconf2020)




<!-- .slide: data-background="yellow" -->
# Overview


<!-- .slide: data-background="yellow" -->
it's Vue.js, not Vue.

_But I'll call it Vue._ <!-- .element: class="fragment" -->




<!-- .slide: data-background="DeepPink" -->
# History lesson


<!-- .slide: data-background="DeepPink" -->
## Mockup


<!-- .slide: class="full" data-background="DeepPink" data-background-video="./resources/screencasts/mockup-history-gitg-5.webm" -->


<!-- .slide: class="full" data-background="DeepPink" data-background-video="./resources/screencasts/mockup-history-plone-release.webm" -->


<!-- .slide: class="full" data-background="DeepPink" data-background-video="./resources/screencasts/mockup-resourceregistry-plone4.webm" -->




<!-- .slide: data-background="Cyan" -->
# The new Mockup


<!-- .slide: data-background="Cyan" -->

- Described in [PLIP 3211](https://github.com/plone/Products.CMFPlone/issues/3211)


<!-- .slide: data-background="Cyan" -->

## Based on latest Patternslib

- Well maintained

- Used in many industry projects

- Web Component like library


<!-- .slide: data-background="Cyan" -->

- [https://patternslib.com/](https://patternslib.com/)

- [https://github.com/patternslib/Patterns](https://github.com/patternslib/Patterns)


<!-- .slide: data-background="Cyan" -->

## Modernized Code Base

- ES6+ syntax and features

- ES6 module system

- Dynamic imports

- Modern Toolchain: Webpack, Babel, Jest, ...


<!-- .slide: data-background="Cyan" -->

## ES6+ Syntax

- Default parameters

- Variable scope ``let``, ``const``

- ``async`` / ``await``

- Arrow functions ``() => {}``

- Parameter destructuring, spread syntax, template literals, Optional chaining, ...


<!-- .slide: data-background="Cyan" -->

## ES6 module system

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

- Normal imports:

```js
import Base from "../../core/base";
import Masonry from "masonry-layout";
import ImagesLoaded from "imagesloaded";

export default Base.extend({
    name: "masonry",
    trigger: ".pat-masonry",

    async init($el, opts) {
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




<!-- .slide: data-background="DeepSkyBlue" -->
# The new Resource Registry


<!-- .slide: data-background="DeepSkyBlue" -->
- dings




<!-- .slide: data-background="Blue" -->
# Outlook


<!-- .slide: data-background="Blue" -->
- dings




<!-- .slide: data-background="Purple" -->
# done()


<!-- .slide: data-background="Purple" -->
- dings



