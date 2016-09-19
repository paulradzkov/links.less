# links.less

Configurable css module for rendering links.

## Install

`npm install links.less --save-dev`

`bower install links.less --save`

or use compiled version from CDN

`https://unpkg.com/links.less@latest/links.css`  
`https://unpkg.com/links.less@latest/links.min.css`  
`https://unpkg.com/links.less@latest/links.min.css.map`

## Default settings

```less
.links-settings() {
    @class: link; //you can rename that classname
    @text-decoration: underline;
    @roundness: 0.125em;   // default = 2px
    @focuswidth: 0.1875em; // default = 3px
    //colors
    @link:          #0877db;
    @visited:       #9108db;
    @hover:         #2b9aff;
    @visitedhover:  #bc4df8;
    @active:        #bc4df8;
    //animation
    @aniduration: .3s; //fading duration from hover
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
    @class: pseudolink; //you can rename that classname
    @text-decoration: none;
    @roundness: 0;
    @focuswidth: 3px;
    @aniduration: .5s;
}
```
