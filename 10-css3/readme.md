### CSS3

* 新增了样式
* 如何判定浏览器是否支持哪个样式。https://caniuse.com/
* 常见浏览器前缀 edge, chrome, safari 为 -webkit-。 火狐 -moz-

### CSS3-长度属性

* rem 跟元素字体大小的倍数 即：font-size的倍数，相对于html节点，从头一层一层往下找
* vw(viewport width) 相对于视口宽度的百分比。 他可以跟着视图大小进行变化~
* vh(viewport height)相对于视口高度的百分比。 他可以跟着视图大小进行变化~
* vmax(viewport 宽和高的最大值)的百分比。
* vmin(viewport 宽和高的最小值)的百分比。

### CSS3-盒子属性

* box-sizing
    * content-box 默认：表示width和height设置的是内容区，如果有padding和border那么这个盒子会更大
    * border-box 表示width和height设置的已经包含了border和padding.比较默认的content-box会把内容区变小~
* resize
    * none 默认，不支持拖动
    * horizontal 水平支持拖动，过窄会屏蔽掉数据，配合`overflow:auto` 会在过窄的时候出现滚动条
    * vertical 垂直方向支持拖动
    * both 水平和垂直都支持拖动
* box-shadow **（常用）**盒子阴影

```css
div {
    /*默认值 没有任何阴影*/
    box-shadow: none;
    /*偏右边水平的影子10px，偏下的垂直影子15px*/
    box-shadow: 10px 15px;
    /*偏右边水平的影子10px，偏下的垂直影子15px，影子是红色*/
    box-shadow: 10px 15px red;
    /*偏右边水平的影子10px，偏下的垂直影子15px，影子会进行发散模糊10px，数越大发散的越远，越模糊*/
    box-shadow: 10px 15px 10px;
    /*偏右边水平的影子10px，偏下的垂直影子15px，影子会进行发散模糊10px，数越大发散的越远，越模糊 影子是红色*/
    box-shadow: 10px 15px 10px red;
    /*偏右边水平的影子10px；偏下的垂直影子15px；影子会进行发散模糊10px，数越大发散的越远，越模糊；影子的四周外延20px，越大影子越大 影子是红色*/
    box-shadow: 10px 15px 10px 20px red;
    /* 内阴影，简单点看的话就是对角线对齐*/
    box-shadow: 10px 15px 10px 20px red inset;
}
```

* opacity 设置透明度，值范围：0~1

### CSS3-背景属性

* background-repeat 设置图片铺不满是否重复铺满
* background-position： 设置宽和高的起始点
* background-origin 设置背景图片的起始位置
    * padding-box 默认，从padding作为顶点开始铺
    * border-box 从border开始
    * content-box 从content开始
    * background-clip 裁剪方式
        * border-box 从边框区域开始向外裁剪
        * padding-box 从内边距区域开始向外裁剪，也就是border-box区域的都不要了
        * content-box 从内容区域保留，border和padding的都不要了
        * text 背景图只呈现在文字上面
            * 具体代码如下：

```css
div {
    font-size: 50px;
    font-weight: bold;
    /*设置为透明的*/
    color: transparent;
    /*是还没正式支持的参数*/
    -webkit-background-clip: text;
}
```

* background-size **高频使用**
    * background-size 背景大小
        * 长和宽：百分比，不允许负值；长度px，不允许负值
        * auto 默认，左上角对齐，不进行任何缩放，超出的地方直接切掉
        * contain 左上角对齐，优先按照图片的宽和高长的那个线进行，等 比 例，缩放。
        * cover 左上角对齐，保留等比例进行缩放，多余的地方直接切掉了。比较好的选择了。

- background的复合属性写法: 原点position必须在size前面，并且用/ 分割

```css
div {
    width: 400px;
    height: 500px;
    /* 背景颜色，背景url 是否重复；距离原点偏离位置x, y；/ 大小x y  原点选择content-box 裁剪方式 content-box */
    background: skyblue url("readme.md") no-repeat 0px 0px / 500px 500px content-box;
}
```

* 设置多背景图；尝尝应用于四个角的图片

```css
div {
    width: 400px;
    height: 500px;
    border: 1px solid black;
    background: url('1-lt.jpg') no-repeat left top,
    url('1-rt.jpg') no-repeat right top,
    url('1-lb.jpg') no-repeat left bottom,
    url('1-rb.jpg') no-repeat right bottom;
}
```

### CSS3-边框属性

* border-radius 边框圆角

```css
div {
    width: 400px;
    height: 400px;
    /*半径200px，radiu就是200px到头了，可以认为这就是半径*/
    border-radius: 200px;
    /*这样就是个椭圆*/
    border-radius: 200px 100px;
    /*左上角是个椭圆 x : 200px, y: 100px*/
    border-top-left-radius: 200px 100px;

    /*复合属性： 顺时针*/
    /*border-radius: 左上，右上，右下，左下;*/
}
```

* outline-width 边框外框 不参与计算盒子大小，在margin外面的一个框，不占位

```css
div {
    width: 400px;
    height: 400px;
    border: 1px solid black;
    background-color: gray;
    font-size: 40px;
    margin: 0 auto;
    margin-top: 100px;

    /*外框宽度*/
    outline-width: 20px;
    /*外框颜色*/
    outline-color: orange;
    /*外框线类型： 虚线doshed 实线solid*/
    outline-style: solid;
    /*外框线，偏移，支持正负值*/
    outline-offset: 0px;

    /*  复合属性 跨度，实线，颜色。 不支持偏移offset */
    outline: 20px solid orange;
}
```

### font文字属性

* 文本阴影 text-shadow

```css
h1 {
    font-size: 80px;
    text-align: center;
    /*默认，没有阴影*/
    text-shadow: none;

    /*偏右边水平的影子3px，偏下的垂直影子3px 阴影颜色红色*/
    text-shadow: 3px 3px red;

    /*偏右边水平的影子3px，偏下的垂直影子3px 模糊5px 阴影颜色红色*/
    text-shadow: 3px 3px 5px red;
}
```

* 文本换行 white-space

```css
div {
    width: 400px;
    height: 400px;
    border: 1px solid black;
    font-size: 20px;

    /*默认值：文本超出边界会自动换行，编码中的换行会被识别为空格*/
    white-space: normal;
    /*根据编码的空格进行空格，根据换行而换行。即：按照编码显示, 容器超出也会超出*/
    white-space: pre;
    /*根据编码的空格进行空格，根据换行而换行。即：按照编码显示, 容器超出会换行*/
    white-space: pre-wrap;
    /*编码格式中的，文字的前后的空格会忽略，根据换行而换行。即：按照编码显示, 容器超出会换行*/
    white-space: pre-line;
    /*并成一行，不换行，会超出容器~*/
    white-space: nowrap;
}
```

* 文本溢出 text-overflow 文本溢出往往和文本换行配合使用

```css
li {
    margin-bottom: 40px;
    /*不换行*/
    white-space: nowrap;


    /*截掉*/
    text-overflow: clip;
    /*超出部分变成了三个点~*/
    text-overflow: ellipsis;
    /*进行配合*/
    overflow: hidden /overflow/ auto;
}
```

* 文本修饰 text-decoration

```css
h1 {
    font-size: 100px;
    /*线位置 none默认值无，underline下划线，overline上划线，line-though贯穿线*/
    text-decoration-line: overline;
    /*线类型solid实线 double双线 dotted点状 dashed虚线 wavy波浪*/
    text-decoration-style: dashed;
    /*线颜色*/
    text-decoration-color: red;

    /*复合属性*/
    text-decoration: overline wavy blue;
}
```

* 文本描边 text-stroke-color  
  此属性是测试属性

```css
h1 {
    font-size: 20px;
    /*描边宽度*/
    -webkit-text-stroke-width: 5px;
    /*描边颜色*/
    -webkit-text-stroke-color: red;

    /*  复合写法*/
    -webkit-text-stroke: 5px red;
}
```

### 渐变 
可以实现立体的效果~
* 线性渐变 linear-gradient
```css
div {
    height: 400px;
    weight: 400px;
    border: 1px solid black;
    /*从上到下 红黄绿*/
    background-image: linear-gradient(red, yellow, green);
    /*设置渐变方向为： 从左下到右上，红黄绿*/
    background-image: linear-gradient(to right, red, yellow, green);
    /*设置渐变的角度 从左下到右上,30度，红黄绿*/
    background-image: linear-gradient(30deg, red, yellow, green);
    /*设置每个渐变的宽度，红50， 黄100， 绿150*/
    background-image: linear-gradient(red 50px, yellow 100px, green 150px);
    /*文字渐变
    background-image: linear-gradient(red 50px, yellow 100px, green 150px);
    -webkit-background-clip: text;
    color: transparent; 设置成透明的*/
}
```
* 径向（中心）渐变 radial-gradient
```css
div {
    height: 400px;
    weight: 400px;
    border: 1px solid black;

    /*中心渐变 红黄绿*/
    background-image: radial-gradient(red, yellow, green);
    /*设置渐变的圆心方向为： 右上角，红黄绿*/
    background-image: radial-gradient(at right top, red, yellow, green);
    /*设置渐变的圆心定位为100px 50px 从左下到右上,30度，红黄绿*/
    background-image: radial-gradient(at 100px 50px, red, yellow, green);
    /*设置为正圆渐变，红黄绿*/
    background-image: radial-gradient(circle, red, yellow, green);
    /*设置圆的半径，可以影响椭圆或者正圆，以及渐变范围*/
    background-image: radial-gradient(100px 50px, red,yellow, green);
    /*设置每个花色的半径*/
    background-image: radial-gradient(100px 100px, red 50px,yellow 50px, green 50px);
    /*这是圆心位置加渲染范围*/
    background-image: radial-gradient(100px 100px at 50px 100px , red 50px,yellow 50px, green 50px);

}
```
* 重复渐变 针对的是调整了每个花色的区域，如果达到了区域就会轮循。
```css
div {
    /*这是圆心位置加渲染范围*/
    background-image: repeating-radial-gradient(100px 100px at 50px 100px , red 50px,yellow 50px, green 50px);
}

```

### 字体

### 2D

### 3D

### 过度

### 动画

### 多列布局
