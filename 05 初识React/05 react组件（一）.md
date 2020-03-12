## 组件的创建与使用以及传递参数
### 一、使用构造函数创建组件

    function Hello(){}

这样我们就创建了一个组件，创建好后怎么使用呢？直接以标签的形式放到页面中即可！（不需要注册，vue中组件要注册才能使用）

    ReactDom.render(
      <div>
        测试组件
        {/*直接把组件以标签的形式放到页面中*/}
        <Hello></Hello>
      </div>,document.getElementById('app')
    )

然后运行 npm run dev,结果和我们预想的有点不一样，页面报错了！

![](https://i.imgur.com/qc5sVcO.png)

组件应该返回个状态（需要个 return 语句），那么我们把 Hello 组件修改一下

    function Hello(){
      return null
    }

然后再运行，OK了，页面成功显示！

![](https://i.imgur.com/l2SXQiH.png)

现在我们在 Hello 组件里返回点东西

    function Hello(){
      return <div>这是Hello组件</div>
    }

![](https://i.imgur.com/rMt1KtU.png)

![](https://i.imgur.com/vwPumGH.png)

### 二、给组件传递参数

（1）组件创建好后，肯定要传参数的，下面就说一下怎么给组件传递参数--使用 props 传参

![](https://i.imgur.com/dtwe790.png)

> 1、首先要在组件上绑定要传递的参数
> 
> 2、给组件传递一个形参 props，此时的 props 是一个对象，里面包含了 cat 的所有属性，这时候就拿到了参数。注意，此时组件中的 props 属性是只读的，不能重新赋值。（Vue中也是）

（2）