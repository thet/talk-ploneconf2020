<!-- .slide: data-background="lime" -->
# $ whoami


<!-- .slide: data-background="lime" -->
- Johannes Raggam
- Graz / Austria


<!-- .slide: data-background="lime" -->
<img alt="Syslab Logo" title="Syslab.com" style="width: 60%; height: auto" src="./resources/imgs/Logo_SYSLAB_ohneClaim_white_1c.svg" />


<!-- .slide: data-background="lime" -->
<img alt="programmatic Logo" title="programmatic.pro" class="antiantialias" style="width: 60%; height: auto" src="./resources/imgs/programmatic-logo-w-200.png" />


<!-- .slide: data-background="lime" -->
<img alt="BlueDynamics Logo" title="bluedynamics.com" style="width: 60%; height: auto" src="./resources/imgs/bdan-logo4.svg" />


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



