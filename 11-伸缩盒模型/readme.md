### CSS3弹性盒模型 flex

1. 伸缩容器

* 当父节点设置了`display: flex`，直接孩子节点也会变成弹性盒子
* 两个兄弟 父伸缩容器的排列方式还是上下，毕竟还是div

---

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

---

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

---

4. 主轴上元素的对齐方式 justify-content 主轴的对齐，是能挤挤就挤挤

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

---

5. 侧轴对齐

* 单行情况 align-items
* 而且align-items会影响到每行的孩子的排列，粒度更细

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

* 多行情况 align-content

- 当容器不设置高度，没设置wrap的时候，且子项只有一行的时候是不生效的
- align-content只影响到行，不影响孩子的排列方式

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

    /*align-items: center;*/
    /*align-items: flex-end;*/

    /*侧轴对齐多行：侧轴的起始位置对齐*/
    /*align-content: flex-start;*/
    /*侧轴对齐多行：侧轴的重点位置对齐*/
    /*align-content: flex-end;*/
    /*侧轴对齐多行：垂直居中*/
    /*align-content: center;*/
    /*侧轴对齐多行：两端有空格，元素垂直之间的空格是两端的两倍*/
    /*align-content: space-around;*/
    /*侧轴对齐多行：元素中间距离相等，两端没有空格*/
    /*align-content: space-between;*/
    /*侧轴对齐多行：元素中间，以及两端的空格距离是一样的*/
    align-content: space-evenly;
    /*侧轴对齐多行，拉伸，三行会平分整个父容器的高度，因此，孩子容器不可以设置高度*/
    align-content: stretch;

}

.inner {
    width: 200px;
    height: 100px; /*strctch 不可以有高度*/
    background-color: green;
    border: 1px solid black;
    box-sizing: border-box;
}
```

* align-content和align-items总结：

1. align-items的粒度比align-content更细，他会设置到一行中的孩子的垂直对齐方式，也会影响每行之间的对齐方式
2. align-content指挥影响到每行之间的对齐方式

---

6. flex-baxis 主轴方向的基准长度

```css
.child {
    /*默认值：浏览器是根据此属性值计算主轴的剩余空间的，如果是auto，根据主轴方向来决定获取parent的width还是height*/
    flex-basis: auto;
    /*主轴如果是横向的，那么，就是指的宽度500px，否则是高度500px*/
    flex-basis: 500px;
}
```

### 伸缩盒模型的伸

* flex-grow 定义子项的放大比例，默认是0：主轴即使存在剩余空间，也不拉伸。
* 当所有伸缩项目的flex-grow都是1，那么他们成比例等分扩大，一起占用剩余空间
* 当伸缩项目的flex-grow的值不相同，就按照对应的占比分配。

```css
.outter {
    width: 1200px;
    height: 800px;
    border: 1px solid black;
    background-color: gray;
    /*水平居中*/
    margin: 0 auto;
    display: flex;
    /*主轴方向从右到左*/
    flex-direction: row;
    /*主轴排满了就换行*/
    flex-wrap: wrap;
}

.items {
    flex-grow: 1;
    width: 200px;
    height: 100px; /*strctch 不可以有高度*/
    background-color: green;
    border: 1px solid black;
}
```

### 伸缩盒模型的缩
* 当父元素的空间不够了，才会触发压缩。
* flex-shrink默认值是1，flex-shrink调整的是缩放的比例。
* flex-shrink的计算公式为：
```
容器总宽度从400px收缩到200px
三个容器宽度为100, 200, 100
flex-shrink缩放比例为 1, 2, 1

那么触发缩放以后，比例值的计算方式明细如下
比例值1:100*1 / 1400
比例值2:200*2 /1400
比例值3:100*1 /1400

实际的需要收缩的值为
200px(父容器欠缺的宽度) * 比例值1
200px(父容器欠缺的宽度) * 比例值2
200px(父容器欠缺的宽度) * 比例值3
```