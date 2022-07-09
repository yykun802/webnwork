## html总结
### 一、html简介

  1.html是==超文本标记语言==的缩写。
  2.==html==、==css==、==javascrip==三部分构成web程序。
  3.html不是一门编程语言，而是一种用于==定义内容结构的标记语言==。
  &nbsp;


###二、html文档结构
&lt;!DOCTYPE html>
&lt;html>
&lt;head>
  &emsp;&emsp;&lt;meta charset="utf-8">
  &emsp;&emsp;&lt;link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
 &emsp;&emsp;&lt;title>页面标题&lt;/title>
&lt;/head>
&lt;body>
  &emsp;&emsp;&lt;h1>我的第一个Web页&lt;/h1>
  &emsp;&emsp;&lt;p>当前有点丑：)&lt;/p>
&lt;/body>
&lt;/html>
&nbsp;


###三、html文档分析
&nbsp;
#####1剖析一个html元素
&lt;p>学好web&lt;/p >//这是一个html元素
&lt;p>是开始标签
&lt;/p>是结束标签
学好web是这个元素的内容
&nbsp;
（1）开始标签（Opening tag）：包含元素的名称（本例为 p），被左、右角括号所包围。表示元素从这里开始或者开始起作用 —— 在本例中即段落由此开始。
（2）结束标签（Closing tag）：与开始标签相似，只是其在元素名之前包含了一个斜杠。这表示着元素的结尾 —— 在本例中即段落在此结束。初学者常常会犯忘记包含结束标签的错误，这可能会产生一些奇怪的结果。
（3）内容（Content）：元素的内容，本例中就是所输入的文本本身。
==开始标签、结束标签与内容相结合，便是一个完整的元素。==
&nbsp;
#####2剖析一个html文档
(1)&lt;!DOCTYPE html>: 声明文档类型。出于历史原因需要，现在可有可无。
(2)&lt;html>&lt;/html>: &lt;html>元素。这个元素包裹了整个完整的页面，是一个==根==元素，其它元素都嵌套到其中。
(3)&lt;head>&lt;/head>: &lt;head>元素。 这个元素是一个容器，它包含了所有==你想包含在HTML页面中但不想在HTML页面中显示的内容==。这些内容包括你想在搜索结果中出现的关键字和页面描述，CSS样式，字符集声明等等。
(4)&lt;meta charset="utf-8">: 这个元素设置文档使用utf-8字符集编码，utf-8字符集包含了人类大部分的文字。基本上他能识别你放上去的所有文本内容。毫无疑问要使用它，并且它能在以后避免很多其他问题。
(5)&lt;link rel="shortcut icon" href="favicon.ico" type="image/x-icon">: 指定页面的图标，出现在浏览器标签上。(试一试：你可随意下载一个.ico图标文件到工作目录中)
(6)&lt;title>&lt;/title>: ==设置页面标题==，出现在浏览器标签上，当你标记/收藏页面时它可用来描述页面。
(7)&lt;body>&lt;/body>:&lt;body>元素。 ==包含你能在页面看到的所有内容==，包括文本，图片，音频，游戏等等。
###4. HTML 文档相关说明
####1.注释
用特殊的记号&lt;!--和-->包括起来进行注释， 比如：

&lt;p>我在注释外，可以显示！&lt;/p>
&lt;!-- &lt;p>我在注释内！浏览器将忽略我&lt;p> -->
==提示==： 输入Ctrl + /即可快捷的进行注释！

注意： HTML ==不区分标签的大小写==，但建议全部使用小写！

####2.空元素
&lt;br>, &lt;hr>, &lt;input>, &lt;img>, &lt;a>等等。我们称其为空元素，如下：
knnk
<!-- 换行 -->
&lt;p>我可以&lt;br>换行</p> 
<!-- 水平分割线 -->
&lt;hr>
<!-- 输入框 -->
&lt;input>
提示: 在上面代码中你看到&lt;br>元素放到&lt;p>元素之中——这被称作嵌套！

元素的属性
1.一个属性必须包含如下内容：
2.一个空格，在属性和元素名称之间。(如果已经有一个或多个属性，就与前一个属性之间有一个空格。)
3.属性名称，后面跟着一个 = 号。
1.一个属性值，由一对引号 "" 引起来。

###5.标题（heading）
一级标题&lt;h1>
二级标题&lt;h2>
三级标题&lt;h3>
四级标题&lt;h4>
五级标题&lt;h5>
....
作用：搜索引擎用标题来==索引页面的内容==
用户也习惯==以标题进行主要内容==浏览，以决定是否查看该页面
==提示==： 一级标题最醒目，应该用于页面的主标题，其次为二级标题，以此类推
==注意==： 不要因为希望醒目，试图使用标题对正文的文字进行放大或加粗。正文文字的醒目可以使用文本格式或 CSS 进行。
###6. 文本格式
注意： 除本节介绍的这些标签可用于文本的格式外，其它标签都不建议用来进行格式的设置，如：&lt;font>&lt;big>&lt;center>等标签皆为不推荐使用的。HTML 是用来表现页面内容而不是对页面进行修饰的，专门的页面美化需要使用后面将要学习的 CSS 。



###7. 超链接 a

超链接语法
&lt;a href="https://www.baidu.com/" target="_blank">百度一下</a>
==说明==：
1.href即为要跳转去的地址
2.target属性为_blank表示在新的页面打开超链接（默认是在当前页面打开即_self）
3.超链接标签包含的内容（当前为文字"百度一下"）即为显示在页面上供用户点击的
4.锚点，也称为书签，用于标记页面的某个元素或位置。通过锚点，我们可以轻易的在长页面内实现跳转。
5.先使用id属性生成某元素的锚点，然后再使用超链接指向该锚点即可。

==注意==：
元素的id值必须是唯一的，也即页面不能再有其它元素的id值为C4
超链接中的地址需要有#符号
###8. 图片及文件路径
在页面插入一张图片如下：

&lt;img src="https://mdbootstrap.com/img/logo/mdb192x192.jpg" alt="MDB Logo" width="200" height="200">
==说明==：
1.src属性为要显示图片文件的位置 URL，即图片文件的路径
2.alt属性当获取图片出现问题时显示的文字（占位符）
3.可为图片指定高宽度，但不建议（可能导致图片变形）
###9. 表格 Table
使用<table>标签：
<pre>

  &lt;table>
     &lt;tr>
      &lt;h>Firstname &lt;/th>
      &lt;th>Lastname&lt;/th>
      &lt;th>Age&lt;/th>
   &lt;/tr>
    &lt;tr>
      &lt;td>Jill&lt;/td>
      &lt;td>Smith&lt;/td>
      &lt;td>50&lt;/td>
    &lt;/tr>
   &lt;tr>
     &lt;td>Eve&lt;/td>
      &lt;td>Jackso&lt;/td>
      &lt;td>94&lt;/td>
    &lt;/tr>
  &lt;/table>
&lt;tr>表示行, &lt;td>表示行中的单元, &lt;th>是表头的单元
</pre>
###10. 列表 List
列表分为==有序列表==和==无序列表==
有序列表
<pre>
&lt;ol>
  &lt;li>Coffee&lt;/li>
  &lt;li>Tea&lt;/li>
  &lt;li>Milk&lt;/li>
&lt;/ol>
</pre>
无序列表
<pre>
&lt;ul>
 &lt;li>Coffee&lt;/li>
  &lt;li>Tea&lt;/li>
  &lt;li>Milk&lt;/li>
&lt;/ul>
</pre>
###11. 表单 Form
用户名、密码、选择买什么、买多少、提出意见等等,需要使用表单来填写
###12. 其它
#####1.区块元素
区块元素在浏览器显示时，新行来开始如：&lt;h1>, &lt;lipre>, &lt;liul>, &lt;litable>，&lt;lidiv> 等。
#####2.内联元素
内联总是一个接一个进行显示如： &lt;span>, &lt;input>, &lt;td>, &lt;a>, &lt;img>等。

#####3.预设格式

&lt;pre>
       内容格式      
&lt;/pre>


##css总结
###1. 何为 CSS
CSS是==级联样式表==的缩写。 
css的作用CSS 决定HTML这些内容该如何在屏幕上呈现。
###2. CSS 语法
选择器，以{}包裹的一条或多条声明
id 选择器
<pre>
sky{
  color: blue;
}
</pre>作用：页面上id为sky的那个元素让它呈现蓝色，
id 选择器适用范围只有一个元素。


class 选择器
<pre>
.center{
  text-align: center;
}
.large{
  font-size: 30px;
}
.red{
  color: red;
}
</pre>
只要页面上某元素的class为red，那么就让它呈现红色
###3. CSS 如何生效
生效方法：外部样式表、内部样式表、内联样式
级联的优先级
1.内联样式
2.内部样式表或外部样式表
3.浏览器缺省样式
###4. 颜色, 尺寸, 对齐

1.颜色
例：&lt;h3 style="background-color:Tomato;">Tomato&lt;/h3>

2.尺寸
我们可以用 height 和 width 设定元素内容占据的尺寸。常见的尺寸单位有：像数 px，百分比 %等。

例：CSS文件 ：

.example-1 {
  width: 100%;
  height: 200px;
  background-color: powderblue;
  text-align: center;
}
3.对齐
对于元素中的文本，我们可以简单的设置text-align属性为left, center, right即可。
###5. 盒子模型
盒子模型指的是一个 HTML 元素可以看作一个盒子。从内到外，这个盒子是由内容 content, 内边距 padding, 边框 border, 外边距 margin构成.
==说明==：
Content 盒子的内容，如文本、图片等
Padding 填充，也叫内边距，即内容和边框之间的区域
Border 边框，默认不显示
Margin 外边距，边框以外与其它元素的区域
###6. 边框与边距
提示：无论边框、内边距还是外边距，它们都有上下左右四个方向。

边框

.example-1 {
  border: 1px dotted black; /* 上下左右都相同 */
}
.example-2 {
  border-bottom: 1px solid blue; /* 只设置底部边框 */
}
.example-3 {
  border: 1px solid grey;
  border-radius: 15px; /* 边框圆角 */
}
.example-4 {
  border-left: 5px solid purple;
}
边距
内边距的设置：
padding: 20px; /* 上下左右都相同 */
padding-top: 20px;
padding-bottom: 100px;
padding-right: 50px;
padding-left: 80px;
padding: 25px 50px 75px 100px; /* 简写形式，按上，右，下，左顺序设置 */
padding: 25px 10px; /* 简写形式，上下为25px，左右为10px */

###7. 定位
(1).static 静态
设置为静态定位position: static;，这是元素的默认定位方式，也即你设置与否，元素都将按正常的页面布局进行
(2)relative 相对
设置为相对定位position: relative;，这将把元素相对于他的静态（正常）位置进行偏移
(3)fixed 固定
(4)absolute 绝对
设置为绝对定位position: absolute;，将使元素相对于其最近设置了定位属性（非static）的父元素进行偏移。
如果该元素的所有父元素都没有设置定位属性，那么就相对于<body>这个父元素
###8. 溢出
当元素内容超过其指定的区域时，我们通过溢出overflow属性来处理这些溢出的部分。
溢出属性有一下几个值：
(1)visible 默认值，溢出部分不被裁剪，在区域外面显示
(2)hidden 裁剪溢出部分且不可见
(3)scroll 裁剪溢出部分，但提供上下和左右滚动条供显示
auto 裁剪溢出部分，视情况提供滚动条
###9. 浮动
在一个区域或容器内，我们可以设置float属性让某元素水平方向上向左或右进行移动，其周围的元素也会重新排列。

==说明==一个元素浮动后，其后的元素将尽可能包围它，或者说出现在这个浮动元素的左或右方。
如果希望浮动元素后面的元素在其下方显示，可使用clear: both样式来进行清除。
###10. 不透明度
我们可以用opacity对任何元素（不过常用于图片）设置不透明度。
值在[0.0～1.0]之间，值越低，透明度越高。
###11. 组合选择器
后代选择器
子选择器
###12. 伪类和伪元素
伪类（pseudo-class）或伪元素（pseudo-element）用于定义元素的某种特定的状态或位置
比如我们可能有这样的需求：

鼠标移到某元素上变换背景颜色
超链接访问前后访问后样式不同
离开必须填写的输入框时出现红色的外框进行警示
保证段落的第一行加粗，其它正常
...
使用伪类/伪元素的语法如下：

/* 选择器后使用 : 号，再跟上某个伪类/伪元素 */
selector:pseudo-class/pseudo-element {
  property:value;
}