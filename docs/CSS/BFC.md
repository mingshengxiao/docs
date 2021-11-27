- FC

格式化上下文是决定盒子之间如何布局的环境，不同的格式化上下文如何布局盒子由自身的规则来决定。

- BFC定义

BFC: 块级格式化上下文，是用于布局块级盒子的一块独立的渲染区域。让处于 BFC 内部的元素与外部的元素相互隔离，使内外元素的定位不会相互影响。

> BFC 是 Web 页面 CSS 视觉渲染的一部分，用于决定块盒子的布局及浮动相互影响范围的一个区域。  MDN - 块格式化上下文

> 具有BFC特性的元素可以看作是隔离了的独立容器，容器里面的元素不会在布局上影响到外面的元素，并且BFC具有普通容器所没有的一些特性。

- 触发BFC的方式:

1. 根元素，即HTML元素
2. 浮动元素，即float为left、right
3. overflow不是visible，即值为auto、scroll、hidden的元素
4. display值为inline-block、table-cell、table-caption、table、inline-table、flex、inline-flex、grid、inline-grid、table-row、table-row-group、table-header-group、table-footer-group、flow-root
5. 定位元素: position为absolute、fixed
6. contain为layout、content、paint的元素
7. 多列容器（元素的column-count 或column-width (en-US)不为auto，包括 column-count为1）

- BFC布局规则:

1. 浮动的元素会被父级计算高度(父级元素触发了BFC),计算BFC的高度时，要考虑BFC所包含的所有子元素
2. 非浮动元素不会覆盖浮动元素的位置(非浮动元素触发了BFC)
3. margin不会传递给父级(父级触发BFC)
4. 属于同一个BFC的两个相邻元素上下margin会重叠,不同BFC不会发生折叠
5. 内部盒子会在垂直方向排列
6. 当元素不是BFC的子元素时，浮动元素高度不参与BFC计算（常见的盒子塌陷问题）
7. 每个盒子（块盒与行盒）的margin box的左边，与包含块border box的左边相接触(对于从左往右的格式化，否则相反)。即使存在浮动也是如此。

- 开发中应用:

1. 阻止margin重叠
2. 可以包含浮动元素 —— 清除内部浮动(清除浮动的原理是两个 div都位于同一个 BFC 区域之中)
3. 自适应两栏布局
4. 可以阻止元素被浮动元素覆盖
5. 阻止因为浏览器因为四舍五入造成的多列布局换行的情况