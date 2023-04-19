### CSS选择器

[https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Selectors](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Selectors)

#### 基础选择器

1. 通配选择器

* 选中所有html元素

```css
* {
    color: coral;
}
```

2. 元素选择器

```css
h2 {
    color: antiquewhite;
}

```

3. 类选择器，选中所有的class属性为xxx的元素

- 命名要求：`-`分割，不要纯数字，不要中文

```css
.green {
    color: green;
}

.big {
    font-size: 60px;
}

```

```html
<h1 class="green">我是第一个</h1>
<!-- 同时应用两个类选择器 -->
<h1 class="green big">我是第一个</h1>

```

4. id选择器，一个元素只能有一个id

```css
#h1_green {
    color: green;
}
```

```html
<h1 id="h1_green">我是第一个</h1>
```

#### 复合选择器

1. 交集选择器 “且”的语义去寻找元素

- 紧邻着编写，元素要放在第一个

* 元素+类选择器

```css
/*选中p标签中class为blue的元素*/
p.blue {
    color: blue;
}
```

* 类+类

```css
/*选中class为dog 和blue的元素*/
.dog.blue {
    color: blue;
}
```

2. 并集选择器 "或"的语义去寻找元素

* 多个选择器用,分割即可

```css
a,
#dog,
.h1_green {
    font-family: Arial;
}
```

3. 后代选择器 儿子孙子重孙子都属于后代

* 空格分割

```css
/*选择ul后面的li元素*/
ul li {
    color: blue;
}

/*选择 ul 后的 li 后的 a元素*/
ul li a {
    color: burlywood;
}

/*选择ul后的a元素*/
ul a {
    color: darksalmon;
}

/* 选择class为person后的li */
.person li {
    color: palegreen;
}

/*选择 person后的 div并且class是man的元素*/
.person div.man {
    color: tomato;
}
```

4. 子代选择器 直接孩子

* 使用`>`连接，先写父再写目标的直接儿子

```css
/*选择class为person的直接孩子li元素*/
.person > li {
    color: blueviolet;
}

/*选择class为person的孩子p的孩子a元素*/
.person > p > a {
    color: darksalmon;
}

```

5. 兄弟选择器

* **向下寻找**直接兄弟，使用`+`连接

```css
/*得到class为person的向下寻找直接兄弟a元素*/
.person + p {
    color: burlywood;
}
```

* **向下寻找**所有兄弟，使用`~`连接

```css
/*得到class为person的向下寻找直接+间接的兄弟a元素*/
.person ~ p {
    color: burlywood;
}
```

6. 属性选择器

* 使用`[]`包裹属性

```css
/*选中有name属性的元素*/
[name] {
    color: #45cfff;
}

/*选中name属性值为abc的元素*/
[name="abc"] {
    color: #45cfff;
}

/*选中name属性值为a开头的元素*/
[name^="a"] {
    color: #45cfff;
}

/*选中name属性值为u结尾的元素*/
[name$="u"] {
    color: #45cfff;
}

/*选中name属性值包含b的元素*/
[name*="b"] {
    color: #45cfff;
}
```
