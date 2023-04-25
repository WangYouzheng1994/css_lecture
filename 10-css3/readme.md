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
* background-origin 设置背景图片的起始位置
    * padding-box 默认，从padding作为顶点开始铺
    * border-box 从border开始
    * content-box 从content开始
    * background-clip
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

- background的复合属性
```css
div {
  
}

```
### CSS3-边框属性