### CSS3弹性盒模型 flex

1. 伸缩容器

* 当父节点设置了`display: flex`，直接孩子节点也会变成弹性盒子
* 两个兄弟 父伸缩容器的排列方式还是上下，毕竟还是div

2. 主轴

* 主轴默认是从左到右，侧轴是垂直于主轴的，并且如果要改侧轴一定是只能改主轴
* 主轴修改说明：

```css
div.outer {
    display: flex;
    /*主轴，横向，从左到右。 默认*/
    flex-direction: row;
    /*主轴，横向，从右到左。*/
    flex-direction: row-reverse;
    /*主轴，纵向，从上到下*/
    flex-direction: column;
    /*主轴，纵向，从下到上*/
    flex-direction: column;
}
```

* 直接孩子元素是按照主轴的方向进行排列的

3. 主轴换行方式 flex-wrap

```css
.outter {
    width: 800px;
    height: 600px;
    background-color: blue;
    border: 1px solid black;
    display: flex;
    /*默认值，如果主轴撑不下了，就压缩孩子*/
    /*flex-wrap: nowrap;*/
    /*主轴放不下了 就往交叉轴换行*/
    /*flex-wrap: wrap;*/
    /*变换主轴的排列方向，默认都是 从左到右，从上到下，一单翻转那么 左到右变成右到左*/
    flex-wrap: wrap-reverse;
}

.inner {
    width: 200px;
    height: 50px;
    background-color: red;
    border: 1px solid black;

}
```

4. 主轴上元素的对齐方式 justify-content

```css
.outter2 {
    /*主轴对齐方式*/

    /*主轴开始的位置开始对齐，默认值 */
    /*justify-content: flex-start;*/
    /*主轴结束的位置开始对齐 */
    /*justify-content: flex-end;*/
    /*主轴居中*/
    /*justify-content: center;*/
    /*主轴对齐：项目均匀分布，两边一倍，项目中间两倍的比例，如果没有位置了就不分割了~*/
    justify-content: space-around;
    /*主轴对齐：项目两边紧贴开始和结束，中间等比分割空格*/
    justify-content: space-between;
    /*主轴对齐：项目均匀分布在一行中，铺不满的时候，均匀用空格分割，所以会居中*/
    justify-content: space-evenly;
}
```

5. 侧轴
* 单行情况
```css
.outter {
    width: 1200px;
    height: 800px;
    border: 1px solid black;
    background-color: gray;
    /*水平居中*/
    margin: 0 auto;
    /*弹性容器*/
    display: flex;
    flex-wrap: wrap;

    /*侧轴对齐：起点对齐*/
    align-items: flex-start;
    /*侧轴对齐：终点对齐*/
    align-items: flex-end;
    /*侧轴对齐：中间对齐*/
    align-items: center;
    /*侧轴对齐：基线对齐，跟着字体大小决定的。。用的很少*/
    align-items: baseline;
    /*垂直填充满整个父容器，要求子元素不能设定height*/
    align-items: stretch;
}

.inner {
    width: 200px;
    /*height: 100px; strctch 不可以有高度*/
    background-color: green;
    border: 1px solid black;
    box-sizing: border-box;
}
```