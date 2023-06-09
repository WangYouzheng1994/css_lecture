### CSS元素的定位

* 元素开启定位后，元素层级就会更高。
* 同时开启定位，后编码css的层级会更高。
* 调整方向的四个参数

```css
div {
    /*距离顶*/
    top: 10px;
    /*距离左边*/
    left: 10px;
    right: 10px;
    bottom: 10px;
}
```

* 左右同时写，left生效，与谁先编码无关。
* 上下同时写，top生效，与谁先编码无关。
* 开启定位后，元素会变成定位元素，可以设置宽和高，并且宽和高默认是由内容撑开的。
* 定位的计算是从margin 外边框开始算的~

1. 相对定位

* 定位不脱离文档流
* 相对的位置是他原来的位置。
* 左右同时写，left生效，与谁先编码无关。
* 可以开启浮动。
* 不改变显示模式display 相对定位的作用：

* 位置微调
* 与绝对定位配合

```css
div {
    position: relative;
}
```

2. 绝对定位

* 开启后，脱离文档流
* 定位的位置参考是他的包含块：

> 包含块的概念：
> 1. 没脱离文档流的元素，他的包含块是他的父元素。
> 2. 脱离文档流的元素，他的包含块是他的第一个开启定位的祖先元素，如果祖先元素都没开启定位，那么就会找到html元素，因此~往往最后找到了html~

* 基于以上包含块的概念，因此绝对定位会和相对定位配合使用，即：父亲开启相对定位，孩子使用绝对定位~
* 如果定位中使用了top，那么可以和margin-top用，如果用了left定位，margin-left一起用，以此类推~但不推荐这么搞~
* 绝对定位不可以使用浮动，不生效。
* 使用绝对定位后，元素的类型变成了“定位元素”，html中显示的是span，但是他却支持设置宽和高（行内元素不支持设置宽和高，全靠内容撑出来）~~

- 绝对定位，尽可能不要使用margin。

```css
div {
    position: absolute;
}
```

3. 固定定位

* 元素会脱离文档流。
* left、right、top、bottom 直接就会相对于“视口”，就是页面的边缘~
* 牢记视口和html定位的区别，当页面出现了滚动，固定定位会跟着滚动的~
* 如果定位中使用了top，那么可以和margin-top用，如果用了left定位，margin-left一起用，以此类推~但不推荐这么搞~
* 浮动会失效
* 元素会变成定位元素，及时是span（行内元素），也可以进行宽高设置了哈

```css
div {
    position: fixed;
}
```

4. 粘性定位

* 不脱离文档流
* 核心就是为了实现一个 滚动条滚动然后把元素粘住。以前都是用js实现的
* 要粘谁 就给谁设置，什么时候不粘了？ 他所在的父容器下边缘脱离视口以后。

```css
.first {
    background-color: cornflowerblue;
    /*  设置粘性定位  */
    position: sticky;
    /* 设置什么时候 开始粘上 */
    top: 0px
}

```

* 他相对的是离他最近的一个可滚动的祖先元素。默认是视口，如果父容器是能滚动的比如overflow:auto，那么就不是视口了哈

```css
.item2 {
    height: 300px;
    overflow: auto;
}
```

* 支持top，还有right，她完全是靠滚动条来的~
* 支持浮动，不推荐
* 支持margin，不推荐

### 定位的层级

* 定位后 层级会上升。
* 如果父元素设置了z-index，那么孩子元素的z-index 会受到父元素的z-index的影响

### 定位的特殊应用：绝对定位absolute和固定fixed定位

* 浮动后，进行水平、垂直居中 方案1：

```css
.inner {
    background-color: orange;
    font-size: 20px;
    padding: 20px;
    border: 10px solid black;
    /*开启定位以后，宽和高是由内容撑开的*/
    position: absolute;
    /*子元素会超出父元素，width设置的是content的宽和高，那超出的部分是，border和padding
    width: 100%*/

    /*  特殊应用1：填满父元素  */
    /*左边贴死*/
    left: 0;
    /*右边也贴死*/
    right: 0;
    /*上下填满父元素*/
    top: 0;
    bottom: 0;
    margin: auto;
}
```

方案2：

```css
.inner {
    width: 400px;
    height: 100px;
    background-color: orange;
    font-size: 20px;
    padding: 20px;
    border: 10px solid black;
    /*开启定位以后，宽和高是由内容撑开的*/
    position: absolute;
    /*子元素会超出父元素，width设置的是content的宽和高，那超出的部分是，border和padding
    width: 100%*/

    /*  特殊应用2：水平垂直居中于父元素  */
    /*左边贴死*/
    left: 0;
    /*右边也贴死*/
    right: 0;
    /*上下填满父元素*/
    top: 0;
    bottom: 0;
    /*定位会计算margin，他会自动调整margin的大小*/
    margin: auto;
}
```

### 定位的特殊应用：让定位元素填充包含块的宽和高

* 让宽度一致，设置left和right都为0
* 让高度一致，设置top和bottom都为0

```css
.outter {
    height: 400px;
    background-color: #888;
    /*  配合子元素的absolute，relative  */
    position: relative;
}

.inner {
    background-color: orange;
    font-size: 20px;
    padding: 20px;
    border: 10px solid black;
    /*开启定位以后，宽和高是由内容撑开的*/
    position: absolute;
    margin: 0px;
    /*子元素会超出父元素，width设置的是content的宽和高，那超出的部分是，border和padding
    width: 100%*/

    /*  特殊应用1：填满父元素  */
    /*左边贴死*/
    left: 0;
    /*右边也贴死*/
    right: 0;
    /*上下填满父元素*/
    top: 0;
    bottom: 0;
}
```