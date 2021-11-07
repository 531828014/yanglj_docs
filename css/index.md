# CSS 篇

## Flex 布局

?> [flex 自适应表格](/demo/flex自适应表格.html ":target=_self")

任何一个容器都可以指定为 Flex 布局。

```
.box{
  display: flex;
}
```

行内元素也可以使用 Flex 布局。

```
.box{
  display: inline-flex;
}
```

注意，设为 Flex 布局以后，子元素的 float、clear 和 vertical-align 属性将失效。

![logo](../images/css/flex/bg2015071004.png)

> 采用 Flex 布局的元素，称为 Flex 容器（flex container），简称"容器"。
> 它的所有子元素自动成为容器成员，称为 Flex 项目（flex item），简称"项目"。
> 容器两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。

#### 容器的属性

以下 6 个属性设置在容器上。

- flex-direction ：决定主轴的方向
- flex-wrap：轴线排不下，如何换行
- flex-flow：flex-direction 属性和 flex-wrap 属性的简写形式
- justify-content：项目在主轴上的对齐方式
- align-items：项目在交叉轴上如何对齐。
- align-content：定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。

##### flex-direction 属性

```
.box {
  flex-direction: row | row-reverse | column | column-reverse;
}
 row（默认值）：主轴为水平方向，起点在左端。
 row-reverse：主轴为水平方向，起点在右端。
 column：主轴为垂直方向，起点在上沿。
 column-reverse：主轴为垂直方向，起点在下沿。
```

![logo](../images/css/flex/bg2015071005.png)

##### flex-wrap 属性

默认情况下，项目都排在一条线（又称"轴线"）上。flex-wrap 属性定义，如果一条轴线排不下，如何换行。

```
.box{
  flex-wrap: nowrap | wrap | wrap-reverse;
}
（1）nowrap（默认）：不换行。
（2）wrap：换行，第一行在上方。
（3）wrap-reverse：换行，第一行在下方。
```

![logo](../images/css/flex/bg2015071006.png)

##### flex-flow 属性

flex-flow 属性是 flex-direction 属性和 flex-wrap 属性的简写形式，默认值为 row nowrap。

```
.box {
  flex-flow: <flex-direction> || <flex-wrap>;
}
```

##### justify-content 属性

justify-content 属性定义了项目在主轴上的对齐方式。

```
.box {
  justify-content: flex-start | flex-end | center | space-between | space-around;
}
flex-start（默认值）：左对齐
flex-end：右对齐
center： 居中
space-between：两端对齐，项目之间的间隔都相等。
space-around：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。
```

![logo](../images/css/flex/bg2015071010.png)

##### align-items 属性

align-items 属性定义项目在交叉轴上如何对齐。

```
.box {
  align-items: flex-start | flex-end | center | baseline | stretch;
}
```

![logo](../images/css/flex/bg2015071011.png)

##### align-content 属性

align-content 属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。

```
.box {
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}
flex-start：与交叉轴的起点对齐。
flex-end：与交叉轴的终点对齐。
center：与交叉轴的中点对齐。
space-between：与交叉轴两端对齐，轴线之间的间隔平均分布。
space-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
stretch（默认值）：轴线占满整个交叉轴。
```

![logo](../images/css/flex/bg2015071012.png)

### 项目的属性

以下 6 个属性设置在项目上。

- order：定义项目的排列顺序
- flex-grow：定义项目的放大比例
- flex-shrink：定义了项目的缩小比例
- flex-basis：定义了在分配多余空间之前，项目占据的主轴空间
- flex：flex-grow, flex-shrink 和 flex-basis，默认值为 0 1 auto。后两个属性可选。
- align-self

##### order 属性

order 属性定义项目的排列顺序。数值越小，排列越靠前，默认为 0。

```
.item {
  order: <integer>;
}
```

![logo](../images/css/flex/bg2015071013.png)

##### flex-grow 属性

flex-grow 属性定义项目的放大比例，默认为 0，即如果存在剩余空间，也不放大。

```
.item {
  flex-grow: <number>; /* default 0 */
}
```

![logo](../images/css/flex/bg2015071014.png)

所有项目的 flex-grow 属性都为 1，则它们将等分剩余空间（如果有的话）。

一个项目的 flex-grow 属性为 2，其他项目都为 1，则前者占据的剩余空间将比其他项多一倍。

##### flex-shrink 属性

flex-shrink 属性定义了项目的缩小比例，默认为 1，即如果空间不足，该项目将缩小。

```
.item {
  flex-shrink: <number>; /* default 1 */
}
```

![logo](../images/css/flex/bg2015071015.jpg)

所有项目的 flex-shrink 属性都为 1，当空间不足时，都将等比例缩小。

一个项目的 flex-shrink 属性为 0，其他项目都为 1，则空间不足时，前者不缩小。

负值对该属性无效。

##### flex-basis 属性

flex-basis 属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为 auto，即项目的本来大小。

```
.item {
  flex-basis: <length> | auto; /* default auto */
}
```

它可以设为跟 width 或 height 属性一样的值（比如 350px），则项目将占据固定空间。

##### flex 属性

flex 属性是 flex-grow, flex-shrink 和 flex-basis 的简写，默认值为 0 1 auto。后两个属性可选。

```
.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
}
```

该属性有两个快捷值：auto (1 1 auto) 和 none (0 0 auto)。

!> 建议优先使用这个属性，而不是单独写三个分离的属性，因为浏览器会推算相关值。

##### align-self 属性

align-self 属性允许单个项目有与其他项目不一样的对齐方式，可覆盖 align-items 属性。默认值为 auto，表示继承父元素的 align-items 属性，如果没有父元素，则等同于 stretch。

```
.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
该属性可能取6个值，除了auto，其他都与align-items属性完全一致。
```

![logo](../images/css/flex/bg2015071016.png)

---

## 文字溢出显示省略号

```
.box{
  white-space: nowrap; //文本强制不换行；
  text-overflow:ellipsis; //文本溢出显示省略号；
  overflow:hidden; //溢出的部分隐藏；
}

```
