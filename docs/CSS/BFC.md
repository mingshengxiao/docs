- BFC定义

BFC: 块级格式化上下文，是用于布局块级盒子的一块独立的渲染区域。让处于 BFC 内部的元素与外部的元素相互隔离，使内外元素的定位不会相互影响。

> BFC 是 Web 页面 CSS 视觉渲染的一部分，用于决定块盒子的布局及浮动相互影响范围的一个区域。  MDN - 块格式化上下文

- 触发BFC的方式:

1. 根元素，即HTML元素
2. 浮动元素，即float为left、right
3. overflow不是visible，即值为auto、scroll、hidden的元素
4. display不是inline-block、table-cell、table-caption、table、inline-table、flex、inline-flex、grid、inline-grid
5. 定位元素: position为absolute、fixed
6. contain为layout、content、paint的元素

- BFC布局规则:

1. 浮动的元素会被父级计算高度(父级元素触发了BFC)
2. 非浮动元素不会覆盖浮动元素的位置(非浮动元素触发了BFC)
3. margin不会传递给父级(父级触发BFC)
4. 属于同一个BFC的两个相邻元素上下margin会重叠

- 开发中应用:

1. 阻止margin重叠
2. 可以包含浮动元素 —— 清除内部浮动(清除浮动的原理是两个 div都位于同一个 BFC 区域之中)
3. 自适应两栏布局
4. 可以阻止元素被浮动元素覆盖