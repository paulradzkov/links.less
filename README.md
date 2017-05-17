# links.less

[![npm version](https://badge.fury.io/js/links.less.svg)](https://badge.fury.io/js/links.less) [![bower version](https://badge.fury.io/bo/links.less.svg)](https://badge.fury.io/bo/links.less)

Configurable css module for rendering links.

## Install

`npm install links.less --save-dev`

`bower install links.less --save`

or use compiled version from CDN

`https://unpkg.com/links.less@0.0.5/links.css`  
`https://unpkg.com/links.less@0.0.5/links.min.css`  
`https://unpkg.com/links.less@0.0.5/links.min.css.map`


## Usage in HTML

See [demo on Codepen](http://codepen.io/paulradzkov/pen/JNdJqg).

Default colors apply to all links and classnames `.link`, `.link-novisited`, `.link-inherit`.

Custom `:focus` styles and animation apply only to links that has no class attribute (`a:not[class]`) and `.link`, `.link-novisited`, `.link-inherit`.

### `.link`

Use `.link` to apply styles to any tag:

```html
<a class="mytag link" href="#">customized link</span>
<span class="link" tabindex="0">pseudolink</span>
<button class="link">button</button>
```

### `.link-novisited`

Links with class `.link-novisited` never look like :visited. Good for navigation for example.

```html
<nav>
    <a class="link-novisited" href="https://www.google.com/">google</a>
    <a class="link-novisited" href="https://github.com/">github</a>
    <a class="link-novisited" href="http://codepen.io/">codepen</a>
</nav>
```

### `.link-inherit`

Links with class `.link-inherit` use same color as parent element for :link and :visited states. Good if you want to make links in footer less prominent.

```html
<footer style="color:#999">
    © <a class="link-inherit" href="http//paulradzkov.com">Paul Radzkov</a> 2017.
</footer>
```

## Usage in LESS

Install library with `npm install links.less --save-dev` and include its main file inside your project less file:

```less
@import (less) "node_modules/links.less/links.less";
```

That is enough to run library with default parameters.

To customize settings add `.links-settings()` mixin after import and redefine any parameter:

```less
@import (less) "node_modules/links.less/links.less";

.links-settings() {
    @links-class: pseudolink; //you can rename that classname
    @links-text-decoration: none;
    @links-roundness: 0;
    @links-focuswidth: 0;
    @links-aniduration: .5s;
}
```

### Default settings

All list of settings:

```less
.links-settings() {
    @links-class: link; //you can rename that classname
    @links-text-decoration: underline;
    @links-roundness: 0.125em;   // default = 2px
    @links-focuswidth: 0.1875em; // default = 3px
    //colors
    @links-link:          #0877db;
    @links-hover:         #2b9aff;
    @links-visited:       #9108db;
    @links-visitedhover:  #bc4df8;
    @links-active:        #bc4df8;
    @links-fadeout: 75%;  // amount of transparency added to underline
    //animation
    @links-aniduration: .3s; //fading duration from hover
}
```

### Using mixin for coloring your own links

You can recolor links with `.links-color()` mixin:

```less
@import (less) "node_modules/links.less/links.less";

.links-settings() {
    // your customized parameters
}

.mycustomlink {
    .links-color(red);
}
```

You can pass from 1 to 6 arguments to mixin. See the mapping scheme:

```less
.links-color(@link-color);
.links-color(@link-color, @hover-color);
.links-color(@link-color, @hover-color, @visited-color);
.links-color(@link-color, @hover-color, @visited-color, @active-color);
.links-color(@link-color, @hover-color, @visited-color, @visitedhover-color, @active-color);
.links-color(@link-color, @hover-color, @visited-color, @visitedhover-color, @active-color, @fadeout);
```

The last one `@fadeout` by default has value 75% and refers to amount of transparency added to underline.
