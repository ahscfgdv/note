# html

**HTML 定义**

HTML 超文本标记语言——HyperText Markup Language。
• 超文本是什么？链接
• 标记是什么？标记也叫标签，带尖括号的文本

**标签语法：**

标签成对出现，中间包裹内容
<>里面放英文字母（标签名）
结束标签比开始标签多 /
拓展
双标签：成对出现的标签
单标签：只有开始标签，没有结束标签

**HTML 基本骨架**

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>网页标题</title>
</head>
<body>
  给用户看的内容
</body>
</html>
```

html：整个网页
head：网页头部，用来存放给浏览器看的信息，例如CSS
title：网页标题
body：网页主体，用来存放给用户看的信息，例如图片、文字

**标签的关系**

```html
<html>
  <head>
    <title></title>
  </head>
  <body>
    
  </body>
</html>
```

作用：明确标签的书写位置；让代码格式更整齐
父子关系（嵌套关系）
兄弟关系（并列关系）

父子关系：子级标签换行且缩进（Tab键）
兄弟关系：兄弟标签换行要对齐

**注释**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <!-- 这是文字，能看见吗？变成了注释，浏览器不显示 -->
  <strong>这是加粗的strong</strong>
</body>
</html>
```

在 VS Code 中，添加 / 删除注释的快捷键：Ctrl + /

## 基本标签

**标题标签**

标签名：h1 ~ h6（双标签）
显示特点：
• 文字加粗
• 字号逐渐减小
• 独占一行（换行）

经验分享：
• h1 标签在一个网页中只能用一次，用来放新闻标题或网页的 logo
• h2 ~ h6 没有使用次数的限制

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <h1>一级标题</h1>
  <h2>二级标题</h2>
  <h3>三级标题</h3>
  <h4>四级标题</h4>
  <h5>五级标题</h5>
  <h6>六级标题</h6>
</body>
</html>
```

**段落标签**

标签名：p（双标签）
显示特点：
• 独占一行
• 段落之间存在间隙

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
</body>
</html>
```

**换行与水平线标签**

换行：`<br>`（单标签）
水平线：`<hr>`（单标签）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>换行与水平线标签</title>
</head>
<body>
  第一行内容
  <br>
  <br>
  第二行内容
  <hr>
</body>
</html>
```

**文本格式化标签**

作用：为文本添加特殊格式，以突出重点。常见的文本格式：加粗、倾斜、下划线、删除线等。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <strong>strong 加粗</strong>
  <b>b 加粗</b>
  <em>em 倾斜</em>
  <i>i 倾斜</i>
  <ins>ins 下划线</ins>
  <u>u 下划线</u>
  <del>del 删除线</del>
  <s>s 删除线</s>
</body>
</html>
```

**图像标签**

作用：在网页中插入图片。
`<img src="图片的 URL">`
src用于指定图像的位置和名称，是 `<img>` 的必须属性。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>图像-基本使用</title>
</head>
<body>
  <img src="./cat.jpg">
</body>
</html>
```

**图像标签-属性**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>图像-属性</title>
</head>
<body>
  <!-- 以前网速慢，可能导致图片加载不出来，不想影响网页内容的浏览，用alt替换 -->
  <img src="./cat1.jpg" alt="这是一只猫">

  <img src="./dog.jpg" title="这是一只狗">

  <!-- 浏览器缩放图片，默认是等比例缩放 -->
  <img src="./cat.jpg" width="100">

  <img src="./dog.jpg" height="600">
</body>
</html>
```

**路径**

路径指的是查找文件时，从起点到终点经历的路线。
路径分类：
• 相对路径：从当前文件位置出发查找目标文件
• 绝对路径：从盘符出发查找目标文件

相对路径 -从当前文件位置出发查找目标文件
/ 表示进入某个文件夹里面
. 表示当前文件所在文件夹
.. 表示当前文件的上一级文件夹

绝对路径 -从盘符出发查找目标文件
Windows 电脑从盘符出发 `C:\images\mao.jpg`
Mac 电脑从根目录（/）出发
Windows 默认是 \ ，其他系统是 /，建议统一写为 /

**超链接**

作用：点击跳转到其他页面。
`<a href="https://www.baidu.com">跳转到百度</a>`
href 属性值是跳转地址，是超链接的必须属性。
超链接默认是在当前窗口跳转页面，添加 target="_blank" 实现新窗口打开页面。
拓展：开发初期，不确定跳转地址，则 href 属性值写为 #，表示空链接，页面不会跳转，在当前页面刷新一次。

**音频标签**

`<audio src="音频的 URL"></audio>`

![images](./images/屏幕截图%202023-11-26%20193532.png)

**个人简介**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>个人简介</title>
</head>
<body>
  <h1>尤雨溪</h1>
  <hr>
  <p>尤雨溪，前端框架<a href="../17-综合案例二/vue简介.html">Vue.js</a>的作者，<a href="#">HTML5</a>版Clear的打造人，独立开源开发者。曾就职于Google Creative Labs和Meteor Development Group。由于工作中大量接触开源的项目<a href="#">JavaScript</a>，最后自己也走上了开源之路，现全职开发和维护<a href="#">Vue.js</a>。

  </p>
  <img src="./photo.jpg" alt="尤雨溪的照片" title="尤雨溪">
  <h2>学习经历</h2>
  <p>尤雨溪毕业于上海复旦附中，在美国完成大学学业，本科毕业于Colgate University，后在Parsons设计学院获得Design & Technology艺术硕士学位，任职于纽约Google Creative Lab。</p>
  <h2>主要成就</h2>
  <p>尤雨溪<strong>大学专业并非是计算机专业</strong>，在大学期间他学习专业是室内艺术和艺术史，后来读了美术设计和技术的硕士， <ins>正是在读硕士期间，他偶然接触到了JavaScript ，从此被这门编程语言深深吸引，开启了自己的前端生涯</ins> 。</p>
  <p>2014年2月，开发了一个前端开发库Vue.js。Vue.js 是构建 Web 界面的 JavaScript 框架，是一个通过简洁的API提供高效的数据绑定和灵活的组件系统。</p>
  <h2>社会任职</h2>
  <p>2016年9月3日，在南京的JSConf上，Vue作者尤雨溪正式宣布加盟阿里巴巴Weex团队，尤雨溪称他将以技术顾问的身份加入Weex团队来做 Vue 和 Weex 的 JavaScript runtime 整合，目标是让大家能用 Vue 的语法跨三端。</p>
</body>
</html>
```

**vue简介**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Vue 简介</title>
</head>
<body>
  <h1>Vue.js</h1>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>其作者为<a href="../16-综合案例一/个人简介.html" target="_blank">尤雨溪</a></p>
  <h2>主要功能</h2>
  <p>Vue.js是一套构建用户界面的渐进式框架。与其他重量级框架不同的是，Vue采用自底向上增量开发的设计。Vue 的核心库只关注视图层，并且非常容易学习，非常容易与其它库或已有项目整合。另一方面，Vue 完全有能力驱动采用单文件组件和Vue生态系统支持的库开发的复杂单页应用。</p>
  <p>Vue.js 的目标是通过尽可能简单的 API 实现响应的数据绑定和组合的视图组件。</p>
  <p>Vue.js 自身不是一个全能框架——它只聚焦于视图层。因此它非常容易学习，非常容易与其它库或已有项目整合。另一方面，在与相关工具和支持库一起使用时 [2] ，Vue.js 也能驱动复杂的单页应用。</p>
  <video src="../media/vue.mp4" controls></video>
</body>
</html>
```

## 列表，表格，表单

![images]()
