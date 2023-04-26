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
* 