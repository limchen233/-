近期项目使用的`jQuery+JSP`，前端组件使用了`layui`。涉及到了排序、合计、多级表头等问题。

`layui`表格有三种渲染方式，我使用的是**方法渲染**。

##### 一、排序

为某列排序，在table渲染时，首先要开启排序，然后添加`initSort`参数，并添加要排序的字段名：

```html
<table id="layTable" lay-filter="layTable"></table>
```

```javascript
table.render({
  elem: '#layTable',
  data: tableData,
  sort:true,  // 开启排序
  initSort: {
    field: 'value',// 要排序的字段
    type: 'desc' //排序方式  asc: 升序、desc: 降序、null: 默认排序
  }
});
```

##### 二、合计

显示合计行。首先要开启合计功能，在table渲染时添加`totalRow:true`。然后在要显示`合计`两字的列添加`totalRowText:"合计"`,最后在需要合计的列添加`totalRow: true`，这样就开启了合计功能。`totalRow`属性会自动计算所在列的和。

然后我们会发现每个合计的数字后面都有`00`，例如`16.00`。我们可以通过`done`函数来去掉结尾的0。

![image-20210823141659531](https://github.com/limchen233/picgo/blob/master/img/image-20210823141659531.png?raw=true)

```javascript
//渲染表格
table.render({
  elem: '#layTable',
  data: tableData,
  totalRow:true, // 开启合计功能
  cols: [tableColumns],
  done:function(res, curr, count){// 去掉合计行小数点
    var divArr = $(".layui-table-total div.layui-table-cell");
    $.each(divArr,function (index,item) {
      var _div = $(item);
      var content = _div.html();
      content = content.replace(".00","");
      _div.html(content);
    });
  }
});
```

三、表头字数太多换行

首先给需要换行的列添加`width`属性。然后添加以下`CSS`样式：

```css
.layui-table-cell {
   padding:0 4px;
   height:auto;
   overflow:visible;
   text-overflow:inherit;
   white-space:normal;
   word-break: break-all;
   text-align: center;
}
```

效果：

![image-20210823143235938](https://github.com/limchen233/picgo/blob/master/img/image-20210823143235938.png?raw=true)

