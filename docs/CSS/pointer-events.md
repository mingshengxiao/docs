### 属性pointer-events的功能及作用

<h3>pointer-events属性指定在某些情况下，某些特定的图形元素可以成为鼠标点击的target</h3>

pointer-events属性的取值如下:
```css
/* Keyword values */
pointer-events: auto;
/*none: 元素永远不会成为鼠标事件的target。但是，当其后代元素的pointer-events属性指定其他值时，鼠标事件可以指向后代元素，在这种情况下，鼠标事件将在捕获或冒泡阶段触发父元素的事件侦听器。*/
pointer-events: none;
pointer-events: visiblePainted; /* SVG only */
pointer-events: visibleFill;    /* SVG only */
pointer-events: visibleStroke;  /* SVG only */
pointer-events: visible;        /* SVG only */
pointer-events: painted;        /* SVG only */
pointer-events: fill;           /* SVG only */
pointer-events: stroke;         /* SVG only */
pointer-events: all;            /* SVG only */

/* Global values */
pointer-events: inherit;
pointer-events: initial;
pointer-events: unset;
```

#### 引用场景

1. 仅仅是在页面显示某些元素，不希望触发这些元素上的点击事件