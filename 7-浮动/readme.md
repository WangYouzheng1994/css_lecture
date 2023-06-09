### Float 浮动
* 浮动本身是定位用于 文字与图片的环绕效果处理。
* 浮动现在是很主流的定位方式。

通过案例总结：
* 浮动第一原则是，可以遮挡无文字的地方，如果有文字：1. 块级元素覆盖，并且文字优先往下顶。2. 行内元素，那么就横向移动

* 浮动后，宽度还是收到父亲宽度的影响，父容器的高度如果够，那么往右边走，如果不够，就超出父容器


### 浮动后的影响总结
* 对兄弟元素：后面的兄弟，会占据浮动元素之前的位置（文档流），在浮动元素的（层级）下面，对前面的兄弟没有影响。
* 对父元素：无法支撑父元素的高度（脱离文档流了），导致父元素高度塌陷，但是父元素的宽度依然会束缚浮动的元素

对兄弟元素：失去了margin合并，但是还是会有margin。

* **消除浮动**的塌陷，以及兄弟块元素无法正常展示内容的影响，以下有5种方案：
- 计算出子元素所需要的高度，给父元素固定写死高度`height:xxx`。
- 给父元素也设置浮动`float:left`，但是会带来其他的浮动影响
- 给父元素设置`overflow：hidden`，虽然会撑起来父元素的高度，但是兄弟的非浮动div中的内容会被隐藏~
- 在所有浮动元素的后面，加一个块元素，目的是撑起来父元素高度，这个块元素，设置 `clear:both`，这样他就可以做到文档流和内容不分离了
- 给父元素的最后设置伪元素css，通过伪元素来消除，原理与第四方案相同:
```css
/*.outter::after的时候 不能有块了，否则会失效*/
.outter::after {
    content: '';
    display: block;
    clear: both;
}
```
这个方案的缺陷是：
```html
<!--  .outter::after的时候 不能有块了，否则会失效  -->
<!--<div class="box last">
4
</div>-->
```
float布局的总结，设置浮动的时候，兄弟元素要么全浮动，要么不浮动。

---
### 使用float进行布局
