### 字体

1. 大小

* 可以被继承

```css
#a {
    font-size: 12px
}
```

2. 字体

* 衬线字体：类似于手写字体，容易阅读。比如：宋体
* 非衬线字体:完全抛弃装饰衬线，只剩下主干，造型简明有力，更具现代感，起源也很晚
* 优先使用英文名字
* 需要进行兜底
* windows默认的字体是微软雅黑

```css

/*衬线字体，最后用serif， 
非衬线字体，最后用sans-serif
*/
#f {
    font-size: 18px;
    font-family: "Microsoft YaHei UI", "STCaiyun", sans-serif;
}
```

3. 字体风格

* italic 斜体

```css
#b {
    font-size: 14px;
    font-family: "楷体";
    font-style: italic;
}
```

5. 字体粗细 从上到下由粗到细

* lighter
* normal 默认
* bold 加粗
* bolder 更粗 很多字体没有这个
* 数值 没意义： 100-300 就是light 400-500 就是normal 500-699 就是bold

```css

#c {
    font-size: 16px;
    font-family: "宋体";
    font-style: normal;
    font-weight: bold;
}
```

6. 字体属性混合编写
* 规则：xxxx，字号，字体
* 属性和属性之间空格分割
```css
div {
    font: bold italic 300px "微软雅黑";
}
```