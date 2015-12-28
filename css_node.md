#CSS Note

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
**usage**: Use this if you want to make your browser calculate padding as part of it height and width. 

**how to use**: Put this style at the top of your CSS file.
```css
* {
  box-sizing: border-box;
}
```