#CSS Notebook

This is a notebook that I want to keep various code snippet for my own learning purpose so that I know where to find it if I want to use it later.

###Clearfix
**usage**: Clearfix is use when you use float on an element or elements and you want its wrapper box to wrap around it or them.
**how to use**: add a class called "group" to the wrapper of floating element.
```css
.group:before,
.group:after {
    content: "";
    display: table;
} 
.group:after {
    clear: both;
}
.group {
    zoom: 1; /* For IE 6/7 (trigger hasLayout) */
}
```

###Box-Sizing
```css
* {
  box-sizing: border-box;
}
```