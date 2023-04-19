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

* :first-child

```css
/*div的后代中，并且在所有兄弟元素中第一个而且是p的*/
div p:first-child {
    color: red;
}

/*div的直接后代中，并且在所有兄弟元素中第一个而且是p的*/
div > p:first-child {
    color: cornflowerblue;
}

/* 在所有兄弟元素中是第一个元素，而且是p的 */
p:first-child {
    color: yellow;
}
```

* :last-child

```css
/*div后代中，在所有兄弟中，最后一个元素并且是p*/
div > p:last-child {
    color: cornflowerblue;
}
```

* :nth-child()

```css
/*div后代中，在所有兄弟中第三个孩子，并且是p的*/
div p:nth-child(3) {
    color: red;
}

/*选择偶数*/
p:nth-child(2n) {
    color: blue
}

p:nth-child(even) {
    color: blue;
}

/*奇数*/
p:nth-child(2n+1) {
    color: greenyellow;
}

p:nth-child(odd) {
    color: greenyellow;
}

/*an+b 公式*/
/*获取前五个*/
p:nth-child(-n+5) {
    color: darkviolet;
}
```

```css
/*获取div的后代中，p类型的兄弟中第一个*/
div p:first-of-type {
    color: red;
}

/*获取div的直接后代中，p类型的兄弟中第一个*/
div > p:first-of-type {
    color: cornflowerblue;
}

/*兄弟中第2个并且是p*/
p:nth-of-type(2) {
    color: #03e8e8;
}
```

* :empty 选中没有任何内容的

```css
/*选中div中没有任何元素的*/
div:empty {
    width: 400px
}
```

* :root 选择根节点

```css
:root {
    color: red
}
```

* :only-of-type 没有相同类型的兄弟

```css
/*span类型，并且没有任何的span兄弟了*/
span:only-of-type {
    color: seagreen;
}

```

* only-child 没有兄弟

```css
/*div 类型的元素，并且没有任何兄弟*/
div:only-child {
    color: darkblue;
}
```

3. 否定伪类
* 排除括号中符合条件的元素
```css

/*div的直接后代的是p类型的，并且不是第一个孩子的元素*/
div>p:not(:first-child) {
    color: green;
}

/*div的直接后代，类型为p 并且除掉属性中title等于你好的、第一个孩子、class等于fall的*/
div>p:not([title='你好'],:first-child,.fall) {
    color: red
}
```

5. UI伪类
* :checked
```css

```
* diaabled
```css

```
* enable
```css

```

6. 目标伪类
7. 语言伪类