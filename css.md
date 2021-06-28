



## CSS

CSS 是一种描述 HTML 文档样式的语言。

CSS 描述应该如何显示 HTML 元素。

#### 什么是 CSS？

- *CSS* 指的是层叠样式表
- CSS 描述了如何在屏幕上显示 HTML 元素
- 外部样式表存储在 **.CSS** 文件中

## 一、创建CSS样式表

插入样式表的方法有三种:

- 外部样式表
- 内部样式表
- 内联样式

### 1.外部样式表

当样式需要应用于很多页面时，外部样式表将是理想的选择。在使用外部样式表的情况下，你可以通过改变一个文件来改变整个站点的外观。每个页面使用 <link> 标签链接到样式表。 <link> 标签在（文档的）头部

浏览器会从文件 mystyle.css 中读到样式声明，并根据它来格式文档。

外部样式表可以在任何文本编辑器中进行编辑。文件不能包含任何的 html 标签。样式表应该以 .css 扩展名进行保存。

```HTML
<head>
  <link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```



### 2.内部样式表

当单个文档需要特殊的样式时，就应该使用内部样式表。你可以使用 <style> 标签在文档头部定义内部样式表

```HTML
<head>
 <style>
  hr {color:sienna;}
  p {margin-left:20px;}
  body {background-image:url("images/back40.gif");}
 </style>
</head>
```



### 3.内联样式

由于要将表现和内容混杂在一起，内联样式会损失掉样式表的许多优势。请慎用这种方法，例如当样式仅需要在一个元素上应用一次时。

要使用内联样式，你需要在相关的标签内使用样式（style）属性。Style 属性可以包含任何 CSS 属性

```HTML
<p style="color:red;margin-left:20px">这是一个段落。</p>
```

### 4.多重样式优先级

样式表允许以多种方式规定样式信息。样式可以规定在单个的 HTML 元素中，在 HTML 页的头元素中，或在一个外部的 CSS 文件中。甚至可以在同一个 HTML 文档内部引用多个外部样式表。

一般情况下，优先级如下：

**（内联样式）Inline style > （内部样式）Internal style sheet >（外部样式）External style sheet > 浏览器默认样式**



## 二、css语法

### 1.选择器

CSS 选择器用于“查找”（或选取）要设置样式的 HTML 元素。

我们可以将 CSS 选择器分为五类：

- **简单选择器**（根据名称、id、类来选取元素）
- **组合器选择器**（根据它们之间的特定关系来选取元素）
- **伪类选择器**（根据特定状态选取元素）
- **伪元素选择器**（选取元素的一部分并设置其样式）
- **属性选择器**（根据属性或属性值来选取元素）

#### 1) .元素选择器

元素选择器根据元素名称来选择 HTML 元素。

```css
p {
  text-align: center;
  color: red;
}
```

#### 2) .id选择器

id 选择器使用 HTML 元素的 id 属性来选择特定元素。

元素的 id 在页面中是唯一的，因此 id 选择器用于选择一个唯一的元素！

要选择具有特定 id 的元素，请写一个井号（＃），后跟该元素的 id。

```css
#p-dom {
  text-align: center;
  color: red;
}
```

#### 3) . 类选择器

类选择器选择有特定 class 属性的 HTML 元素。

如需选择拥有特定 class 的元素，请写一个句点 `. `字符，后面跟类名。

```css
.center {
  text-align: center;
  color: red;
}
//只有特定的 HTML 元素会受类的影响
p.center {
  text-align: center;
  color: red;
}
```

#### 4) . 通用选择器

通用选择器  `* ` 选择页面上的所有的 HTML 元素。

```css
* {
  text-align: center;
  color: blue;
}
```



#### 5). 分组选择器(同级选择器)

分组选择器选取所有具有相同样式定义的 HTML 元素。

```
h1, h2, p {
  text-align: center;
  color: red;
}
```



#### 所有简单的 CSS 选择器

| 选择器               | 例子       | 例子描述                             |
| :------------------- | :--------- | :----------------------------------- |
| class                | .intro     | 选取所有 class="intro" 的元素。      |
| #id                  | #firstname | 选取 id="firstname" 的那个元素。     |
| *                    | *          | 选取所有元素。                       |
| element              | p          | 选取所有 <p> 元素。                  |
| element*,*element,.. | div, p     | 选取所有 <div> 元素和所有 <p> 元素。 |

#### 6) . 后代选择器

后代选择器（descendant selector）又称为包含选择器

后代选择器可以选择作为某元素后代的元素

```css
h1 em {color:red;}
```



#### 7) . 子级选择器

子元素选择器只能选择作为某元素子元素的元素

```
h1 > span {color:red;}
```

#### 8) . 相邻兄弟选择器

相邻兄弟选择器匹配所有作为指定元素的相邻同级的元素。

兄弟（同级）元素必须具有相同的父元素，“相邻”的意思是“紧随其后”。

选择紧随 <div> 元素之后的所有 <p> 元素：

```css
div + p {
  background-color: yellow;
}
```

#### 9) . 通用兄弟选择器

通用兄弟选择器匹配属于指定元素的同级元素的所有元素。

选择属于 <div> 元素的同级元素的所有 <p> 元素：

```css
div ~ p {
  background-color: yellow;
}
```

####  CSS 组合选择器

| 选择器           | 示例    | 示例描述                                   |
| :--------------- | :------ | :----------------------------------------- |
| element  element | div p   | 选择 <div> 元素内的所有 <p> 元素。         |
| element>element  | div > p | 选择其父元素是 <div> 元素的所有 <p> 元素。 |
| element+element  | div + p | 选择所有紧随 <div> 元素之后的 <p> 元素。   |

### 2.宽高

#### CSS 设置高度和宽度

height 和 width 属性用于设置元素的高度和宽度。

height 和 width 属性不包括内边距、边框或外边距。它设置的是元素内边距、边框以及外边距内的区域的高度或宽度。

**height** 和 **width** 属性不包括内边距、边框或外边距！它们设置的是元素的内边距、边框和外边距内的区域的高度/宽度

#### CSS 高度和宽度值

height 和 width 属性可设置如下值：

- auto - 默认。浏览器计算高度和宽度。
- *数值* - 以 px、em,rem 等定义高度/宽度。
- % - 以包含块的百分比定义高度/宽度。

#### CSS 高度和宽度实例

此元素的高度为 200 像素，宽度为 50％

设置 <div> 元素的高度和宽度：

```css
div {
  height: 200px;
  width: 50%;
  background-color: red;
}
```

#### 设置 max-width

max-width 属性用于设置元素的最大宽度。

可以用长度值（例如 px、cm 等）或包含块的百分比（％）来指定 max-width（最大宽度），也可以将其设置为 none（默认值。意味着没有最大宽度）。

当浏览器窗口小于元素的宽度（500px）时，会发生之前那个 <div> 的问题。然后，浏览器会将水平滚动条添加到页面。

**注释：**`max-width` 属性的值将覆盖 `width`（宽度）。

这个 <div> 元素的高度为 100 像素，最大宽度为 500 像素：

```css
div {
  max-width: 500px;
  height: 100px;
  background-color: powderblue;
}
```



### 3.背景

####   1.背景颜色

**background-color** 属性定义了元素的背景颜色

```css
body {background-color:#b0c4de;}
```

#### 2.背景图片

**background-image** 属性描述了元素的背景图像.

默认情况下，背景图像进行平铺重复显示，以覆盖整个元素实体

```css
body {background-image:url('bg.png');}
```

#### 3.背景图片-水平或垂直平铺

默认情况下 **background-repeat** 属性会决定图片在页面的水平或者垂直方向平铺

**repeat-x**：仅在水平方向重复

**repeat-y**：仅在垂直方向重复图像

**no-repeat**：背景图像仅显示一次

```css
body
{
background-image:url('bg.png');
background-repeat:repeat-x;
}
```

#### 4.背景图片位置

背景图像与文本显示在同一个位置，为了让页面排版更加合理，我们可以改变图像的位置

**background-position** 属性用于指定背景图像的位置。

第一个参数是**X**轴起点，第二个参数是**Y**轴起点

```css
body {
  background-image: url("bg.png");
  background-repeat: no-repeat;
  background-position: right top;
}
```

#### 5.背景属性简写

如需缩短代码，也可以在一个属性中指定所有背景属性。它被称为简写属性

在使用简写属性时，属性值的顺序为：

- background-color    背景颜色
- background-image     背景图片
- background-repeat      如何重复
- background-position     背景图片位置

属性值之一缺失并不要紧，只要按照此顺序设置其他值即可。请注意，在上面的例子中，我们没有使用 background-attachment 属性，因为它没有值。

```css
body {
  background-color: #ffffff;
  background-image: url("tree.png");
  background-repeat: no-repeat;
  background-position: right top;
}

body {
  background: #ffffff url("tree.png") no-repeat right top;
}

```

#### 所有 CSS 背景属性

| 属性                | 描述                                     |
| :------------------ | :--------------------------------------- |
| background          | 在一条声明中设置所有背景属性的简写属性。 |
| background-color    | 设置元素的背景色。                       |
| background-image    | 设置元素的背景图像。                     |
| background-position | 设置背景图像的开始位置。                 |
| background-repeat   | 设置背景图像是否及如何重复。             |
| background-size     | 规定背景图像的尺寸。                     |



### 4.边框

CSS border 属性允许指定元素边框的样式、宽度和颜色

#### CSS 边框样式

border-style 属性指定要显示的边框类型。

允许以下值：

- dotted - 定义点线边框
- dashed - 定义虚线边框
- solid - 定义实线边框
- double - 定义双边框
- none - 定义无边框

border-style 属性可以设置一到四个值（用于上边框、右边框、下边框和左边框）

```css
p {border-style: dotted;}
p {border-style: dashed;}
p {border-style: solid;}
p {border-style: double;}
p {border-style: none;}
p {border-style: dotted dashed solid double;}
```

#### CSS 边框 - 单独的边

从上一章的例子中，您已经看到可以为每一侧指定不同的边框。

在 CSS 中，还有一些属性可用于指定每个边框（顶部、右侧、底部和左侧）

```
p {
  border-top-style: dotted;
  border-right-style: solid;
  border-bottom-style: dotted;
  border-left-style: solid;
}
```

#### CSS Border - 简写属性

就像您在上一章中所见，处理边框时要考虑许多属性。

为了缩减代码，也可以在一个属性中指定所有单独的边框属性。

`border` 属性是以下各个边框属性的简写属性：

- `border-width`
- `border-style`（必需）
- `border-color`

```css
p {
  border: 5px solid red;
}
```

#### CSS 圆角边框

border-radius 属性用于向元素添加圆角边框

```css
p {
  border: 2px solid red;
  border-radius: 5px;
}
```



### 5.盒模型

#### CSS 盒模型

所有HTML元素可以看作盒子，在CSS中，"box model"这一术语是用来设计和布局时使用。

CSS盒模型本质上是一个盒子，封装周围的HTML元素，它包括：边距，边框，填充，和实际内容。

盒模型允许我们在其它元素和周围元素边框之间的空间放置元素。

下面的图片说明了盒子模型(Box Model)：


![CSS box-model](https://www.runoob.com/images/box-model.gif)

不同部分的说明：

- **Margin(外边距)** - 清除边框外的区域，外边距是透明的。
- **Border(边框)** - 围绕在内边距和内容外的边框。
- **Padding(内边距)** - 清除内容周围的区域，内边距是透明的。
- **Content(内容)** - 盒子的内容，显示文本和图像。

为了正确设置元素在所有浏览器中的宽度和高度，你需要知道的盒模型是如何工作的。

#### 元素的宽度和高度

 当指定一个 CSS 元素的宽度和高度属性时，只是设置内容区域的宽度和高度。完整大小的元素还包括内边距，边框和外边距。

下面的例子中的元素的总宽度为300px：

```css
div {    
    width: 300px;    
    border: 25px solid green;    
    padding: 25px;    
    margin: 25px; 
}
```

实际宽度为：
300px (宽)
\+ 50px (左 + 右填充)
\+ 50px (左 + 右边框)
\+ 50px (左 + 右边距)
= 450px

试想一下，你只有 250 像素的空间。让我们设置总宽度为 250 像素的元素:

```css
div {    
    width: 220px;    
    padding: 10px;    
    border: 5px solid gray;    
    margin: 0; 
}
```

最终元素的总宽度计算公式是这样的：

总元素的宽度=宽度+左填充+右填充+左边框+右边框+左边距+右边距

元素的总高度最终计算公式是这样的：

总元素的高度=高度+顶部填充+底部填充+上边框+下边框+上边距+下边距

### 6.外边距

​	CSS margin(外边距)属性定义元素周围的空间

#### margin

margin 清除周围的（外边框）元素区域。margin 没有背景颜色，是完全透明的。

margin 可以单独改变元素的上，下，左，右边距，也可以一次改变所有的属性。

![img](https://www.runoob.com/wp-content/uploads/2013/08/VlwVi.png)



#### 可选的值：

| 值       | 说明                                        |
| :------- | :------------------------------------------ |
| auto     | 设置浏览器边距。 这样做的结果会依赖于浏览器 |
| *length* | 定义一个固定的margin（使用像素，pt，em等）  |
| *%*      | 定义一个使用百分比的边距                    |

#### Margin - 单边外边距属性

在CSS中，它可以指定不同的侧面不同的边距

```css
margin-top:100px; 
margin-bottom:100px; 
margin-right:50px; 
margin-left:50px;
```



#### Margin - 简写属性

为了缩短代码，有可能使用一个属性中margin指定的所有边距属性。这就是所谓的简写属性。

所有边距属性的简写属性是 **margin** :

技巧口令: **上 右 下 左**

```css
margin:100px 50px;
```

margin属性可以有一到四个值。

- margin:25px 50px 75px 100px;
    - 上边距为25px
    - 右边距为50px
    - 下边距为75px
    - 左边距为100px
- margin:25px 50px 75px ;
    - 上边距为25px
    - 左右边距为50px
    - 下边距为75px
- margin:25px 50px;
    - 上下边距为25px
    - 左右边距为50px
- margin:25px;
    - 所有的4个边距都是25px



### 7.内边距

​	CSS padding（填充）是一个简写属性，定义元素边框与元素内容之间的空间，即上下左右的内边距

当元素的 padding（填充）内边距被清除时，所释放的区域将会受到元素背景颜色的填充。

单独使用 padding 属性可以改变上下左右的填充。

![img](https://www.runoob.com/wp-content/uploads/2013/08/VlwVi.png)

#### 可选的值

| 值       | 说明                                |
| :------- | :---------------------------------- |
| *length* | 定义一个固定的填充(像素, pt, em,等) |
| *%*      | 使用百分比值定义一个填充            |

#### 填充- 单边内边距属性

在CSS中，它可以指定不同的侧面不同的填充：

技巧口令: **上 右 下 左**

```css
padding-top:25px;
padding-bottom:25px;
padding-right:50px;
padding-left:50px;
```

- 上内边距是 25px
- 右内边距是 50px
- 下内边距是 25px
- 左内边距是 50px

#### 填充 - 简写属性

为了缩短代码，它可以在一个属性中指定的所有填充属性。

这就是所谓的简写属性。所有的填充属性的简写属性是 **padding** :

```css
padding:25px 50px;
```

Padding属性，可以有一到四个值。

 **padding:25px 50px 75px 100px;**

- 上填充为25px
- 右填充为50px
- 下填充为75px
- 左填充为100px

 **padding:25px 50px 75px;**

- 上填充为25px
- 左右填充为50px
- 下填充为75px

 **padding:25px 50px;**

- 上下填充为25px
- 左右填充为50px

 **padding:25px;**

- 所有的填充都是25px



### 8.CSS 外边距合并

**外边距合并指的是，当两个垂直外边距相遇时，它们将形成一个外边距。**

**合并后的外边距的高度等于两个发生合并的外边距的高度中的较大者。**

#### 外边距合并

外边距合并（叠加）是一个相当简单的概念。但是，在实践中对网页进行布局时，它会造成许多混淆。

简单地说，外边距合并指的是，当两个垂直外边距相遇时，它们将形成一个外边距。合并后的外边距的高度等于两个发生合并的外边距的高度中的较大者。

当一个元素出现在另一个元素上面时，第一个元素的下外边距与第二个元素的上外边距会发生合并。

![CSS 外边距合并实例 1](https://www.w3school.com.cn/i/css/margin_collapsing_1.gif)

当一个元素包含在另一个元素中时（假设没有内边距或边框把外边距分隔开），它们的上和/或下外边距也会发生合并

![CSS 外边距合并实例 2](https://www.w3school.com.cn/i/css/margin_collapsing_example_2.gif)

假设有一个空元素，它有外边距，但是没有边框或填充。在这种情况下，上外边距与下外边距就碰到了一起，它们会发生合并：

![CSS 外边距合并实例 3](https://www.w3school.com.cn/i/css/margin_collapsing_example_3.gif)

如果这个外边距遇到另一个元素的外边距，它还会发生合并：

![CSS 外边距合并实例 4](https://www.w3school.com.cn/i/css/margin_collapsing_example_4.gif)

这就是一系列的段落元素占用空间非常小的原因，因为它们的所有外边距都合并到一起，形成了一个小的外边距。

外边距合并初看上去可能有点奇怪，但是实际上，它是有意义的。第一个段落上面的空间等于段落的上外边距。如果没有外边距合并，后续所有段落之间的外边距都将是相邻上外边距和下外边距的和。这意味着段落之间的空间是页面顶部的两倍。如果发生外边距合并，段落之间的上外边距和下外边距就合并在一起，这样各处的距离就一致了。

![CSS 外边距合并的实际意义](https://www.w3school.com.cn/i/css/margin_collapsing.gif)

**注释：**只有普通文档流中**块框的垂直外边距**才会发生外边距合并。行内框、浮动框或绝对定位之间的外边距不会合并。



### 9.文本

#### 1.文本颜色

color 属性用于设置文本的颜色。颜色由以下值指定：

- 颜色名 - 比如 "red"
- 十六进制值 - 比如 "#ff0000"
- rgb值 - 比如 "rgb(158, 60, 77);"
- rgba 值 - 比如 "rgba(158, 60, 77,0.5);"

R：红色值。正整数 | 百分数

G：绿色值。正整数 | 百分数

B：蓝色值。正整数 | 百分数

A：Alpha透明度。取值0~1之间。(颜色的透明度)

```css
body {
  color: blue;
}

h1 {
  color: green;
}

h2{
    background-color: rgba(158, 60, 77,0.5);
}

h3{
    background-color: rgba(158, 60, 77);
}
```

#### 2.文本对齐

文本排列属性是用来设置文本的水平对齐方式。

文本可居中或对齐到左或右,两端对齐.

```css
h1 {text-align:center;} 
p.date {text-align:right;} 
p.main {text-align:left;}
```

#### 3.文本修饰

text-decoration 属性用来设置或删除文本的装饰。

从设计的角度看 text-decoration属性主要是用来删除链接的下划线：

```css
a {text-decoration:none;}
```

#### 4.文本转换

文本转换属性是用来指定在一个文本中的大写和小写字母。

可用于所有字句变成大写或小写字母，或每个单词的首字母大写。

```css
p.uppercase {text-transform:uppercase;}  //全部大写
p.lowercase {text-transform:lowercase;}   //全部小写
p.capitalize {text-transform:capitalize;} //文本中的每个单词以大写字母开头
```

#### 5.文本缩进

文本缩进属性是用来指定文本的第一行的缩进。

```css
p {text-indent:50px;}
```



### 10.字体

CSS字体属性定义字体，加粗，大小，文字样式。

#### 1.字体

font-family 属性设置文本的字体系列。

font-family 属性应该设置几个字体名称作为一种"后备"机制，如果浏览器不支持第一种字体，他将尝试下一种字体。

**注意**: 如果字体系列的名称超过一个字，它必须用引号，如Font Family："宋体"。

多个字体系列是用一个逗号分隔指明

```css
p{font-family:"Times New Roman", Times, serif;}  //标准雅黑  
```

#### 2.字体大小

font-size 属性设置文本的大小。

设置文字的大小与像素控制文字大小：

```css
h1 {font-size:40px;}
h2 {font-size:30px;}
p {font-size:14px;}
```

#### 3.文字粗细

使用**font-weight**修改文字粗细

```css
font-weight:600
```

#### CSS字体属性

| Property    | 描述               |
| :---------- | :----------------- |
| font-family | 指定文本的字体系列 |
| font-size   | 指定文本的字体大小 |
| font-weight | 指定字体的粗细。   |



## 三、布局

### 1.display属性

**display** 属性是用于控制布局的最重要的 CSS 属性。

display 属性规定是否/如何显示元素。

每个 HTML 元素都有一个默认的 display 值，具体取决于它的元素类型。大多数元素的默认 display 值为 block 或 inline。

#### 块级元素（block element）

块级元素总是从新行开始，并占据可用的全部宽度（尽可能向左和向右伸展）。

这个 <div> 元素属于块级元素。

#### 行内元素（inline element）

内联元素不从新行开始，仅占用所需的宽度。

这是段落中的行内 <span> 元素。

行内元素的一些例子：

- <span>
- <a>
- <img>

#### Display: none;

display: none; 通常与 JavaScript 一起使用，以隐藏和显示元素，而无需删除和重新创建它们。如果您想知道如何实现此目标，请查看本页面上的最后一个实例。

默认情况下，<script> 元素使用 display: none;。

#### 覆盖默认的 Display 值

如前所述，每个元素都有一个默认 display 值。但是，您可以覆盖它。

将行内元素更改为块元素，反之亦然，对于使页面以特定方式显示同时仍遵循 Web 标准很有用。

一个常见的例子是为实现水平菜单而生成行内的 <li> 元素

```css
li {
  display: inline;
}
```

设置元素的 display 属性仅会更改*元素的显示方式*，而不会更改元素的种类。因此，带有 **display: block;** 的行内元素不允许在其中包含其他块元素

将 <span> 元素显示为块元素：

```css
span {
  display: block;
}
```



### 2.定位

#### Position 属性

position 属性规定应用于元素的定位方法的类型。

有三个不同的位置值：

- relative
- fixed
- absolute

元素其实是使用 top、bottom、left 和 right 属性定位的。但是，除非首先设置了 position 属性，否则这些属性将不起作用。根据不同的 position 值，它们的工作方式也不同。

#### position: relative;(相对定位)

position: relative; 的元素相对于其正常位置进行定位。

设置相对定位的元素的 top、right、bottom 和 left 属性将导致其偏离其正常位置进行调整。不会对其余内容进行调整来适应元素留下的任何空间。

这个 <div> 元素设置了 position: relative;

```css
div.relative {
  position: relative;
  left: 30px;
  border: 3px solid #73AD21;
}
```

#### position: fixed;(固定定位)

position: fixed; 的元素是相对于视口定位的，这意味着即使滚动页面，它也始终位于同一位置。 top、right、bottom 和 left 属性用于定位此元素。

固定定位的元素不会在页面中通常应放置的位置上留出空隙。

请注意页面右下角的这个固定元素。

```css
div.fixed {
  position: fixed;
  bottom: 0;
  right: 0;
  width: 300px;
  border: 3px solid #73AD21;
}
```

#### position: absolute;(绝对定位)

position: absolute; 的元素相对于**最近的定位祖先**元素进行定位（而不是相对于视口定位，如 fixed）。

然而，如果绝对定位的元素没有祖先，它将使用文档主体（body），并随页面滚动一起移动。

**注意：**“被定位的”元素是其位置除 **static** 以外的任何元素。

**口令：子绝父相**

```
div.relative {
  position: relative;
  width: 400px;
  height: 200px;
  border: 3px solid #73AD21;
} 

div.absolute {
  position: absolute;
  top: 80px;
  right: 0;
  width: 200px;
  height: 100px;
  border: 3px solid #73AD21;
}
```

#### 重叠元素

在对元素进行定位时，它们可以与其他元素重叠。

z-index 属性指定元素的堆栈顺序（哪个元素应放置在其他元素的前面或后面）。

```css
img {
  position: absolute;
  left: 0px;
  top: 0px;
  z-index: -1;
}
```

#### CSS 定位属性

| 属性     | 描述                         |
| :------- | :--------------------------- |
| bottom   | 设置定位框的底部外边距边缘。 |
| left     | 设置定位框的左侧外边距边缘。 |
| position | 规定元素的定位类型。         |
| right    | 设置定位框的右侧外边距边缘。 |
| top      | 设置定位框的顶部外边距边缘。 |
| z-index  | 设置元素的堆叠顺序。         |



### 3.溢出

#### overflow 

overflow 属性指定在元素的内容太大而无法放入指定区域时是剪裁内容还是添加滚动条。

overflow 属性可设置以下值：

- visible - 默认。溢出没有被剪裁。内容在元素框外渲染
- hidden - 溢出被剪裁，其余内容将不可见
- scroll - 溢出被剪裁，同时添加滚动条以查看其余内容
- auto - 与 scroll 类似，但仅在必要时添加滚动条

**overflow** 属性仅适用于具有指定高度的块元素

#### overflow-x  overflow-y

overflow-x 和 overflow-y 属性规定是仅水平还是垂直地（或同时）更改内容的溢出：

- overflow-x 指定如何处理内容的左/右边缘。
- overflow-y 指定如何处理内容的上/下边缘。

#### 所有 CSS Overflow 属性

| 属性       | 描述                                                |
| :--------- | :-------------------------------------------------- |
| overflow   | 规定如果内容溢出元素框会发生什么情况。              |
| overflow-x | 规定在元素的内容区域溢出时如何处理内容的左/右边缘。 |
| overflow-y | 指定在元素的内容区域溢出时如何处理内容的上/下边缘。 |



### 4.浮动

float浮动，会使元素向左或向右移动，**其周围的元素也会重新排列**。

#### 元素怎样浮动

元素的水平方向浮动，意味着元素只能左右移动而不能上下移动。

一个浮动元素会尽量向左或向右移动，直到它的外边缘碰到包含框或另一个浮动框的边框为止。

浮动元素之后的元素将围绕它。

浮动元素之前的元素将不会受到影响。

```css
img{
    float:right;  //left
}
```



#### 清除浮动 

- **在标签结尾处加空div标签 clear:both**

```css
.text_line{
    clear:both;
}
```

- **父级div定义 伪类:after 和 zoom**

    利用:after或者:before来在元素内部插入元素块，从而达到清除浮动的效果

    ```css
    div.box {
        zoom:1;
    } 
    div.box :after {
        clear:both;
        content:'.';
        display:block;
        width: 0;
        height: 0;
        visibility:hidden;
    } 
    ```

- **父级div定义 overflow:hidden**

    ```css
    div.box {
        overflow:hidden
    } 
    ```

- **父级元素单独定义高度**

    ```css
    div.box {
        height:200px
    } 
    ```



### 5.水平 & 垂直对齐

#### 1.元素居中对齐

要水平居中对齐一个元素(如 <div>), 可以使用 **margin: auto;**。

设置到元素的宽度将防止它溢出到容器的边缘。

元素通过指定宽度，并将两边的空外边距平均分配

 如果没有设置 **width** 属性(或者设置 100%)，居中对齐将不起作用

div 元素是居中的

```css
.center {    
    margin:0 auto;    
    width: 50%;    
    border: 3px solid green;    
    padding: 10px; 
}
```

#### 2.文本居中对齐

如果仅仅是为了文本在元素内居中对齐，可以使用 **text-align: center;**

```css
.center {    
    text-align: center;    
    border: 3px solid green; 
}
```

#### 3.行内元素居中对齐

要让图片居中对齐, 可以使用 **margin: auto;** 并将它编程 **块** 元素

```css
img {
    display: block;
    margin:0 auto;
    width: 40%;
}
```

#### 4.垂直对齐

- 使用 padding 将内容控制在元素中间

    ```css
    .center {
      padding: 70px 0;
      border: 3px solid green;
    }
    ```

    

- 使用 line-height 利用行高让文字居中

    ```css
    .center {
      line-height: 200px;
      height: 200px;
      border: 3px solid green;
      text-align: center;
    }
    
    /* 如果有多行文本，请添加如下代码：*/
    .center p {
      line-height: 1.5;
      display: inline-block;
      vertical-align: middle;
    }
    ```

    

- 使用 Flexbox

    ```css
    .center {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 200px;
      border: 3px solid green; 
    }
    ```



## 四、伪类

### 1.伪类

css伪类是用来添加一些选择器的特殊效果



##### 1) .语法

伪类的语法：

```css
a:link {color:#FF0000;} /* 未访问的链接 */ 
a:visited {color:#00FF00;} /* 已访问的链接 */ 
a:hover {color:#FF00FF;} /* 鼠标划过链接 */ 
a:active {color:#0000FF;} /* 已选中的链接 */
```

**注意：** 在CSS定义中，a:hover 必须被置于 a:link 和 a:visited 之后，才是有效的

​             在 CSS 定义中，a:active 必须被置于 a:hover 之后，才是有效的

​             伪类的名称不区分大小写



##### 2) .first-child 伪类

使用 :first-child 伪类来选择父元素的第一个子元素。

###### 匹配第一个 <p> 元素

```css
p:first-child{
    color:blue;
}
```

###### 匹配所有<p> 元素中的第一个 <i> 元素

```css
p > i:first-child{
    color:blue;
}
```

##### 3).last-child 选择器

使用 :last-child 伪类来选择父元素的最后一个子元素

###### 匹配最后哦一个 <p> 元素

```css
p:last-child{
    color:blue;
}
```

###### 匹配所有<p> 元素中的最后一个 <i> 元素

```css
p > i:last-child{
    color:blue;
}
```

##### 

### 2.伪元素

#### 1).  :before 伪元素

**:before** 伪元素可以在元素的内容前面插入新内容

在每个 <h1>元素前面插入一幅图片：

```css
h1:before {
    content:url(logo.png);
}
```

#### 2) . :after 伪元素

**:after** 伪元素可以在元素的内容之后插入新内容

在每个 <h1> 元素后面插入一幅图片：

```css
h1:after {    
    content:url(logo.png); 
}
```



## 五、样式

### 1. CSS 阴影效果

- **text-shadow** 文字阴影

    ```css
    h1 {
        /**只指定水平阴影（2px）和垂直阴影（2px）**/
      text-shadow: 2px 2px;
    }
    
    h1 {
         /**为阴影添加颜色**/
      text-shadow: 2px 2px red;
    }
    
    h1 {
         /**向阴影添加模糊效果**/
      text-shadow: 2px 2px 5px red;
    }
    h1 {
        /**带有黑色阴影的白色文本**/
      color: white;
      text-shadow: 2px 2px 4px #000000;
    }
    
    h1 {
        /**多个阴影**/
      text-shadow: 0 0 3px #FF0000, 0 0 5px #0000FF;
    }
    h1 {
        /**带有黑色、蓝色和深蓝色阴影的白色文本**/
      color: white;
      text-shadow: 1px 1px 2px black, 0 0 25px blue, 0 0 5px darkblue;
    }
    h1 {
         /**在文本周围创建纯边框（无阴影）**/
      color: yellow;
      text-shadow: -1px 0 black, 0 1px black, 1px 0 black, 0 -1px black;
    }
    ```

    

- **box-shadow**  盒子阴影

    ```css
    div {
     /**只指定水平阴影和垂直阴影**/
      box-shadow: 10px 10px;
    }
    
    div {
         /**为阴影添加颜色**/
      box-shadow: 10px 10px grey;
    }
    
    div {
        /**向阴影添加模糊效果**/
      box-shadow: 10px 10px 5px grey;
    }
    ```



### 2. 2D 转换

CSS 转换（transforms）允许您移动、旋转、缩放和倾斜元素

#### 1). translate() 

从其当前位置移动元素（根据为 X 轴和 Y 轴指定的参数）。

把 <div> 元素从其当前位置向右移动 50 个像素，并向下移动 100 个像素

```
div {
  transform: translate(50px, 100px);
}
```

#### 2). rotate() 

根据给定的角度顺时针或逆时针旋转元素

把 <div> 元素顺时针旋转 20 度

```css
div {
  transform: rotate(20deg);
}

div {
    /**使用负值将逆时针旋转元素**/
  transform: rotate(-20deg);
}
```

#### 3). scale() 

scale() 方法增加或减少元素的大小（根据给定的宽度和高度参数）。

把 <div> 元素增大为其原始宽度的两倍和其原始高度的三倍

```css
div {
  transform: scale(2, 3);
}

div {
    /**元素减小为其原始宽度和高度的一半**/
  transform: scale(0.5, 0.5);
}
```

#### 4) . scaleX() 

scaleX() 方法增加或减少元素的宽度。

把 <div> 元素增大为其原始宽度的两倍：

```css
div {
  transform: scaleX(2);
}
```

#### 5) . scaleY() 

scaleY() 方法增加或减少元素的高度。

把 <div> 元素增大到其原始高度的三倍：

```css
div {
  transform: scaleY(3);
}
```

#### 6) . skewX()

skewX() 方法使元素沿 X 轴倾斜给定角度。

把 <div> 元素沿X轴倾斜 20 度

```css
div {
  transform: skewX(20deg);
}
```

#### 7) . skewX() 

skewY() 方法使元素沿 Y 轴倾斜给定角度。

把 <div> 元素沿 Y 轴倾斜 20 度：

```css
div {
  transform: skewY(20deg);
}
```

#### 8) . skew() 

skew() 方法使元素沿 X 和 Y 轴倾斜给定角度。

使 <div> 元素沿 X 轴倾斜 20 度，同时沿 Y 轴倾斜 10 度

```css
div {
  transform: skew(20deg, 10deg);
}

div {
    /**如果未指定第二个参数，则值为零**/
  transform: skew(20deg);
}
```

#### 9). matrix()

matrix() 方法把所有 2D 变换方法组合为一个。

matrix() 方法可接受六个参数，其中包括数学函数，这些参数使您可以旋转、缩放、移动（平移）和倾斜元素。

参数如下：matrix(scaleX(),skewY(),skewX(),scaleY(),translateX(),translateY())

```css
div {
  transform: matrix(1, -0.3, 0, 1, 0, 0);
}
```



#### CSS 2D 转换方法

| 函数                            | 描述                                     |
| :------------------------------ | :--------------------------------------- |
| matrix(*n*,*n*,*n*,*n*,*n*,*n*) | 定义 2D 转换，使用六个值的矩阵。         |
| translate(*x*,*y*)              | 定义 2D 转换，沿着 X 和 Y 轴移动元素。   |
| translateX(*n*)                 | 定义 2D 转换，沿着 X 轴移动元素。        |
| translateY(*n*)                 | 定义 2D 转换，沿着 Y 轴移动元素。        |
| scale(*x*,*y*)                  | 定义 2D 缩放转换，改变元素的宽度和高度。 |
| scaleX(*n*)                     | 定义 2D 缩放转换，改变元素的宽度。       |
| scaleY(*n*)                     | 定义 2D 缩放转换，改变元素的高度。       |
| rotate(*angle*)                 | 定义 2D 旋转，在参数中规定角度。         |
| skew(*x-angle*,*y-angle*)       | 定义 2D 倾斜转换，沿着 X 和 Y 轴。       |
| skewX(*angle*)                  | 定义 2D 倾斜转换，沿着 X 轴。            |
| skewY(*angle*)                  | 定义 2D 倾斜转换，沿着 Y 轴。            |



### 3. 3D

#### 3D 转换方法

通过 CSS transform 属性，您可以使用以下 3D 转换方法：

- rotateX()
- rotateY()
- rotateZ()

#### 1). rotateX() 

rotateX() 方法使元素绕其 X 轴旋转给定角度：

```css
#myDiv {
  transform: rotateX(150deg);
}
```

#### 2). rotateY() 

rotateY() 方法使元素绕其 Y 轴旋转给定角度:

```css
#myDiv {
  transform: rotateY(130deg);
}
```

#### 3) . rotateZ() 

rotateZ() 方法使元素绕其 Z 轴旋转给定角度：

```css
#myDiv {
  transform: rotateZ(90deg);
}
```



### 4.过渡

#### 1).transition

CSS 过渡允许您在给定的时间内平滑地改变属性值

CSS3 过渡是元素从一种样式逐渐改变为另一种的效果

要实现这一点，必须规定两项内容：

- 指定要添加效果的CSS属性

- 指定效果的持续时间

    应用于宽度属性的过渡效果，时长为 2 秒：

    ```css
    div{
    	width:100px;
    	height:100px;
    	background:red;
    	transition:width 2s;
    	-webkit-transition:width 2s; /* Safari */
    }
    
    div:hover{
    	width:300px;
    }
    ```

    

要添加多个样式的变换效果，添加的属性由逗号分隔：

```css
div {
    width: 100px;
    height: 100px;
    background: red;
    -webkit-transition: width 2s, height 2s, -webkit-transform 2s; /* For Safari 3.1 to 6.0 */
    transition: width 2s, height 2s, transform 2s;
}

div:hover {
    width: 200px;
    height: 200px;
    -webkit-transform: rotate(180deg); /* Chrome, Safari, Opera */
    transform: rotate(180deg);
}
```

#### 指定过渡的速度曲线

transition-timing-function 属性规定过渡效果的速度曲线。

transition-timing-function 属性可接受以下值：

- ease - 规定过渡效果，先缓慢地开始，然后加速，然后缓慢地结束（默认）
- linear - 规定从开始到结束具有相同速度的过渡效果
- ease-in -规定缓慢开始的过渡效果
- ease-out - 规定缓慢结束的过渡效果
- ease-in-out - 规定开始和结束较慢的过渡效果
- cubic-bezier(n,n,n,n) - 允许您在三次贝塞尔函数中定义自己的值

```css
#div1 {transition-timing-function: linear;}
#div2 {transition-timing-function: ease;}
#div3 {transition-timing-function: ease-in;}
#div4 {transition-timing-function: ease-out;}
#div5 {transition-timing-function: ease-in-out;}
```



#### 2) .延迟过渡效果

transition-delay 属性规定过渡效果的延迟（以秒计）。

下例在启动之前有 1 秒的延迟：

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 3s;
  transition-delay: 1s;
}

div:hover {
  width: 300px;
}
```

#### 3). 简写的 transition 属性：

​	transition: 属性 时间 效果 延时

```
div {
  transition: width 2s linear 1s;
}
```



### 5.动画

动画是使元素从一种样式逐渐变化为另一种样式的效果。

您可以改变任意多的样式任意多的次数。

请用百分比来规定变化发生的时间，或用关键词 "from" 和 "to"，等同于 0% 和 100%。

0% 是动画的开始，100% 是动画的完成。

为了得到最佳的浏览器支持，您应该始终定义 0% 和 100% 选择器。

当在 **@keyframes** 创建动画，把它绑定到一个选择器，否则动画不会有任何效果。

指定至少这两个CSS3的动画属性绑定向一个选择器：

- 规定动画的名称
- 规定动画的时长

```css
div{
	width:100px;
	height:100px;
	background:red;
	animation:myfirst 5s;
	-webkit-animation:myfirst 5s; /* Safari and Chrome */
}

@keyframes myfirst
{
	from {background:red;}
	to {background:yellow;}
}

@-webkit-keyframes myfirst /* Safari and Chrome */
{
	from {background:red;}
	to {background:yellow;}
}
```

当动画为 25% 及 50% 时改变背景色，然后当动画 100% 完成时再次改变：

```css
div{
	width:100px;
	height:100px;
	background:red;
	position:relative;
	animation:myfirst 5s;
	-webkit-animation:myfirst 5s; /* Safari and Chrome */
}

@keyframes myfirst
{
	0%   {background:red; left:0px; top:0px;}
	25%  {background:yellow; left:200px; top:0px;}
	50%  {background:blue; left:200px; top:200px;}
	75%  {background:green; left:0px; top:200px;}
	100% {background:red; left:0px; top:0px;}
}

@-webkit-keyframes myfirst /* Safari and Chrome */
{
	0%   {background:red; left:0px; top:0px;}
	25%  {background:yellow; left:200px; top:0px;}
	50%  {background:blue; left:200px; top:200px;}
	75%  {background:green; left:0px; top:200px;}
	100% {background:red; left:0px; top:0px;}
}
```



### 6.媒体查询

在屏幕可视窗口尺寸小于 480 像素的设备上修改背景颜色:

```css
@media screen and (max-width: 480px) {    
    body {        
        background-color: lightgreen;    
    } 
}

/**在屏幕可视窗口尺寸小于 600 像素时将 div 元素隐藏**/
@media screen and (max-width: 600px) {
  div.example {
    display: none;
  }
}
```



## 六、css三大特性

### 1.层叠性（覆盖）

![图片](https://mmbiz.qpic.cn/mmbiz_png/iclmxCdEUxyLseicHWsw8SmT9a2Y5jbibYTAueJLuOj7UV053UehR96PX15xGJHt3WlTEJCHJBPHhHuITFgkGRhsA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

所谓层叠性是指多种CSS样式的叠加。

是浏览器处理冲突的一个能力,如果一个属性通过两个相同选择器设置到同一个元素上，那么这个时候一个属性就会将另一个属性层叠掉

#### 层叠原则：

- 样式冲突，遵循的原则是**就近原则。** 那个样式离着结构近，就执行那个样式。
- 样式不冲突，不会层叠



### 2.继承性

![图片](https://mmbiz.qpic.cn/mmbiz_png/iclmxCdEUxyLseicHWsw8SmT9a2Y5jbibYTsmia2ZicrTHibAgpGSszYUUAap7hgKmaZ8icLvYpITBtCxX6J6qECiaj1Pw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

子标签会继承父标签的某些样式，如文本颜色和字号。

想要设置一个可继承的属性，只需将它应用于父元素即可。

#### 注意：

- 恰当地使用继承可以简化代码，降低CSS样式的复杂性。比如有很多子级孩子都需要某个样式，可以给父级指定一个，这些孩子继承过来就好了。
- 子元素可以继承父元素的样式（**text-，font-，line-这些元素开头的可以继承，以及color属性**）



### 3.优先级

![图片](https://mmbiz.qpic.cn/mmbiz_png/iclmxCdEUxyLseicHWsw8SmT9a2Y5jbibYTt1pWicJ0I7dibT6Gq2uq3aD11ldmpj0n1dLdBxL87l69GjKIhhHMcwWQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

定义CSS样式时，经常出现两个或更多规则应用在同一元素上，此时，

- 选择器相同，则执行层叠性
- 选择器不同，就会出现优先级的问题。

#### 权重计算公式

关于CSS权重，我们需要一套计算公式来去计算，这个就是 CSS Specificity（特殊性）

| 标签选择器             | 计算权重公式 |
| ---------------------- | ------------ |
| 继承或者 *             | 0,0,0,0      |
| 每个元素（标签选择器） | 0,0,0,1      |
| 每个类，伪类           | 0,0,1,0      |
| 每个ID                 | 0,1,0,0      |
| 每个行内样式 style=""  | 1,0,0,0      |
| 每个!important 重要的  | ∞ 无穷大     |

- 值从左到右，左面的最大，一级大于一级，数位之间没有进制，级别之间不可超越。
- 关于CSS权重，我们需要一套计算公式来去计算，这个就是 CSS Specificity（特殊性）



### 4.权重叠加

我们经常用交集选择器，后代选择器等，是有多个基础选择器组合而成，那么此时，就会出现权重叠加。

就是一个简单的加法计算

- div ul li ------> 0,0,0,3
- .nav ul li ------> 0,0,1,2
- a:hover -----—> 0,0,1,1
- .nav a ------> 0,0,1,1

#####    注意：

​         数位之间没有进制 比如说：0,0,0,5 + 0,0,0,5 =0,0,0,10 而不是 0,0, 1, 0， 所以不会存在10个div能赶上一个类选择器的情况。

 1） 如果选中了，那么以上面的公式来计权重。谁大听谁的。
 2） 如果没有选中，那么权重是0，因为继承的权重为0。



## 七、相对路径绝对路径

#### **绝对路径**

**绝对路径是指文件在硬盘上真正存在的路径**

  E:\Vip\css
  https://www.zhaoxiedu.net/static/imgs/companyInfo/Logo1.png

#### **相对路径：**

**相对于当前文件的目标文件位置**

./index.css

./logo.png

##### 相对路径 ./和../和/三种路径的区别:

  **./  当前目录**

  **../  父级目录**

  **/   根目录**



## 八、单位

## 绝对长度

绝对长度单位是固定的

| 单位 | 描述 |
| :--- | :--- |
| px   | 像素 |

## 相对长度

相对长度单位规定相对于另一个长度属性的长度

| 单位 | 描述                                                         |
| :--- | :----------------------------------------------------------- |
| em   | 相对于元素的字体大小（font-size）（2em 表示当前字体大小的 2 倍） |
| rem  | 相对于根元素的字体大小（font-size）（px/16=rem）             |
| vw   | 相对于视口*宽度的 1%                                         |
| vh   | 相对于视口*高度的 1%                                         |
| %    | 相对于父元素                                                 |

