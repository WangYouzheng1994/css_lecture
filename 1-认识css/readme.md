### CSS样式表的引入
1. 行内（内联）样式
* 只适合简单的样式调整，不可复用

```html
<h1 style="color: red; font-size:5px"></h1>
```
2. 内嵌（内部）样式
* 单页面内部可以复用

```html

<style>
    h1 {
        color: red; 
        font-size:5px
    }
</style>
```

3. 外部引入 **（最高频使用）**
* 可以做到页面级别的复用，只要引用了此css的页面都可以用，做到了样式分离，也可以触发浏览器缓存。

```html
<link rel="stylesheet" href="1.css"/> 

```
1.css如下
```css
h1 {
        color: red; 
        font-size:5px
    }
```


4. 嵌套引入，解决引入多个css的问题

html内容：
```html
 <link rel="stylesheet" href="style.css">
```
 
style.css内容

```css
@import "1.css";
@import "2.css";
@import "3.css";
@import "4.css";
```

### CSS样式表优先级
- 优先级从高到低：
1. 行内样式优先级最高
2. 内部样式和外部引入样式,他俩优先级是评级的，因此取决于引入顺序，后面会覆盖前面的
3. 同一个样式表，与编写顺序有关，后面会覆盖前面的


### CSS语法
1. 注释 `/**/`
2. 属性值用`;`结尾
3. 由选择器和声明块组成。

### CSS代码风格
1. 展开风格：开发阶段用，便于阅读与调试
2. 紧凑风格：上线推荐，减少文件体积。一般命名都是有个min的文件。webpack会帮我们把css变成紧凑的。