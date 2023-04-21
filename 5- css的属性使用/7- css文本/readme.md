### 文本样式

1. 间距

- 用px作为单位，支持负数

* 字符间距 letter-spacing

```css
.letterspacing {
    letter-spacing: 12px;
}
```

* 单词间距 word-spacing

```css
.wordspacing {
    word-spacing: 12px;
}
```

2. 划线

* text-decoration

```css
.overline {
    text-decoration: overline;

}

.underline {
    text-decoration: underline;
}

.linethrough {
    text-decoration: line-through;
}

/*可以通过设置none 去掉超
链接a标签的下划线
ins上划线
del的删除线
*/
.none {
    text-decoration: none;
}
```

- 复合案例，没有顺序要求

```css

/*红色的上划波浪线*/
.overline {
    text-decoration: overline wavy red;
}

/*绿色的下划虚线*/
.underline {
    text-decoration: underline dotted green;
}
```

3. 文本缩进

* text-indent px为单位

```css
/* 缩进*/
.indent {
    text-indent: 40px;
}
```

4. 文本对齐

* text-align：支持left、center、right

```css
 /* 缩进40px，右对齐*/
.indent {
    text-indent: 40px;
    text-align: right;
}
```

5. 行高

> font-size 这个参数其实是调整的字体外围的那个看不见的盒子。 但是字体是可以超出那个盒子的，尤其是下边缘。
> 文字本身是基于基线对齐的。 基线：英文x的下边缘
* line-height 行高支持四种模式，是可以继承的

```css
div {
    font-size: 40px;
    /*数值表示*/
    /*line-height: 40px;*/
    /*line-height: normal;*/
    /*相对于font-size的倍数*/
    /*line-height: 1.5; 常用*/
    /*相对于font-size的百分比倍数*/
    line-height: 150%
}

```
> height和line-height的关系：如果设置了height，那么lineheight不会影响盒子的高度，
> 但是如果没有写height，那么高度就是行数+line-height

* line-height可以设置单行文字的垂直居中，方式是，和height保持一致
```css
div {
  height: 100px;
  /*保持和height一直的高度，就可以垂直居中啦*/
  line-height: 100px;
}

```

6. 垂直对齐
* vertical-align  
用于指定同一行元素之间以及表格单元格内文字的垂直对齐方式，**不能控制块元素**
- 可选参数
  - baseline 默认值，与父元素的基线对齐
  - top 顶部对齐
  - middle 元素的中部对齐父元素的基线 + 父元素字母x一半的对齐
  - bottom 底部对齐

```css
div {
    /*vertical-align: middle;*/
    /*vertical-align: top;*/
    vertical-align: bottom;
}
```