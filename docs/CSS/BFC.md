- BFC定义

BFC: 块级格式化上下文，是用于布局块级盒子的一块渲染区域。

> BFC 是 Web 页面 CSS 视觉渲染的一部分，用于决定块盒子的布局及浮动相互影响范围的一个区域。  
— MDN - 块格式化上下文

- 触发BFC的方式:

1. 根元素，即HTML元素
2. 浮动元素，即float为left、right
3. overflow不是visible，即值为auto、scroll、hidden的元素
4. display不是inline-block、table-cell、table-caption、table、inline-table、flex、inline-flex、grid、inline-grid
5. 定位元素: position为absolute、fixed
6. contain为layout、content、paint的元素