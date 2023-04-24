### CSS的三大特性
1. 层叠性
2. 继承性
* 样式可以继承，继承的原则是就近原则
3. 优先级
* 选择器优先级
* 样式应用优先级

### 子元素div水平垂直居中
* 方案1：
```css
.parentdiv {
    width: 800px;
    height: 400px;
    background-color: #00ff51;
    /*避免margin塌陷*/
    overflow: hidden;
}

.childdiv {
    width: 400px;
    height: 100px;
    background-color: orange;
    font-size: 20px;
    /*水平居中*/
    margin: 0 auto;
    margin-top: 150px;
}

```

* 使用定位：



### 垂直居中
* vertical-align 
### 清除基线
* parent 设置font-size:0