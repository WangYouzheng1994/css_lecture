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
1. 交集选择器
2. 