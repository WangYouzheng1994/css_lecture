### 长度单位

1. 长度单位

* em font-size的倍数，相对于父节点，一层一层往上找
* rem font-size的倍数，相对于html节点，从头一层一层往下找
* 百分比，相对于父节点的百分比

```css
.child {
    /*相对于外层的宽度的150%*/
    width: 150%;
    /*相对于外层的150%*/
    font-size: 150%
}

```

em会有好多特殊情况：

1. text-indent 相对于当前的fontsize

### 元素的显示模式

- 块元素 block

1. 独占一行
2. 默认宽度撑满父元素，如果没有指定宽度，收到margin,padding,border的横向挤压
3. 默认的高度由内容撑开
4. css可以调整它的宽width和高height

- 行内元素 inline

1. 不独占，一行中容纳不下的行内元素，会自动去下一行从左到右排列
2. 默认宽度：由内容撑开
3. 默认高度：由内容撑开
4. css无法调整它的宽width和高height

- 行内块元素 inline-block

1. 不独占，一行中容纳不下的行内元素，会自动去下一行从左到右排列
2. 默认宽度：由内容撑开
3. 默认高度：由内容撑开
4. css可以调整它的宽width和高height

### 调整元素的显示模式

* display: block 块元素
* display: inline-block 行内块
* display: inline 行内元素

### 盒子模型的组成部分

1. content

* 设置的宽和高其实是这部分，这部分也是内容区

2. padding

* 背景颜色影响到padding区域

3. border

* color 可以影响到 border

4. margin

---

- 盒子的内径是 content + padding + border， 盒子的内径也就是绘制的区域。
- 盒子的外径是 margin
- 盒子的完整占地儿是：margin + border + padding + content

### padding 内边距

padding: 上下左右，紧邻content的区域

* 行内元素的padding 只有左右可用，上下是不占文档流的。就是，只能呈现，但是不会占地方。。。有点像浮层~

```css
/*复合属性 一个值，四个边距都一样*/
div {
    padding: 20px;
}

/*复合属性 两个值： 上下20px、左右40px*/
div {
    padding: 20px 40px;
}

/*复合属性 三个值： 上10px 左右20px 下30px*/
div {
    padding: 10px 20px 30px;
}
/*复合属性 四个值：上右下左  顺时针 */

div {
    padding: 10px 20px 30px 40px;
}

```

### margin 外边距
* 在盒子的最外围区域
* inline行内元素，不收margin top、margin bottom的影响。

- 左右居中
```css
/* 上下是0  左右是auto，这样左右的margin就会一半一半*/
div {
    margin: 0 auto
}

```

### margin塌陷的问题和解决方案
margin塌陷的原因，w3c当年就这么设计的。
1. 嵌套的div，最上面的孩子div 设置了margin-top会变成父的margin-top效果
2. 嵌套的div，最下面的孩子div 设置了margin-bottom会变成父的margin-bottom效果

解决方案：
* 给父元素设置不为0的padding
* 给父元素设置宽度不为0的border
* 给父元素设置css样式`overflow:hidden`

### margin合并的现象
1. 上下紧邻的两个兄弟块元素，或者说支持margin top和margin bottom的元素。他们上下之间的间距不会出现1+1的间距效果，间距是以最大值为准。

解决方案：  
无需解决，给上面的设置下间距 或者给下面的设置上间距。

### 内容溢出的情况处理
* overflow 默认是visible，会超出content的范围，  
可选参数有：
- visible 默认显示。
- hidden  超出部分 隐藏
- scroll 无论是否溢出都会显示滚动条
- auto  如果溢出就显示滚动条，否则不显示


### 元素的隐藏
* visibility 默认是show，设置为hidden就会隐藏，但是保留占位
* display，设置为display:none, 不占位，没有大小宽高。

### 元素样式的继承
* 继承的样式，优先级是最低的
### 元素默认样式
1. 元素默认是有默认样式的：
* `<a>`：下划线，字体颜色，指向的小手
* `h1, h2, h3` 加粗，大小
* `p` 上下外边距
* `body` 默认8px外边距

--- 
### 布局
