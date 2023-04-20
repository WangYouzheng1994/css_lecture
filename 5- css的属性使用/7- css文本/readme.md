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