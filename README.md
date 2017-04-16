# links.less

[![npm version](https://badge.fury.io/js/links.less.svg)](https://badge.fury.io/js/links.less) [![bower version](https://badge.fury.io/bo/links.less.svg)](https://badge.fury.io/bo/links.less)

Configurable css module for rendering links.

## Install

`npm install links.less --save-dev`

`bower install links.less --save`

or use compiled version from CDN

`https://unpkg.com/links.less@0.0.2/links.css`  
`https://unpkg.com/links.less@0.0.2/links.min.css`  
`https://unpkg.com/links.less@0.0.2/links.min.css.map`

## Default settings

```less
.links-settings() {
    @links-class: link; //you can rename that classname
    @links-text-decoration: underline;
    @links-roundness: 0.125em;   // default = 2px
    @links-focuswidth: 0.1875em; // default = 3px
    //colors
    @links-link:          #0877db;
    @links-visited:       #9108db;
    @links-hover:         #2b9aff;
    @links-visitedhover:  #bc4df8;
    @links-active:        #bc4df8;
    //animation
    @links-aniduration: .3s; //fading duration from hover
}
```

## Usage in LESS

Running with default parameters:

```less
@import (less) "node_modules/links.less/links.less";
```

Rewrite basic parameters:

```less
@import (less) "node_modules/links.less/links.less";

.links-settings() {
    @links-class: pseudolink; //you can rename that classname
    @links-text-decoration: none;
    @links-roundness: 0;
    @links-focuswidth: 3px;
    @links-aniduration: .5s;
}
```
