首先我们要知道 **jsx 语法的本质：**并不是直接把 jsx 渲染到页面上，而是内部先转换成了 createElement 形式再渲染的；

**在 jsx 中混合写入 js 表达式**：在 jsx 语法中，要把 JS 代码写到 `{ }` 中

   + 渲染数字
   + 渲染字符串
   + 渲染布尔值
   + 为属性绑定值
   + 渲染jsx元素

**在 jsx 语法中，标签必须成对出现，如果是单标签，则必须自闭和！**

> 当 编译引擎，在编译 JSX 代码的时候，如果遇到了`<`那么就把它当作 HTML 代码去编译，如果遇到了 `{}` 就把花括号内部的代码当作普通 JS 代码去编译；

![](https://i.imgur.com/10vSY4B.png)

![](https://i.imgur.com/DCSbJ6O.png)

![](https://i.imgur.com/VDULDge.png)