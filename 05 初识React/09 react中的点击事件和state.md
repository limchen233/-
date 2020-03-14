## react 中的按钮点击事件

1、事件的名称都是React的提供的，因此名称的首字母必须大写`onClick`、`onMouseOver`

2、为事件提供的处理函数，必须是如下格式

    onClick= { function } //注意： = 号后面不是双引号，而是{}
    <button onClick={function(){console.log('ok)}}>按钮</button>

![](https://i.imgur.com/tswh4hx.png)