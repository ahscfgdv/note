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

**列表**

作用：布局内容排列整齐的区域。
列表分类：无序列表、有序列表、定义列表。

**无序列表**

作用：布局排列整齐的不需要规定顺序的区域。
标签：ul 嵌套 li，ul 是无序列表，li 是列表条目。
注意事项：
• ul 标签里面只能包裹 li 标签
• li 标签里面可以包裹任何内容

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>无序列表</title>
</head>
<body>
  <ul>
    <li>列表条目1</li>
    <li>列表条目2</li>
    <li>列表条目3</li>
  </ul>
</body>
</html>
```

**有序列表**

作用：布局排列整齐的需要规定顺序的区域。
标签：ol 嵌套 li，ol 是有序列表，li 是列表条目。

注意事项：
• ol 标签里面只能包裹 li 标签
• li 标签里面可以包裹任何内容

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>有序列表</title>
</head>
<body>
  <ol>
    <li>步骤1</li>
    <li>步骤2</li>
    <li>步骤3</li>
  </ol>
</body>
</html>
```

**定义列表**

标签：dl 嵌套 dt 和 dd，dl 是定义列表，dt 是定义列表的标题，dd 是定义列表的描述/ 详情。

注意事项：
• dl 里面只能包含dt 和 dd
• dt 和 dd 里面可以包含任何内容

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>定义列表</title>
</head>
<body>
  <dl>
    <dt>服务中心</dt>
    <dd>申请售后</dd>
    <dd>售后政策</dd>
  </dl>
</body>
</html>
```

**表格 – 基本用法**

表格 – 基本用法

**表格**

标签：table 嵌套 tr，tr 嵌套 td / th。

![images](./images/屏幕截图%202023-11-27%20130927.png)

提示：在网页中，表格默认没有边框线，使用 border 属性可以为表格添加边框线。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>表格-基本使用</title>
</head>
<body>
  <table border="1">
    <tr>
      <th>姓名</th>
      <th>语文</th>
      <th>数学</th>
      <th>总分</th>
    </tr>
    <tr>
      <td>张三</td>
      <td>99</td>
      <td>100</td>
      <td>199</td>
    </tr>
    <tr>
      <td>李四</td>
      <td>98</td>
      <td>100</td>
      <td>198</td>
    </tr>
    <tr>
      <td>总结</td>
      <td>全市第一</td>
      <td>全市第一</td>
      <td>全市第一</td>
    </tr>
  </table>
</body>
</html>
```

**表格结构标签**

作用：用表格结构标签把内容划分区域，让表格结构更清晰，语义更清晰。

![images](./images/屏幕截图%202023-11-27%20131042.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>表格结构标签</title>
</head>
<body>
  <table border="1">
    <thead>
      <tr>
        <th>姓名</th>
        <th>语文</th>
        <th>数学</th>
        <th>总分</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>张三</td>
        <td>99</td>
        <td>100</td>
        <td>199</td>
      </tr>
      <tr>
        <td>李四</td>
        <td>98</td>
        <td>100</td>
        <td>198</td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <td>总结</td>
        <td>全市第一</td>
        <td>全市第一</td>
        <td>全市第一</td>
      </tr>
    </tfoot>
  </table>
</body>
</html>
```

**合并单元格**

作用：将多个单元格合并成一个单元格，以合并同类信息。

合并单元格的步骤：

1. 明确合并的目标
2. 保留最左最上的单元格，添加属性（取值是数字，表示需要合并的单元格数量）
  – 跨行合并，保留最上单元格，添加属性 rowspan
  – 跨列合并，保留最左单元格，添加属性 colspan
3. 删除其他单元格
注意：不能跨表格结构标签合并单元格（thead、tbody、tfoot）

![images](./images/屏幕截图%202023-11-27%20131334.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>表格结构标签</title>
</head>
<body>
  <table border="1">
    <thead>
      <tr>
        <th>姓名</th>
        <th>语文</th>
        <th>数学</th>
        <th>总分</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>张三</td>
        <td>99</td>
        <td rowspan="2">100</td>
        <td>199</td>
      </tr>
      <tr>
        <td>李四</td>
        <td>98</td>
        <!-- <td>100</td> -->
        <td>198</td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <td>总结</td>
        <td colspan="3">全市第一</td>
        <!-- <td>全市第一</td>
        <td>全市第一</td> -->
      </tr>
    </tfoot>
  </table>
</body>
</html>
```

**表单**

作用：收集用户信息。
使用场景：
• 登录页面
• 注册页面
• 搜索区域

**input 标签基本使用**

input 标签 type 属性值不同，则功能不同。

![images](./images/屏幕截图%202023-11-27%20131549.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>input基本使用</title>
</head>
<body>
  <!-- 特点：输入什么就显示什么 -->
  文本框：<input type="text">
  <br><br>
  <!-- 特点：输入什么都是以 点 的形式显示 -->
  密码框：<input type="password">
  <br><br>
  单选框：<input type="radio">
  <br><br>
  多选框：<input type="checkbox">
  <br><br>
  上传文件：<input type="file">
</body>
</html>
```

**input 标签占位文本**

占位文本：提示信息。
文本框和密码框都可以使用。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>input占位文本</title>
</head>
<body>
  文本框：<input type="text" placeholder="请输入用户名">
  <br><br>
  密码框：<input type="password" placeholder="请输入密码">
</body>
</html>
```

**单选框 radio**

![images](./images/屏幕截图%202023-11-27%20131826.png)

提示：name 属性值自定义。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>单选框</title>
</head>
<body>
  性别：
  <input type="radio" name="gender"> 男
  <input type="radio" name="gender" checked> 女
</body>
</html>
```

**上传文件 - file**

默认情况下，文件上传表单控件只能上传一个文件，添加 multiple 属性可以实现文件多选功能。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>上传多个文件</title>
</head>
<body>
  上传文件：<input type="file" multiple>
</body>
</html>
```

**下拉菜单**

标签：select 嵌套 option，select 是下拉菜单整体，option是下拉菜单的每一项。
默认显示第一项，selected 属性实现默认选中功能

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>下拉菜单</title>
</head>
<body>
  城市：
  <select>
    <option>北京</option>
    <option>上海</option>
    <option>广州</option>
    <option>深圳</option>
    <option selected>武汉</option>
  </select>
</body>
</html>
```

**文本域**

作用：多行输入文本的表单控件
标签：textarea，双标签。
注意点：
• 实际开发中，使用 CSS 设置 文本域的尺寸
• 实际开发中，一般禁用右下角的拖拽功能

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>文本域</title>
</head>
<body>
  <!-- 工作中，使用 CSS 禁用右下角的拖拽功能；使用 CSS 设置尺寸 -->
  <textarea>请输入评论</textarea>
</body>
</html>
```

**label 标签**

作用：网页中，某个标签的说明文本。
经验：用 label 标签绑定文字和表单控件的关系，增大表单控件的点击范围。

**label 标签 – 增大点击范围**

写法一

- label 标签只包裹内容，不包裹表单控件
- 设置 label 标签的 for 属性值 和表单控件的 id 属性值相同

写法二

- 使用 label 标签包裹文字和表单控件，不需要属性
提示：支持 label 标签增大点击范围的表单控件：文本框、密码框、上传文件、单选框、多选框、下拉菜单、文本域等等。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>label标签</title>
</head>
<body>
  性别：
  <input type="radio" name="gender" id="man"> <label for="man">男</label>
  <label><input type="radio" name="gender"> 女</label>
</body>
</html>
```

**按钮 - button**

type属性值：

![images](./images/屏幕截图%202023-11-27%20132620.png)

提示：
• 注意：按钮需配合 form 标签（表单区域）才能实现对应的功能。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>按钮</title>
</head>
<body>
  <!-- form 表单区域 -->
  <!-- action="" 发送数据的地址 -->
  <form action="">
    用户名：<input type="text">
    <br><br>
    密码：<input type="password">
    <br><br>

    <!-- 如果省略 type 属性，功能是 提交 -->
    <button type="submit">提交</button>
    <button type="reset">重置</button>
    <button type="button">普通按钮</button>
  </form>
</body>
</html>
```

**无语义的布局标签**

作用：布局网页（划分网页区域，摆放内容）

- div：独占一行
- span：不换行

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>div 和 span</title>
</head>
<body>
  <!-- div：大盒子 -->
  <div>这是 div 标签</div>
  <div>这是 div 标签</div>
  <!-- span：小盒子 -->
  <span>这是 span 标签</span>
  <span>这是 span 标签</span>
</body>
</html>
```

**字符实体**

当在HTML中需要显示特殊字符时，可以使用字符实体来代替这些字符。以下是一些常用字符实体及其对应的代码：

1. **小于号 (<)**
   - 实体名称：`&lt;`
   - 实体代码：`&#60;` 或 `&#x3C;`

2. **大于号 (>)**
   - 实体名称：`&gt;`
   - 实体代码：`&#62;` 或 `&#x3E;`

3. **和号 (&)**
   - 实体名称：`&amp;`
   - 实体代码：`&#38;` 或 `&#x26;`

4. **引号 (")**
   - 实体名称：`&quot;`
   - 实体代码：`&#34;` 或 `&#x22;`

5. **单引号 (')**
   - 实体名称：`&apos;` (在HTML5中)
   - 实体代码：`&#39;` 或 `&#x27;`

6. **版权符号 (©)**
   - 实体名称：`&copy;`
   - 实体代码：`&#169;` 或 `&#xA9;`

7. **注册商标符号 (®)**
   - 实体名称：`&reg;`
   - 实体代码：`&#174;` 或 `&#xAE;`

8. **非断空格 ( )**
   - 实体名称：`&nbsp;`
   - 实体代码：`&#160;` 或 `&#xA0;`

9. **欧元符号 (€)**
   - 实体名称：`&euro;`
   - 实体代码：`&#8364;` 或 `&#x20AC;`

10. **英镑符号 (£)**
    - 实体名称：`&pound;`
    - 实体代码：`&#163;` 或 `&#xA3;`

这些字符实体或实体代码可以在HTML文档中直接使用，浏览器会将其解析成对应的特殊字符进行显示。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>字符实体</title>
</head>
<body>
  <!-- 在代码中敲键盘的空格，网页只识别一个 -->
  乾坤未定，你我皆是黑&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;马。
  &lt;p&gt;
</body>
</html>
```

**体育新闻**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>体育新闻</title>
</head>
<body>
  <ul>
    <li>
      <img src="./images/1.jpg" alt="">
      <h3>主帅安东尼奥回西班牙休假 国青抵达海口进行隔离</h3>
    </li>
    <li>
      <img src="./images/2.jpg" alt="">
      <h3>梅州主帅：申花有强有力的教练组 球员体能水平高</h3>
    </li>
    <li>
      <img src="./images/3.jpg" alt="">
      <h3>马德兴:00后球员将首登亚洲舞台 调整心态才务实</h3>
    </li>
  </ul>
</body>
</html>
```

**注册页面**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>注册信息</title>
</head>
<body>
  <h1>注册信息</h1>
  <form action="">
    <!-- 表单控件 -->
    <!-- 个人信息 -->
    <h2>个人信息</h2>
    <label>姓名：</label><input type="text" placeholder="请输入真实姓名">
    <br><br>
    <label>密码：</label><input type="password" placeholder="请输入密码">
    <br><br>
    <label>确认密码：</label><input type="password" placeholder="请输入确认密码">
    <br><br>
    <label>性别：</label>
    <label><input type="radio" name="gender"> 男</label>
    <label><input type="radio" name="gender" checked> 女</label>
    <br><br>
    <label>居住城市：</label>
    <select>
      <option>北京</option>
      <option>上海</option>
      <option>广州</option>
      <option>深圳</option>
      <option>武汉</option>
    </select>
    <!-- 教育经历 -->
    <h2>教育经历</h2>
    <label>最高学历：</label>
    <select>
      <option>博士</option>
      <option>硕士</option>
      <option>本科</option>
      <option>大专</option>
    </select>
    <br><br>
    <label>学校名称：</label><input type="text">
    <br><br>
    <label>所学专业：</label><input type="text">
    <br><br>
    <label>在校时间：</label>
    <select>
      <option>2015</option>
      <option>2016</option>
      <option>2017</option>
      <option>2018</option>
    </select>
    --
    <select>
      <option>2019</option>
      <option>2020</option>
      <option>2021</option>
      <option>2022</option>
    </select>
    <!-- 工作经历 -->
    <h2>工作经历</h2>
    <label>公司名称：</label><input type="text">
    <br><br>
    <label>工作描述：</label>
    <br>
    <textarea></textarea>
    <br><br>
    <!-- 协议 和 按钮 -->
    <input type="checkbox"><label>已阅读并同意以下协议：</label>
    <ul>
      <li><a href="#">《用户服务协议》</a></li>
      <li><a href="#">《隐私政策》</a></li>
    </ul>
    <br><br>
    <button>免费注册</button>
    <button type="reset">重新填写</button>
  </form>
</body>
</html>
```
