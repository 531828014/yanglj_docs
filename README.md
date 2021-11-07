# Markdown 语法

> An awesome project.

!> 一段重要的内容，可以和其他 **Markdown** 语法混用。

?> _TODO_ 完善示例

[link](/demo/)
[link](/demo/ ":ignore")
[link](/demo ":target=_blank")
[link](/demo2 ":target=_self")
[link](/demo ":disabled")

[example.com](https://example.com/ ":crossorgin")

- [ ] foo
- bar
- [x] baz
- [] bam <~ not working

  - [ ] bim
  - [ ] lim

  ![logo](https://docsify.js.org/_media/icon.svg ":size=WIDTHxHEIGHT")
  ![logo](https://docsify.js.org/_media/icon.svg ":size=50x100")
  ![logo](https://docsify.js.org/_media/icon.svg ":size=100")

<!-- 支持按百分比缩放 -->

![logo](https://docsify.js.org/_media/icon.svg ":size=10%")

![logo](https://docsify.js.org/_media/icon.svg ":class=someCssClass")

![logo](https://docsify.js.org/_media/icon.svg ":id=someCssId")

### 你好，世界！ :id=hello-world

# 一级标题

## 二级标题

### 三级标题

#### 四级标题

##### 五级标题

###### 六级标题

_斜体文本_
_斜体文本_
**粗体文本**
**粗体文本**
**_粗斜体文本_**
**_粗斜体文本_**

---

---

---

---

---

RUNOOB.COM
GOOGLE.COM
~~BAIDU.COM~~

<u>带下划线文本</u>

无序列表使用星号(\*)、加号(+)或是减号(-)作为列表标记，这些标记后面要添加一个空格

- 第一项
- 第二项
- 第三项

* 第一项
* 第二项
* 第三项

- 第一项
- 第二项
- 第三项

1.  第一项：
    - 第一项嵌套的第一个元素
    - 第一项嵌套的第二个元素
2.  第二项：
    - 第二项嵌套的第一个元素
    - 第二项嵌套的第二个元素

> 区块引用
> 菜鸟教程
> 学的不仅是技术更是梦想

> 最外层
>
> > 第一层嵌套
> >
> > > 第二层嵌套

- 第一项
  > 菜鸟教程
  > 学的不仅是技术更是梦想
- 第二项

`printf()` 函数

```javascript
$(document).ready(function () {
  alert("RUNOOB");
});
```

这是一个链接 [菜鸟教程](https://www.runoob.com)

这个链接用 1 作为网址变量 [Google][1]
这个链接用 runoob 作为网址变量 [Runoob][runoob]
然后在文档的结尾为变量赋值（网址）
[1]: http://www.google.com/
[runoob]: http://www.runoob.com/

<img src="http://static.runoob.com/images/runoob-logo.png" width="50%">

|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |


| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |

直接在文档里面用 HTML 撰写
目前支持的 HTML 元素有：<kbd> <b> <i> <em> <sup> <sub> <br>等 

使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑

**文本加粗** 
\*\* 正常显示星号 \*\*
