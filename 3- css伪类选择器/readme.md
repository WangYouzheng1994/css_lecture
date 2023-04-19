### 伪类和伪元素
https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements

- 伪元素其实相当于伪造了一个元素，并且给这个元素加了样式  
* 俩冒号`::`
- 伪类是给元素某些状态的描述，伪类没有伪造元素，例如 first-child 只是给子元素添加样式而已，
* 一个冒号`:`

#### 伪类选择器
1. 动态伪类 
* 下面a标签的伪类的编写顺序切记不可打乱，否则会有问题
* a标签特有 link 和 visited
```css
/* 选中没有访问过的a元素 */
a:link {
    color: blue;
}
/* 选中访问过的a元素 */
a:visited {
    color: red;
}
/* 选中鼠标停留的a元素 */
a:hover {
    color: yellow;
}

/* 选中（点击的时候）激活的a元素 */
a:active {
    color: green;
}

/*选中鼠标悬浮的span*/
span:hover {
    color: green;
}
/*选中鼠标点击激活时候的span*/
span:active {
    color: red;
}

```

2. 结构伪类