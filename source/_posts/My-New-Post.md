---
title: My New Post
date: 2020-04-25 23:38:49
categories:
 - 前端
---

## HTML基础

### 一、HTML5和HTML4的区别

#### 1、HTML5推出的原因：

|      |       HTML存在问题        |        HTML5解决方案         |
| :--: | :-----------------------: | :--------------------------: |
|  1   |   Web浏览器间的兼容性低   | 使各浏览器的功能符合通用标准 |
|  2   |     文档结构不够明确      |     增加与结构相关的元素     |
|  3   | Web应用程序的功能受到限制 |  提供供Web应用程序使用的API  |

#### 2、HTML5语法的改变：

- 内容类型不变：HTML5的文件扩展符（html或.htm）与内容类型（text/html）保持不变

- DOCTYPE声明变化：HTML4中需要指明是HTML的哪个版本，HTML5不需要，只使用<!DOCTYPE html>即可

- 指定字符编码变化：

  HTML4：

  ```html
  <meta http-equiv=‶content-type″ content=‶text/html; charset=UTF-8″>
  ```

  HTML5:

  ```html
  <meta charset=‶UTF-8″>
  ```

- 可以省略元素的标记：HTML5中很多元素标记可以省略

- 具有boolean值的属性调整：不指定属性值、属性名设定为属性值、字符串设为空时表示属性值为true；不写该属性表示属性值为false。

  ```html
  <input type=‶checkbox″ checked=‶checked″>          表示checked值为true
  
  <input type=‶checkbox″ checked=‶″>                      表示checked值为true
  
  <input type=‶checkbox″>                                       表示checked值为false
  ```

- 可省略引号：HTML5可省略指定属性值时的引号。


#### 3、 新增的元素和废除的元素：

新增结构元素

|      |  元素   |                             解释                             |
| :--: | :-----: | :----------------------------------------------------------: |
|  1   | section | 表示页面中内容块，如章节，页眉页脚等，可以和h1到h6结合表示文档结构 |
|  2   | article | 表示页面中一块与上下文不相关的独立内容，如博客中的一篇文章或报纸中的一篇文章 |
|  3   |  aside  |       表示article内容之外，与article内容相关的辅助信息       |
|  4   | header  |             表示页面中的区域块，通常用它表示标题             |
|  5   | hgroup  |              用于对整个页面或页面中标题进行整合              |
|  6   | footer  | 通常表示区域快的脚部或底部，用于承载作者姓名、创作日期等与作者的元素 |
|  7   |   nav   |                      表示页面中导航部分                      |
|  8   | figure  |    表示一段独立的流内容，一般表示主体流内容的一个独立单元    |

新增其他元素

|      |  元素  |                             解释                             |
| :--: | :----: | :----------------------------------------------------------: |
|  1   | video  |                  定义电影片段、视频流等视频                  |
|  2   | audio  |                       定义音乐或音频流                       |
|  3   | canvas | 画布，本身没有行为，仅提供一块画布，但它的API展现给JavaScript及脚本，能够把想绘制的东西绘制在canvas上 |

新增的input元素的类型

|      |  元素类型   |           意义           |
| :--: | :---------: | :----------------------: |
|  1   |    email    |  表示必须输的email地址   |
|  2   |     url     | 表示文本框输入的一个地址 |
|  3   |   number    |         表示数字         |
|  4   |    range    |      表示数字范围值      |
|  5   | DataPickers |   表示日历的日期、时间   |

废除的元素：能用css属性写出的元素（basefont，big，center，font等），不再使用frame框架，只有部分浏览器支持的元素

#### 4、 新增的属性和废除的属性

新增属性

|      |          属性          |                             作用                             |
| :--: | :--------------------: | :----------------------------------------------------------: |
|  1   |       autofocus        |                    页面加载后自动获得焦点                    |
|  2   |      placeholder       |                             提示                             |
|  3   |          form          |          声明元素属于哪个表单（值指向目标表单的id）          |
|  4   |        required        |                    提示用户输入域不能为空                    |
|  5   |      autocomplete      |                输入时的提示（邮箱补全提示等）                |
|  6   | img按钮的height和width |                       设置button的高宽                       |
|  7   |          list          | 与datalist标签配合使用（list为输入框法的属性，datalist标签设置提示，内涵option标签） |
|  8   |     max，min，step     |                 为输入包含日期的输入框作约束                 |
|  9   |        pattern         |          用于验证输入字段的模式，其实就是正则表达式          |
|  10  |        multiple        |     规定输入域中可选择多个值（适用于input[email,file]）      |
|  11  |        control         |           在lable中使用，可访问lable中表单元素的值           |
|  12  |      link的sizes       | sizes 属性规定被链接资源的尺寸。只有当被链接资源是图标时 (rel="icon")，才能使用该属性 |
|  13  |      ol的reversed      |            reversed是个bool属性，规定有序列表倒序            |
|  14  |     style的scoped      |           提供作用域，使用时在当前元素和子元素生效           |
|  15  |        mainfest        |                      下次断网时也可看见                      |

#### 5、全局属性

HTML5中新增全局属性的概念，全局属性指可以对任何元素都使用的属性

|      |    全局属性     |                             应用                             |
| :--: | :-------------: | :----------------------------------------------------------: |
|  1   | contentEditable | 允许用户编辑元素中内容，使用该属性的元素必须为可以获得鼠标焦点的元素，而且在点击鼠标后向用户提供一个插入符号，提示用户该元素允许进行编辑 |
|  2   |   designMode    | 用来指定整个页面是否可编辑，当页面可编辑时，页面中所有支持contentEditable属性的元素都变为可编辑状况。designMode属性只能在JavaScript脚本中被修改、编辑。属性值可取on（可编辑）或off（不可编辑） |
|  3   |     hidden      |  使元素不可见，但是浏览器渲染元素，在javascript中设置属性值  |

### 二、meta标签

#### 1、meta标签的实例

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
```

#### 2、meta标签的组成

`meta`标签共有两个属性：http-equiv属性和name属性

- http-equiv属性：相当于http的文件头作用，向浏览器传回一些有用的信息，使浏览器正确和精确地显示网页内容，与之对应的属性值为content（参数）

语法格式：＜meta http-equiv=”参数” content=”参数变量值”＞

实例：

```html
1.<meta http-equiv=”Set-Cookie” content=”cookievalue=xxx; expires=Friday,12-Jan-2001 18:18:18 GMT; path=/”>:如果网页过期，那么存盘的cookie将被删除。必须使用GMT的时间格式。
2.<meta http-equiv='expires' content='时间' >：用于设定网页的到期时间。一旦网页过期，必须到服务器上重新传输。
3.<meta http-equiv=”Refresh” content=”5;URL”>：告诉浏览器在【数字】秒后跳转到【一个网址】
4.<meta http-equiv=”content-Type” content=”text/html; charset=utf-8″>：设定页面使用的字符集。
  <meta charset=”utf-8″>：在HTML5中设定字符集的简写写法。
5.<meta http-equiv=”Pragma” content=”no-cache”>：禁止浏览器从本地计算机的缓存中访问页面内容。访问者将无法脱机浏览。
6.<meta http-equiv=”Window-target” content=”_top”>：用来防止别人在iframe(框架)里调用自己的页面，这也算是一个非常实用的属性。
7.<meta http-equiv='X-UA-Compatible' content='IE=edge,chrome=1'> :强制浏览器按照特定的版本标准进行渲染。但不支持IE7及以下版本。如果是ie浏览器就用最新的ie渲染，如果是双核浏览器就用chrome内核。
```

- name属性：用于描述网页，与之对应的属性值为content（便于搜索引擎机器人查找信息和分类信息）

语法格式：＜meta name=”参数” content=”具体的参数值”＞

实例：（对SEO比较重要的是ketwords和description）

```html
1.<meta name=”viewport” content=”width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no”>：在移动设备浏览器上，禁用缩放（zooming）功能，用户只能滚动屏幕。
2.<meta name=”description” content=””>：告诉搜索引擎，当前页面的主要内容是xxx。
3.<meta name=”keywords” content=””>：告诉搜索引擎，当前页面的关键字。
4.<meta name=”author” content=””>：告诉搜索引擎，标注网站作者是谁。
5.<meta name=”copyright” content=””>：标注网站的版权信息。
```

### 三、src和href的区别

#### 1、主要运用：

```html
引用css文件时：`href="cssfile.css"`
引用js文件时：`src="myscript.js"`
引用图片：`src="mypic.jpg"`
网站链接：`href="http://www.webpage.com"
```

#### 2、使用区别：

src用于替代这个元素，而href用于建立这个标签与外部资源之间的关系 

##### href (Hypertext Reference) 超文本引用：

指定web资源的位置，从而定义当前的锚点，当使用link引入时，css文件的加载是同时进行的，而使用@import引入的样式实在页面载入之后在加载的，推荐使用link而不是@import

##### src (Source)源：

这个属性是将资源嵌入到当前文档中元素所在的位置，原理是当执行这段代码时，会暂停页面的渲染知道加载完这个js文件或者img，所以推荐在文档最后引入文件

### 四、script标签中的async和defer

#### 1、问题：

当在HTML文件中使用script时，会按照顺序来执行脚本，在加载和执行过程过程中，会产生组赛后续的DOM渲染

#### 2、解决方案之defer：

执行是异步的，当执行HTML文件时，遇到script引入，开始下载，同时执行后面的操作，**在整个页面渲染完成后就执行**，多个defer按照顺序进行

#### 3、解决方案之async：

执行是异步的，当执行HTML文件时，遇到script引入，开始下载，同时执行后面的操作，**在下载完文件之后就进行加载**，多个async不一定按照顺序执行

### 五、块级元素和行内元素

#### 1、块级元素：

- 块级元素会独占一行
- 高度，行高，外边距和内边距可以单独设置
- 宽度默认是容器的100%
- 可以容纳内联元素和其他块级元素

```
常见的块级元素：<h1>~<h6>,<p>,<div>,<ul>,<ol>,<li>
```

#### 2、行内元素

- 和相邻的行内元素在一行上
- 高度和宽度无效，但是水平方向的padding和margin可以设置，垂直方向上无效
- 默认宽度为本身的宽度
- 行内元素只能容纳纯文本或者其他行内元素（a标签除外）

```
常见的行内元素有：<a>,<strong>,<b>,<em>,<del>,<span>等
```

#### 3、行内块级元素

- 和相邻的行内块在一行，但是会有间隙
- 默认宽肃为本身的宽度
- 高度，行高，内边距外边距都可以设置

```
在行内元素中有几个特殊的标签，<img/>,<input/>,<td/>,可以设置它们的宽高度以及对齐属性
```

#### 4、显示模式的转换

快转行内：

```html
display：inline;
```

行内转块：

```html
display: block;
```

块，行内转行内块：

```
display: inline-block;
```

