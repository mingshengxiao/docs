- Babel是什么

Babel是JavaScript编译器。

- Babel作用

Babel只是转译新标准引入的语法，如箭头函数、let/const、解构。对于新标准引入的全局变量、部分原生对象新增的原型链上的方法等不做处理。

- Babel编译过程

Babel编译分为三个过程，包括:

**解析(Parsing)**:将代码字符串解析成抽象语法树    
**转换(Transformation)**:对抽象语法树进行转换操作   
**生成(Code Generation)**:根据变换后的抽象语法树再生成代码字符串