# CSS

## CSS 初体验

**CSS 定义**

层叠样式表 (Cascading Style Sheets，缩写为 CSS)，是一种 样式表 语言，用来描述HTML 文档的呈现（美化内容）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>初识 CSS</title>
  <style>
    /* CSS 代码 */
    /* 选择器 { CSS 属性} */
    /* 属性名和属性值成对出现 → 键值对 */
    p {
      /* 文字颜色 */
      color: red;
      /* 字号 */
      font-size: 30px;
    }
  </style>
</head>
<body>
  <p>体验 CSS</p>
</body>
</html>
```

## CSS 引入方式

**CSS 引入方式**

内部样式表：学习使用

- CSS 代码写在 style 标签里面

外部样式表：开发使用

- CSS 代码写在单独的 CSS 文件中（.css）
  在 HTML 使用 link 标签引入
  行内样式：配合 JavaScript 使用
  CSS 写在标签的 style 属性值里

行内样式：配合 JavaScript 使用

- CSS 写在标签的 style 属性值里

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS 引入方式</title>
  <!-- link 引入外部样式表； rel：关系，样式表 -->
  <link rel="stylesheet" href="./my.css">
</head>
<body>
  <p>这是 p 标签</p>
  <!-- 行内，style=" CSS" -->
  <div style="color: green; font-size: 30px;">这是 div 标签</div>
</body>
</html>
```

## 选择器

作用：查找标签，设置样式。
基础选择器

- 标签选择器
- 类选择器
- id 选择器
- 通配符选择器

**标签选择器**

标签选择器：使用标签名作为选择器 → 选中同名标签设置相同的样式。
例如：p, h1, div, a
注意：标签选择器无法差异化同名标签的显示效果。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>标签选择器</title>
  <style>
    /* 特点：选中同名标签设置相同的样式，无法差异化同名标签的样式 */
    p {
      color: red;
    }
  </style>
</head>
<body>
  <p>这是 p 标签</p>
  <p>1111</p>
  <p>2222</p>
</body>
</html>
```

**类选择器**

作用：查找标签，差异化设置标签的显示效果。
步骤：

- 定义类选择器 → .类名
- 使用类选择器 → 标签添加 class="类名“

注意：

- 类名自定义，不要用纯数字或中文，尽量用英文命名
- 一个类选择器可以供多个标签使用
- 一个标签可以使用多个类名，类名之间用空格隔开

开发习惯：类名见名知意，多个单词可以用 - 连接，例如：news-hd

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>类选择器</title>
  <style>
    /* 定义 */
    .red {
      color: red;
    }

    .size {
      font-size: 50px;
    }
  </style>
</head>
<body>
  <!-- 使用 -->
  <!-- 一个类选择器可以给多个标签使用 -->
  <p class="red">111111</p>
  <p>222222</p>
  <!-- 一个标签可以使用多个类名，class属性值写多个类名，类名用空格隔开 -->
  <div class="red size">div 标签</div>
</body>
</html>
```

**id选择器**

作用：查找标签，差异化设置标签的显示效果。
场景：id 选择器一般配合 JavaScript 使用，很少用来设置 CSS 样式
步骤：

- 定义 id 选择器 → #id名
- 使用 id 选择器 → 标签添加 id= "id名"

规则：

- 同一个 id 选择器在一个页面只能使用一次

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>id选择器</title>
  <style>
    /* 定义 */
    #red {
      color: red;
    }
  </style>
</head>
<body>
  <!-- 使用 -->
  <div id="red">div 标签</div>
</body>
</html>
```

**通配符选择器**

作用：查找页面所有标签，设置相同样式。
通配符选择器： *，不需要调用，浏览器自动查找页面所有标签，设置相同的样式

经验：

- 通配符选择器可以用于清除标签的默认样式，例如：标签默认的外边距、内边距

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>通配符选择器</title>
  <style>
    * {
      color: red;
    }
  </style>
</head>
<body>
  <p>p 标签</p>
  <div>div 标签</div>
  <h1>h1 标签</h1>
  <ul>
    <li>li</li>
    <li>li</li>
    <li>li</li>
  </ul>
  <strong>strong</strong>
</body>
</html>
```

**画盒子**

目标：使用合适的选择器画盒子
新属性

![images](./images/屏幕截图%202023-11-27%20135447.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>画盒子</title>
  <style>
    .red {
      /* 宽度 */
      width: 100px;
      /* 高度 */
      height: 100px;
      /* 背景色 */
      background-color: brown;
    }

    .orange {
      width: 200px;
      height: 200px;
      background-color: orange;
    }
  </style>
</head>
<body>
  <div class="red">div1</div>
  <div class="orange">div2</div>
</body>
</html>
```

## 文字控制属性

![images](./images/屏幕截图%202023-11-27%20135655.png)

**字体大小**

属性名：font-size
属性值：文字尺寸，PC 端网页最常用的单位 px
经验：谷歌浏览器默认字号是16px

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>字体大小</title>
  <style>
    /* 经验：谷歌浏览器文字有默认大小 16px */
    p {
      /* font-size 属性必须有单位，否则属性不生效 */
      font-size: 30px;
    }
  </style>
</head>
<body>
  <p>测试字体大小</p>
  <div>测试默认字体大小</div>
</body>
</html>
```

**字体粗细**

属性名：font-weight
属性值

- 数字（开发使用）
- 关键字

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>字体粗细</title>
  <style>
    h3 {
      font-weight: 400;
    }

    div {
      font-weight: 700;
    }
  </style>
</head>
<body>
  <h3>h3 标题</h3>
  <div>div 标签</div>
</body>
</html>
```

**字体样式**

作用：清除文字默认的倾斜效果
属性名：font-style
属性值

- 正常（不倾斜）：normal
- 倾斜：italic

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>字体倾斜</title>
  <style>
    em {
      font-style: normal;
    }

    div {
      font-style: italic;
    }
  </style>
</head>
<body>
  <em>em 标签</em>
  <div>div 标签</div>
</body>
</html>
```

**行高**

作用：设置多行文本的间距
属性名：line-height
属性值

- 数字 + px
- 数字（当前标签font-size属性值的倍数）

行高的测量方法：从一行文字的最顶端（最底端）量到下一行文字的最顶端（最底端）。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>行高</title>
  <style>
    p {
      font-size: 20px;
      /* line-height: 30px; */
      /* 行高值是数字，表示是当前标签字体大小的倍数 */
      line-height: 2;
    }
  </style>
</head>
<body>
  <p>今年受成本驱动、需求拉动以及全球粮价上涨等各种因素叠加影响，我国粮食价格整体上扬，小麦、玉米、大豆价格高位波动，水稻价格运行平稳，优质优价特征明显，农民择机择时售粮，实现种粮收益最大化。但种粮成本持续攀升成为影响农民增收的“拦路虎”。这是因为，在去年高粮价的刺激下，今年土地租金以及化肥、农药、柴油等农资价格大幅上涨，种粮成本随之增加。加之今年粮食生产遭遇去年北方罕见秋雨秋汛、今年“南旱北涝”等极端天气，虽然没有带来灾害性后果，但一些农户为抗灾付出更多生产成本，种粮农户收益空间进一步收窄。</p>
</body>
</html>
```

**行高-垂直居中**

垂直居中技巧：行高属性值等于盒子高度属性值
注意：该技巧适用于单行文字垂直居中效果

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>垂直居中</title>
  <style>
    div {
      height: 100px;
      background-color: skyblue;

      /* 注意：只能是单行文字垂直居中 */
      line-height: 100px;
    }
  </style>
</head>
<body>
  <div>文字</div>
</body>
</html>
```

**字体族**

属性名：font-family
属性值：字体名
拓展（了解）：font-family属性值可以书写多个字体名，各个字体名用逗号隔开，执行顺序是从左向右依次查找• font-family 属性最后设置一个字体族名，网页开发建议使用无衬线字体

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>字体族</title>
  <style>
    div {
      font-family: 楷体;
    }
  </style>
</head>
<body>
  <div>测试文字</div>
</body>
</html>
```

**font 复合属性**

![images](./images/屏幕截图%202023-11-27%20140457.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>font 属性</title>
  <style>
    /* 文字倾斜、文字加粗、字体大小是30px、行高2倍、楷体 */ 
    div {
      /* font: italic 700 30px/2 楷体; */

      /* font 属性必须写字号和字体，否则 属性不生效 */
      font: 30px 楷体;
      /* font: italic 700 30px/2; */
    }
  </style>
</head>
<body>
  <div>测试 font 属性</div>
</body>
</html>
```

**文本缩进**

属性名：text-indent
属性值：

- 数字 + px
- 数字 + em（推荐：1em = 当前标签的字号大小）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>文本缩进</title>
  <style>
    p {
      text-indent: 2em;
      font-size: 30px;
    }
  </style>
</head>
<body>
  <p>今年受成本驱动、需求拉动以及全球粮价上涨等各种因素叠加影响，我国粮食价格整体上扬，小麦、玉米、大豆价格高位波动，水稻价格运行平稳，优质优价特征明显，农民择机择时售粮，实现种粮收益最大化。但种粮成本持续攀升成为影响农民增收的“拦路虎”。这是因为，在去年高粮价的刺激下，今年土地租金以及化肥、农药、柴油等农资价格大幅上涨，种粮成本随之增加。加之今年粮食生产遭遇去年北方罕见秋雨秋汛、今年“南旱北涝”等极端天气，虽然没有带来灾害性后果，但一些农户为抗灾付出更多生产成本，种粮农户收益空间进一步收窄。</p>
</body>
</html>
```

**文本对齐方式**

作用：控制内容水平对齐方式
属性名：text-align
属性值

![images](./images/屏幕截图%202023-11-27%20140719.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>文本对齐方式</title>
  <style>
    h1 {
      /* 本质：居中的是文字内容，不是标签 */
      /* text-align: left; */
      text-align: center;
      /* text-align: right; */
    }
  </style>
</head>
<body>
  <h1>标题文字</h1>
</body>
</html>
```

**水平对齐方式 – 图片**

text-align本质是控制内容的对齐方式，属性要设置给内容的父级

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>图片对齐方式</title>
  <style>
    div {
      text-align: center;
    }
  </style>
</head>
<body>
  <div>
    <img src="./images/1.jpg" alt="">
  </div>
</body>
</html>
```

**文本修饰线**

属性名： text-decoration
属性值

![images](./images/屏幕截图%202023-11-27%20140912.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>文本修饰线</title>
  <style>
    a {
      /* 无，去掉修饰线 */
      text-decoration: none;
    }

    div {
      /* 下划线 */
      text-decoration: underline;
    }

    p {
      text-decoration: line-through;
    }

    span {
      text-decoration: overline;
    }
  </style>
</head>
<body>
  <a href="#">a 标签，去掉下划线</a>
  <div>div 标签，添加下划线</div>
  <p>p 标签，添加删除线</p>
  <span>span 标签，添加顶划线</span>
</body>
</html>
```

**color 文字颜色**

属性名：color
属性值

![images](./images/屏幕截图%202023-11-27%20141156.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>文字颜色</title>
  <style>
    h1 {
      background-color: aqua;
      /* color: red; */
      /* color: rgb(0,255,0); */
      /* color: rgba(0,0,0,0.8); */
      /* color: #0000ff; */
      color: #00f;
    }
  </style>
</head>
<body>
  <h1>h1 标签</h1>
</body>
</html>
```

**调试工具 – 谷歌浏览器**

作用：检查、调试代码；帮助程序员发现代码问题、解决问题

1. 打开调试工具
    浏览器窗口内任意位置 / 选中标签 → 鼠标右键 → 检查
    F12
2. 使用调试工具

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>调试工具</title>
  <style>
    /* 
      调试工具的细节
      1. 如果是错误的属性，有黄色叹号
      2. CSS 属性的前面有多选框，如果勾选：这个属性生效； 如果没有勾选：这个属性不生效
    */
    div {
      color: red;
      font-size: 66;
    }
  </style>
</head>
<body>
  <div>测试文字</div>
</body>
</html>
```

## 综合案例

**综合案例一 – 新闻详情**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>新闻详情</title>
  <style>
    h1 {
      text-align: center;
      font-weight: 400;
      font-size: 30px;
      color: #333;
    }

    div {
      font-size: 14px;
      color: #999;
    }

    p {
      text-indent: 2em;
      font-size: 18px;
      color: #333;
    }

    /* div {
      text-align: center;
    } */

    .pic {
      text-align: center;
    }
  </style>
</head>
<body>
  <h1>在希望的田野上 | 湖北秋收开镰 各地多举措保增产增收</h1>
  <div>来源：央视网 | 2222年12月12日 12:12:12</div>
  <p><strong>央视网消息：</strong>眼下，湖北省秋收开镰已有一周多的时间。水稻收割已经超过四成，玉米收割七成。湖北省通过大力推广新品种水稻，建设高标准农田等一系列措施，为秋粮稳产提供有力支撑。</p>
  <p>中稻占据了湖北全年粮食产量的一半以上。在湖北的主产区荆门市，370万亩中稻已经收割四成以上。</p>
  <div class="pic">
    <img src="./1.jpg" alt="">
  </div>
  <p>王化林说的新品种，是湖北省研发的杂交水稻“华夏香丝”，不仅产量高，还具有抗病、抗倒、抗高温的特性。在荆门漳河镇的一工程示范田内，像“华夏香丝”这样抗旱节水的品种还有20多个，这些水稻新品将在荆门全面推广，确保来年增产增收。</p>
  <p>此外，湖北还大力推进高标准农田建设。截至今年6月，已建成3980万亩高标准农田。目前，湖北全省仍有1800多万亩中稻正在有序收割中，预计10月中旬收割完毕。</p>
</body>
</html>
```

**综合案例二 – CSS 简介**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS 简介</title>
  <style>
    h1 {
      color: #333;
    }

    p {
      text-indent: 2em;
      font-size: 14px;
      color: #444;
      line-height: 30px;
    }

    a {
      color: #0069c2;
    }

    li {
      font-size: 14px;
      color: #444;
      line-height: 30px;
    }
  </style>
</head>
<body>
  <h1>CSS（层叠样式表）</h1>
  <p>层叠样式表 (Cascading Style Sheets，缩写为 CSS），是一种 <a href="#">样式表</a> 语言，用来描述 HTML 或 XML（包括如 SVG、MathML、XHTML 之类的 XML 分支语言）文档的呈现。CSS 描述了在屏幕、纸质、音频等其它媒体上的元素应该如何被渲染的问题。</p>
  <p><strong>CSS 是开放网络的核心语言之一</strong>，由 W3C 规范 实现跨浏览器的标准化。CSS 节省了大量的工作。 样式可以通过定义保存在外部.css 文件中，同时控制多个网页的布局，这意味着开发者不必经历在所有网页上编辑布局的麻烦。CSS 被分为不同等级：CSS1 现已废弃， CSS2.1 是推荐标准， CSS3 分成多个小模块且正在标准化中。</p>
  <ul>
    <li>CSS 介绍 如果你是 Web 开发的新手，请务必阅读我们的 CSS 基础 文章以学习 CSS 的含义和用法。</li>
    <li>CSS 教程 我们的 CSS 学习区 包含了丰富的教程，它们覆盖了全部基础知识，能使你在 CSS 之路上从初出茅庐到游刃有余。</li>
    <li>CSS 参考 针对资深 Web 开发者的 <a href="#">详细参考手册</a> ，描述了 CSS 的各个属性与概念。</li>
  </ul>
</body>
</html>
```

## 复合选择器

**复合选择器**

定义：由两个或多个基础选择器，通过不同的方式组合而成。
作用：更准确、更高效的选择目标元素（标签）

**后代选择器**

后代选择器：选中某元素的后代元素。
选择器写法：父选择器 子选择器 { CSS 属性}，父子选择器之间用空格隔开

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>后代选择器</title>
  <style>
    /* div 里面的 span 文字颜色是红色 */
    /* 后代选择器，选中所有后代，包含儿子、孙子、重孙子... */
    div span {
      color: red;
    }
  </style>
</head>
<body>
  <span>span 标签</span>
  <div>
    <span>这是div 的儿子 span</span>
    <p>
      <span>孙子 span</span>
    </p>
  </div>
</body>
</html>
```

**子代选择器**

子代选择器：选中某元素的子代元素（最近的子级）。
选择器写法：父选择器 > 子选择器 { CSS 属性}，父子选择器之间用 > 隔开

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>子代选择器</title>
  <style>
    /* div 的儿子 span 文字颜色是红色 */
    div > span {
      color: red;
    }
  </style>
</head>
<body>
  <div>
    <span>儿子 span</span>
    <p>
      <span>孙子 span</span>
    </p>
  </div>
</body>
</html>
```

**并集选择器**

并集选择器：选中多组标签设置相同的样式。
选择器写法：选择器1, 选择器2, …, 选择器N { CSS 属性}，选择器之间用 , 隔开

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>交集选择器</title>
  <style>
    /* 第一个 p 标签文字颜色是红色 */
    /* 既又的关系：既是 p 标签，又是有 box 类 */
    p.box {
      color: red;
    }
  </style>
</head>
<body>
  <p class="box">p 标签，使用了类选择器 box</p>
  <p>p 标签</p>
  <div class="box">div 标签，使用了类选择器</div>
</body>
</html>
```

**交集选择器**

交集选择器：选中同时满足多个条件的元素。
选择器写法：选择器1选择器2 { CSS 属性}，选择器之间连写，没有任何符号。
注意：如果交集选择器中有标签选择器，标签选择器必须书写在最前面

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>交集选择器</title>
  <style>
    /* 第一个 p 标签文字颜色是红色 */
    /* 既又的关系：既是 p 标签，又是有 box 类 */
    p.box {
      color: red;
    }
  </style>
</head>
<body>
  <p class="box">p 标签，使用了类选择器 box</p>
  <p>p 标签</p>
  <div class="box">div 标签，使用了类选择器</div>
</body>
</html>
```

伪类选择器：伪类表示元素状态，选中元素的某个状态设置样式。
鼠标悬停状态：选择器:hover { CSS 属性 }

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>伪类选择器</title>
  <style>
    /* 任何标签都可以设置鼠标悬停的状态 */
    /* :hover表示鼠标悬停 */
    a:hover {
      color: red;
    }

    /* div:hover */
    .box:hover {
      color: green;
    }
  </style>
</head>
<body>
  <a href="#">a 标签，超链接</a>
  <div class="box">div 标签</div>
</body>
</html>
```

**伪类-超链接**

超链接一共有四个状态

![images](./images/屏幕截图%202023-11-27%20154924.png)

提示：如果要给超链接设置以上四个状态，需要按 LVHA 的顺序书写。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>超链接伪类</title>
  <style>
    /* a:link {
      color: red;
    }

    a:visited {
      color: green;
    }

    a:hover {
      color: blue;
    }

    a:active {
      color: orange;
    } */
    /* 工作中，一个 a 标签选择器设置超链接的样式， hover状态特殊设置 */
    a {
      color: red;
    }

    a:hover {
      color: green;
    }
  </style>
</head>
<body>
  <a href="#">a 标签，测试伪类</a>
</body>
</html>
```

## CSS 特性

**CSS 特性**

CSS特性：化简代码 / 定位问题，并解决问题

- 继承性
- 层叠性
- 优先级

**继承性**

继承性：子级默认继承父级的文字控制属性。
注意：如果标签有默认文字样式会继承失败。例如：a 标签的颜色、标题的字体大小。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS特性-继承性</title>
  <style>
    body {
      font-size: 30px;
      color: red;
      font-weight: 700;
    }
  </style>
</head>
<body>
  <div>div 标签</div>
  <p>p 标签</p>
  <span>span 标签</span>

  <!-- 如果标签自己有样式则生效自己的样式，不继承 -->
  <a href="#">a 标签</a>
  <h1>h1 标签</h1>
</body>
</html>
```

**层叠性**

特点：

- 相同的属性会覆盖：后面的 CSS 属性覆盖前面的 CSS 属性
- 不同的属性会叠加：不同的 CSS 属性都生效

注意：选择器类型相同则遵循层叠性，否则按选择器优先级判断

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS特性-层叠性</title>
  <style>
    /* 覆盖；叠加 */

    div {
      color: green;
      font-size: 30px;
    }

    div {
      color: red;
      font-weight: 700;
    }
  </style>
</head>
<body>
  <div>div 标签</div>
</body>
</html>
```

**优先级**

优先级：也叫权重，当一个标签使用了多种选择器时，基于不同种类的选择器的匹配规则

规则：选择器优先级高的样式生效。
公式：通配符选择器 < 标签选择器 < 类选择器 < id选择器 < 行内样式 < !important
（选中标签的范围越大，优先级越低）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS 特性-优先级</title>
  <style>
    /* 技巧：选择器选中标签的范围越大，优先级/权重 越低 */
    div {
      color: green;
    }

    /* !important 提权功能，提高权重/优先级到 最高，慎用 */
    * {
      color: red !important;
    }

    .box {
      color: blue;
    }

    #test {
      color: orange;
    }
  </style>
</head>
<body>
  <div class="box" id="test" style="color: purple;">div 标签</div>
</body>
</html>
```

**优先级 – 叠加计算规则**

叠加计算：如果是复合选择器，则需要权重叠加计算。
公式：（每一级之间不存在进位）
规则：

- 从左向右依次比较选个数，同一级个数多的优先级高，如果个数相同，则向后比较
- !important 权重最高
- 继承权重最低

第一题

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>权重叠加-第一题</title>
  <style>
    /* (0, 0, 2, 1) */
    .c1 .c2 div { 
        color: blue;
    }

    /* (0, 1, 0, 1) */
    div #box3 {
        color:green;
    }

    /* (0, 1, 1, 0) */
    #box1 .c3 {
        color:orange;
    }
  </style>
</head>
<body>
    <div id="box1" class="c1">
        <div id="box2" class="c2">
            <div id="box3" class="c3">
                这行文本是什么颜色的？
            </div>
        </div>
    </div>
</body>
</html>
```

第二题

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>权重叠加-第二题-继承</title>
  <style>
        div p {
            color:red;
        } 

    /* 继承权重最低 */
        .father {
            color:blue;
        } 
  </style>
</head>
<body>
    <div class="father">
        <p class="son"> 
            文字
        </p>
    </div>
</body>
</html>
```

第三题

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>权重叠加-第三题</title>
    <style>
    /* (0, 2, 0, 0) */
        #father #son {
            color:blue; 
        } 

    /* (0, 1, 1, 1) */
        #father p.c2 {
            color:black;
        } 

    /* (0, 0, 2, 2) */
        div.c1 p.c2 {
            color:red;
        } 

        #father { 
            color:green !important;
        } 

        div#father.c1 {
            color: yellow ;
        } 

    </style>
</head>
<body>
  <div id="father" class="c1">
        <p id="son" class="c2">
            这行文本是什么颜色的？ 
        </p>
    </div>
</body>
</html>
```

## Emmet 写法

Emmet写法：代码的简写方式，输入缩写 VS Code 会自动生成对应的代码。

![images](./images/屏幕截图%202023-11-27%20160642.png)
![images](./images/屏幕截图%202023-11-27%20160706.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Emmet 写法</title>
  <style>
    div {
      /* width: ; */
      /* height: ; */
      width: 500px;
      background-color: #fff;
      width: 500px;
      height: 200px;
      background-color: #fff;
    }
  </style>
</head>
<body>
  <div></div>
  <p class="box"></p>
  <div class="box"></div>
  <p id="box"></p>

  <div></div>
  <p></p>

  <div>
    <p></p>
  </div>

  <span></span><span></span><span></span>

  <div>111</div>
</body>
</html>
```

## 背景属性

**背景属性**

![images](./images/屏幕截图%202023-11-27%20161132.png)

**背景图**

网页中，使用背景图实现装饰性的图片效果。
属性名：background-image（bgi）
属性值：url(背景图 URL)
提示：背景图默认有平铺（复制）效果

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>背景图</title>
  <style>
    /* 盒子是 400 * 400 */
    div {
      width: 400px;
      height: 400px;

      /* 背景图默认是平铺（复制）的效果 */
      background-image: url(./images/1.png);
    }
  </style>
</head>
<body>
  <div>div 标签</div>
</body>
</html>
```

**背景图平铺方式**

属性名：background-repeat（bgr）
属性值

![images](./images/屏幕截图%202023-11-27%20161358.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>背景图平铺方式</title>
  <style>
    div {
      width: 400px;
      height: 400px;
      background-color: pink;

      background-image: url(./images/1.png);

      /* 不平铺：盒子的左上角显示一张背景图 */
      background-repeat: no-repeat;
      /* background-repeat: repeat; */
      /* background-repeat: repeat-x; */
      /* background-repeat: repeat-y; */
      
    }
  </style>
</head>
<body>
  <div>div 标签</div>
</body>
</html>
```

**背景图位置**

属性名：background-position（bgp）
属性值：水平方向位置 垂直方向位置

- 关键字
 ![images](./images/屏幕截图%202023-11-27%20161648.png)
- 坐标（数字 + px，正负都可以）
  水平：正数向右；负数向左
  垂直：正数向下；负数向上
  提示：
- 关键字取值方式写法，可以颠倒取值顺序
- 可以只写一个关键字，另一个方向默认为居中；数字只写一个值表示水平方向，垂直方向为居中

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>背景图位置</title>
  <style>
    div {
      width: 400px;
      height: 400px;
      background-color: pink;

      background-image: url(./images/1.png);
      background-repeat: no-repeat;

      /* 左上角 */
      /* background-position: 0 0; */
      /* background-position: left top; */

      /* background-position: right bottom; */

      /* 水平：正数向右，负数向左 */
      /* background-position: 50px 0; */
      /* background-position: -50px 0; */

      /* 垂直：正数向下，负数向上 */
      /* background-position: 0 100px; */
      /* background-position: 0 -100px; */

      /* background-position: 50px center; */

      /* 特殊写法 */
      /* background-position: bottom left; */

      /* 关键字可以只写一个，另一个方向居中 */
      /* background-position: bottom; */

      /* 只写一个数字表示水平方向，垂直方向居中 */
      background-position: 50px;
    }
  </style>
</head>
<body>
  <div>div 标签</div>
</body>
</html>
```

**背景图缩放**

作用：设置背景图大小
属性名：background-size（bgz）
常用属性值：

- 关键字
cover：等比例缩放背景图片以完全覆盖背景区，可能背景图片部分看不见
contain：等比例缩放背景图片以完全装入背景区，可能背景区部分空白
- 百分比：根据盒子尺寸计算图片大小
- 数字 + 单位（例如：px）
提示：工作中，图片比例与盒子比例相同，使用 cover 或 contain 缩放背景图效果相同。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>背景图缩放</title>
  <style>
    div {
      width: 500px;
      height: 300px;
      background-color: pink;
      
      background-image: url(./images/1.png);
      background-repeat: no-repeat;

      /* contain：如果图的宽高跟盒子尺寸相等停止缩放，可能导致盒子有露白 */
      /* background-size: contain; */

      /* cover：图片完全覆盖盒子，可能导致图片显示不全 */
      /* background-size: cover; */

      /* 100% 图片的宽度跟盒子宽度一样，图片的高度按照图片比例等比缩放 */
      background-size: 100%;
    }
  </style>
</head>
<body>
  <div>div 标签</div>
</body>
</html>
```

**背景图固定**

作用：背景不会随着元素的内容滚动。
属性名：background-attachment（bga）
属性值：fixed

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>背景图固定</title>
  <style>
    body {
      background-image: url(./images/bg.jpg);
      background-repeat: no-repeat;
      background-position: center top;

      background-attachment: fixed;
    }
  </style>
</head>
<body>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
  <p>测试文字，撑开body，让浏览器有滚动条</p>
</body>
</html>
```

**背景复合属性**

属性名：background（bg）
属性值：背景色 背景图 背景图平铺方式 背景图位置/背景图缩放 背景图固定（空格隔开各个属性值，不区分顺序）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>background属性</title>
  <style>
    div {
      width: 400px;
      height: 400px;

      /* background: pink url(./images/1.png) no-repeat center bottom/cover; */
      background: pink url(./images/1.png) no-repeat center bottom/contain;
    }
  </style>
</head>
<body>
  <div>div 标签</div>
</body>
</html>
```

## 显示模式

**显示模式**

![images](./images/屏幕截图%202023-11-27%20162713.png)

- 块级元素
  - 独占一行
  - 宽度默认是父级的100%
  - 添加宽高属性生效
- 行内元素
  - 一行可以显示多个
  - 设置宽高属性不生效
  - 宽高尺寸由内容撑开
- 行内块元素
  - 一行可以显示多个
  - 设置宽高属性生效
  - 宽高尺寸也可以由内容撑开

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>显示模式</title>
  <style>
    /* 块级：独占一行；宽度默认是父级的100%；加宽高生效 */
    div {
      width: 100px;
      height: 100px;
    }

    .div1 {
      background-color: brown;
    }

    .div2 {
      background-color: orange;
    }

    /* 行内：一行共存多个；尺寸由内容撑开；加宽高 不 生效 */
    span {
      width: 200px;
      height: 200px;
    }

    .span1 {
      background-color: brown;
    }

    .span2 {
      background-color: orange;
    }

    /* 行内块：一行共存多个；默认尺寸由内容撑开；加宽高生效 */
    img {
      width: 100px;
      height: 100px;
    }
  </style>
</head>
<body>
  <!-- 块元素 -->
  <div class="div1">div 标签1</div>
  <div class="div2">div 标签2</div>

  <!-- 行内元素 -->
  <span class="span1">span11111111</span>
  <span class="span2">span1</span>

  <!-- 行内块元素 -->
  <img src="./images/1.png" alt="">
  <img src="./images/1.png" alt="">
  
</body>
</html>
```

**转换显示模式**

属性名：display
属性值：

![images](./images/屏幕截图%202023-11-27%20164215.png)

## 综合案例2

**综合案例一-热词**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>热词</title>
  <style>
    /* 默认效果 */
    a {
      display: block;
      width: 200px;
      height: 80px;
      background-color: #3064bb;
      color: #fff;
      text-decoration: none;
      text-align: center;
      line-height: 80px;
      font-size: 18px;
    }

    /* 鼠标悬停的效果 */
    a:hover {
      background-color: #608dd9;
    }
  </style>
</head>
<body>
  <a href="#">HTML</a>
  <a href="#">CSS</a>
  <a href="#">JavaScript</a>
  <a href="#">Vue</a>
  <a href="#">React</a>
</body>
</html>
```

**综合案例二 – banner 效果**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>banner效果</title>
  <style>
    .banner {
      height: 500px;
      background-color: #f3f3f4;
      background-image: url(./images/bk.png);
      background-repeat: no-repeat;
      background-position: left bottom;

      /* 文字控制属性，继承给子级 */
      text-align: right;
      color: #333;
    }

    .banner h2 {
      font-size: 36px;
      font-weight: 400;
      line-height: 100px;
    }

    .banner p {
      font-size: 20px;
    }

    .banner a {
      width: 125px;
      height: 40px;
      background-color: #f06b1f;

      display: inline-block;
      /* 转块级无法右对齐，因为块元素独占一行 */
      /* display: block; */

      text-align: center;
      line-height: 40px;
      color: #fff;
      text-decoration: none;
      font-size: 20px;
    }
  </style>
</head>
<body>
  <div class="banner">
    <h2>让创造产生价值</h2>
    <p>我们希望小游戏平台可以提供无限的可能性，让每一个创作者都可以将他们的才华和创意传递给用户。</p>
    <a href="#">我要报名</a>
  </div>
</body>
</html>
```

## 选择器2

**结构伪类选择器**

作用：根据元素的结构关系查找元素

![images](./images/屏幕截图%202023-11-27%20180227.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>结构伪类选择器-基本使用</title>
  <style>
    /* 第一个 */
    li:first-child {
      background-color: green;
    }

    /* 最后一个 */
    li:last-child {
      background-color: green;
    }

    /* 任意个 */
    /* li:nth-child(3) {
      background-color: green;
    } */

    li:nth-child(1) {
      background-color: green;
    }
  </style>
</head>
<body>
  <ul>
    <li>li 1</li>
    <li>li 2</li>
    <li>li 3</li>
    <li>li 4</li>
    <li>li 5</li>
    <li>li 6</li>
    <li>li 7</li>
    <li>li 8</li>
  </ul>
</body>
</html>
```

**:nth-child(公式)**

作用：根据元素的结构关系查找多个元素。

![images](./images/屏幕截图%202023-11-27%20180227.png)

提示：公式中的n取值从 0 开始。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>结构伪类选择器-公式用法</title>
  <style>
    /* 偶数 */
    /* li:nth-child(2n) {
      background-color: green;
    } */

    /* 奇数 */
    /* li:nth-child(2n+1) {
      background-color: green;
    } */

    /* 倍数 */
    /* li:nth-child(5n) {
      background-color: green;
    } */

    /* n 从0开始 */
    /* 第5个以后的标签 */
    /* li:nth-child(n+5) {
      background-color: green;
    } */

    /* 第5个以前的标签 */
    li:nth-child(-n+5) {
      background-color: green;
    }
  </style>
</head>
<body>
  <ul>
    <li>li 1</li>
    <li>li 2</li>
    <li>li 3</li>
    <li>li 4</li>
    <li>li 5</li>
    <li>li 6</li>
    <li>li 7</li>
    <li>li 8</li>
    <li>li 9</li>
    <li>li 10</li>
  </ul>
</body>
</html>
```

**伪元素选择器**

作用：创建虚拟元素（伪元素），用来摆放装饰性的内容

![images](./images/屏幕截图%202023-11-27%20180227.png)

注意点：

- 必须设置 content: ””属性，用来 设置伪元素的内容，如果没有内容，则引号留空即可• 伪元素默认是行内显示模式
- 权重和标签选择器相同

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>伪元素选择器</title>
  <style>
    div {
      width: 300px;
      height: 300px;
      background-color: pink;
    }

    div::before {
      content: '老鼠';
      width: 100px;
      height: 100px;
      display: block;
      background-color: red;
    }
    /* 必须设置content属性 */
    div::after {
      content: '大米';
      width: 100px;
      height: 100px;
      display: inline-block;
      background-color: blue;
    }
  </style>
</head>
<body>
  <!-- 标签内容：老鼠爱大米 -->
  <div>爱</div>
</body>
</html>
```

## PxCooK

**PxCook**

PxCook（像素大厨） 是一款切图设计工具软件。支持PSD文件的文字、颜色、距离自动智能识别。（PSD文件就是设计稿）

- 开发面板（自动智能识别）
- 设计面板（手动测量尺寸和颜色）

## 盒子模型

**盒子模型 – 组成**

作用：布局网页，摆放盒子和内容

盒子模型重要组成部分：

- 内容区域 – width & height • 内边距 – padding（出现在内容与盒子边缘之间）
- 边框线 – border
- 外边距 – margin（出现在盒子外面）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>盒子模型-组成</title>
  <style>
    div {
      width: 200px;
      height: 200px;
      background-color: pink;

      /* 内容与盒子边缘之间 */
      padding: 20px;
      border: 1px solid #000;
      /* 出现在盒子外面，拉开两个盒子之间的距离 */
      margin: 50px;
    }
  </style>
</head>
<body>
  <div>div 标签</div>
</body>
</html>
```

**盒子模型 – 边框线**

属性名：border（bd）
属性值：边框线粗细 线条样式 颜色（不区分顺序）
常用线条样式

![images](./images/屏幕截图%202023-11-27%20183322.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>盒子模型-边框线</title>
  <style>
    div {
      width: 200px;
      height: 200px;
      background-color: pink;

      /* 实线 */
      /* border: 1px solid #000; */

      /* 虚线 */
      /* border: 2px dashed red; */

      /* 点线 */
      border: 3px dotted green;
    }
  </style>
</head>
<body>
  <div>div 标签</div>
</body>
</html>
```

**盒子模型 – 单边框线**

设置单方向边框线
属性名：border-方位名词（bd+方位名词首字母，例如，bdl）
属性值：边框线粗细 线条样式 颜色（不区分顺序）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>盒子模型-单方向边框线</title>
  <style>
    div {
      width: 200px;
      height: 200px;
      background-color: pink;

      border-top: 1px solid #000;
      border-right: 2px dashed red;
      border-bottom: 5px dotted green;
      border-left: 10px solid orange;
    }
  </style>
</head>
<body>
  <div>div 标签</div>
</body>
</html>
```

**盒子模型 – 内边距**

作用：设置 内容 与 盒子边缘 之间的距离。
属性名：padding / padding-方位名词

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>盒子模型-内边距</title>
  <style>
    div {
      width: 200px;
      height: 200px;
      background-color: pink;

      /* padding: 20px; */

      padding-top: 10px;
      padding-right: 20px;
      padding-bottom: 40px;
      padding-left: 80px;
    }
  </style>
</head>
<body>
  <div>div 标签</div>
</body>
</html>
```

**盒子模型 – 内边距 – 多值写法**

padding 多值写法

![images](./images/屏幕截图%202023-11-27%20184203.png)

技巧：从上开始顺时针赋值，当前方向没有数值则与对面取值相同

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>盒子模型-padding多值写法</title>
  <style>
    div {
      width: 200px;
      height: 200px;
      background-color: pink;

      /* 四值：上  右  下  左 */
      /* padding: 10px 20px 40px 80px; */

      /* 三值：上  左右  下 */
      /* padding: 10px 40px 80px; */

      /* 两值：上下  左右 */
      padding: 10px 80px;

      /* 记忆方法：从上开始顺时针转一圈，如果当前方向没有数值，取值跟对面一样 */
    }
  </style>
</head>
<body>
  <div>div 标签</div>
</body>
</html>
```

**盒子模型 – 尺寸计算**

默认情况
盒子尺寸 = 内容尺寸 + border 尺寸 + 内边距尺寸
结论：给盒子加 border / padding 会撑大盒子
解决

- 手动做减法，减掉 border / padding 的尺寸
- 內减模式：box-sizing: border-box

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>盒子模型-尺寸计算</title>
  <style>
    div {
      width: 200px;
      height: 200px;
      /* 手动减法 */
      /* width: 160px;
      height: 160px; */
      background-color: pink;

      padding: 20px;

      /* 內减模式：不需要手动减法，加padding和border不会撑大盒子 */
      box-sizing: border-box;
    }
  </style>
</head>
<body>
  <div>div 标签</div>
</body>
</html>
```

**盒子模型 – 外边距**

作用：拉开两个盒子之间的距离
属性名：margin
提示：与 padding 属性值写法、含义相同
技巧：版心居中 – 左右 margin 值 为 auto（盒子要有宽度）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>版心居中</title>
  <style>
    div {
      /* 版心居中要求：盒子要有宽度 */
      width: 1000px;
      height: 200px;
      background-color: pink;

      /* 外边距 不会 撑大盒子 */
      /* margin: 50px; */
      /* margin-left: 100px; */
      /* margin: 50px 100px; */

      margin: 0 auto;
    }
  </style>
</head>
<body>
  <div>版心内容</div>
</body>
</html>
```

**清除默认样式**

清除标签默认的样式，比如：默认的内外边距。

![images](./images/屏幕截图%202023-11-27%20185543.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>清除默认样式</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    /* 去掉列表的项目符号 */
    li {
      list-style: none;
    }
  </style>
</head>
<body>
  <h1>标题</h1>
  <p>ppppp</p>
  <ul>
    <li>li</li>
  </ul>
</body>
</html>
```

**盒子模型 – 元素溢出**

作用：控制溢出元素的内容的显示方式。
属性名：overflow
属性值

![images](./images/屏幕截图%202023-11-27%20185947.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>元素溢出</title>
  <style>
    div {
      width: 200px;
      height: 200px;
      background-color: pink;

      overflow: hidden;

      /* overflow: scroll; */

      /* overflow: auto; */
    }
  </style>
</head>
<body>
  <div>文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试文字内容测试</div>
</body>
</html>
```

**外边距问题 – 合并现象**

场景：垂直排列的兄弟元素，上下 margin 会合并
现象：取两个 margin 中的较大值生效

![images](./images/屏幕截图%202023-11-27%20190258.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>外边距-合并现象</title>
  <style>
    .one {
      width: 100px;
      height: 100px;
      background-color: brown;
      margin-bottom: 80px;
    }

    .two {
      width: 100px;
      height: 100px;
      background-color: orange;
      margin-top: 50px;
    }
  </style>
</head>
<body>
  <div class="one">one</div>
  <div class="two">two</div>
</body>
</html>
```

**外边距问题 – 塌陷问题**

场景：父子级的标签，子级的添加 上外边距 会产生塌陷问题
现象：导致父级一起向下移动

![images](./images/屏幕截图%202023-11-27%20190556.png)

解决方法：

- 取消子级margin，父级设置padding
- 父级设置 overflow: hidden
- 父级设置 border-top

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>外边距-塌陷问题</title>
  <style>
    .father {
      width: 300px;
      height: 300px;
      background-color: pink;
      /* padding-top: 50px;
      box-sizing: border-box; */

      /* 溢出隐藏 */
      /* overflow: hidden; */

      border-top: 1px solid #000;
    }

    .son {
      width: 100px;
      height: 100px;
      background-color: orange;

      margin-top: 50px;
    }
  </style>
</head>
<body>
  <div class="father">
    <div class="son">son</div>
  </div>
</body>
</html>
```

**行内元素 – 内外边距问题**

场景：行内元素添加 margin 和 padding，无法改变元素垂直位置
解决方法：给行内元素添加 line-height 可以改变垂直位置

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>行内元素的垂直内外边距</title>
  <style>
    span {
      margin: 50px;
      padding: 20px;
      line-height: 100px;
    }
  </style>
</head>
<body>
  <span>span标签</span>
  <span>span标签</span>
</body>
</html>
```

**盒子模型 – 圆角**

作用：设置元素的外边框为圆角。
属性名：border-radius
属性值：数字+px / 百分比
提示：属性值是圆角半径

![images](./images/屏幕截图%202023-11-27%20191600.png)

技巧：从左上角开始顺时针赋值，当前角没有数值则与对角取值相同。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>圆角-基本使用</title>
  <style>
    div {
      margin: 50px auto;
      width: 200px;
      height: 200px;
      background-color: orange;

      /* border-radius: 20px; */

      /* 记忆：从左上角顺时针赋值，没有取值的角与对角取值相同 */

      /* 四值：左上  右上  右下  左下 */
      /* border-radius: 10px 20px 40px 80px; */

      /* 三值：左上  右上+左下  右下 */
      /* border-radius: 10px 40px 80px; */

      /* 两值：左上+右下  右上+左下 */
      border-radius: 10px 80px;
    }
  </style>
</head>
<body>
  <div></div>
</body>
</html>
```

**盒子模型 – 常用圆角**

常见应用 – 正圆形状

- 给正方形盒子设置圆角属性值为 宽高的一半 / 50%

常见应用 – 胶囊形状

- 给长方形盒子设置圆角属性值为 盒子高度的一半

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>圆角-特殊场景</title>
  <style>
    img {
      width: 200px;
      height: 200px;

      /* border-radius: 100px; */

      /* 最大值是50%。超过50%没有效果 */
      border-radius: 50%;
    }

    div {
      width: 200px;
      height: 80px;
      background-color: orange;

      border-radius: 40px;
    }
  </style>
</head>
<body>
  <!-- 正圆形 -- 头像 -->
  <img src="./images/1.jpg" alt="">

  <!-- 胶囊状 -->
  <div></div>
</body>
</html>
```

**盒子模型 – 阴影**

作用：给元素设置阴影效果
属性名：box-shadow
属性值：X 轴偏移量 Y 轴偏移量 模糊半径 扩散半径 颜色 内外阴影
注意：

- X 轴偏移量 和 Y 轴偏移量 必须书写
- 默认是外阴影，内阴影需要添加 inset

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>盒子阴影</title>
  <style>
    div {
      margin: 50px auto;
      width: 200px;
      height: 80px;
      background-color: orange;

      box-shadow: 2px 5px 10px 1px rgba(0,0,0,0.5) inset;
    }
  </style>
</head>
<body>
  <div></div>
</body>
</html>
```

## 综合案例3

**综合案例一 – 产品卡片**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>产品卡片</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background-color: #f1f1f1;
    }

    .product {
      margin: 50px auto;
      padding-top: 40px;

      width: 270px;
      height: 253px;
      background-color: #fff;
      text-align: center;

      border-radius: 10px;
    }

    .product h4 {
      margin-top: 20px;
      margin-bottom: 12px;
      font-size: 18px;
      color: #333;
      font-weight: 400;
    }

    .product p {
      font-size: 12px;
      color: #555;
    }
  </style>
</head>
<body>
  <div class="product">
    <img src="./images/liveSDK.svg" alt="">
    <h4>抖音直播SDK</h4>
    <p>包含抖音直播看播功能</p>
  </div>
</body>
</html>
```

**综合案例二 – 新闻列表**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>新闻列表</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    li {
      list-style: none;
    }

    a {
      text-decoration: none;
    }

    .news {
      margin: 100px auto;
      width: 360px;
      height: 200px;
      /* background-color: pink; */
    }

    .news .hd {
      height: 34px;
      background-color: #eee;
      border: 1px solid #dbdee1;
      border-left: 0;
    }

    .news .hd a {
      /* -1 盒子向上移动 */
      margin-top: -1px;
      display: block;
      border-top: 3px solid #ff8400;
      border-right: 1px solid #dbdee1;
      width: 48px;
      height: 34px;
      background-color: #fff;

      text-align: center;
      line-height: 32px;
      font-size: 14px;
      color: #333;
    }

    .news .bd {
      padding: 5px;
    }

    .news .bd li {
      padding-left: 15px;
      background-image: url(./images/square.png);
      background-repeat: no-repeat;
      background-position: 0 center;
    }

    .news .bd li a {
      padding-left: 20px;
      background: url(./images/img.gif) no-repeat 0 center;

      font-size: 12px;
      color: #666;
      line-height: 24px;
    }

    .news .bd li a:hover {
      color: #ff8400;
    }
  </style>
</head>
<body>
  <!-- 新闻区域 包含 标题 + 内容 -->
  <div class="news">
    <div class="hd"><a href="#">新闻</a></div>
    <div class="bd">
      <ul>
        <li><a href="#">点赞“新农人” 温暖的伸手</a></li>
        <li><a href="#">在希望的田野上...</a></li>
        <li><a href="#">“中国天眼”又有新发现 已在《自然》杂志发表</a></li>
        <li><a href="#">急！这个领域，缺人！月薪4万元还不好招！啥情况？</a></li>
        <li><a href="#">G9“带货”背后：亏损面持续扩大，竞争环境激烈</a></li>
        <li><a href="#">多地力推二手房“带押过户”，有什么好处？</a></li>
      </ul>
    </div>
  </div>
</body>
</html>
```

## 标准流

标准流也叫文档流，指的是标签在页面中默认的排布规则，例如：块元素独占一行，行内元素可以一行显示多个。

![images](./images/屏幕截图%202023-11-27%20200259.png)

**浮动**

浮动
作用：让块元素水平排列。
属性名：float
属性值

- left：左对齐
- right：右对齐

特点：

- 浮动后的盒子顶对齐
- 浮动后的盒子具备行内块特点
- 浮动后的盒子脱标，不占用标准流的位置

![images](./images/屏幕截图%202023-11-27%20200535.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>浮动-基本使用</title>
  <style>
    /* 特点：顶对齐；具备行内块显示模式特点；浮动的盒子会脱标 */
    .one {
      width: 100px;
      height: 100px;
      background-color: brown;

      float: left;
    }

    .two {
      width: 200px;
      height: 200px;
      background-color: orange;

      /* float: left; */

      float: right;
    }
  </style>
</head>
<body>
  <div class="one">one</div>
  <div class="two">two</div>
</body>
</html>
```

**浮动 – 产品区域布局**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>浮动-产品布局</title>
  <style>
    * {
      margin: 0;
      padding: 0;
    }

    li {
      list-style: none;
    }

    .product {
      margin: 50px auto;
      width: 1226px;
      height: 628px;
      background-color: pink;
    }

    .left {
      float: left;
      width: 234px;
      height: 628px;
      background-color: skyblue;
    }

    .right {
      float: right;
      width: 978px;
      height: 628px;
      background-color: brown;
    }

    .right li {
      float: left;
      margin-right: 14px;
      margin-bottom: 14px;
      width: 234px;
      height: 300px;
      background-color: orange;
    }

    /* 第四个li和第八个li 去掉右侧的margin */
    .right li:nth-child(4n) {
      margin-right: 0;
    }

    /* 细节：如果父级宽度不够，浮动的盒子会掉下来 */
  </style>
</head>
<body>
  <!-- 版心：左右，右面：8个产品 → 8个 li -->
  <div class="product">
    <div class="left"></div>
    <div class="right">
      <ul>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
      </ul>
    </div>
  </div>
</body>
</html>
```

**清除浮动**

场景：浮动元素会脱标，如果父级没有高度，子级无法撑开父级高度（可能导致页面布局错乱）解决方法：清除浮动（清除浮动带来的影响）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>浮动-清除浮动</title>
<style>
  .father {
    margin: 10px auto;
    width: 1200px;
    /* height: 300px; */
    background-color: pink;
  }

  .left {
    float: left;
    width: 200px;
    height: 300px;
    background-color: skyblue;
  }

  .right {
    float: right;
    width: 950px;
    height: 300px;
    background-color: orange;
  }

  .bottom {
    height: 100px;
    background-color: brown;
  }

</style>
</head>
<body>
<div class="father">
  <div class="left"></div>
  <div class="right"></div>
</div>
<div class="bottom"></div>
</body>
</html>
```

**清除浮动**

**方法一：额外标签法**

- 在父元素内容的最后添加一个块级元素，设置 CSS 属性 clear: both

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>清除浮动-额外标签法</title>
  <style>
    .father {
      margin: 10px auto;
      width: 1200px;
      /* height: 300px; */
      background-color: pink;
    }

    .left {
      float: left;
      width: 200px;
      height: 300px;
      background-color: skyblue;
    }

    .right {
      float: right;
      width: 950px;
      height: 300px;
      background-color: orange;
    }

    .bottom {
      height: 100px;
      background-color: brown;
    }

    .clearfix {
      clear: both;
    }
  </style>
</head>
<body>
  <div class="father">
    <div class="left"></div>
    <div class="right"></div>
    <!-- 额外标签 -->
    <div class="clearfix"></div>
  </div>
  <div class="bottom"></div>
</body>
</html>
```

**方法二：单伪元素法**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>清除浮动-单伪元素法</title>
  <style>
    .father {
      margin: 10px auto;
      width: 1200px;
      /* height: 300px; */
      background-color: pink;
    }

    .left {
      float: left;
      width: 200px;
      height: 300px;
      background-color: skyblue;
    }

    .right {
      float: right;
      width: 950px;
      height: 300px;
      background-color: orange;
    }

    .bottom {
      height: 100px;
      background-color: brown;
    }

    /* 单伪元素法 */
  .clearfix::after {
    content: "";
    display: block;
    clear: both;
  }
  </style>
</head>
<body>
  <div class="father clearfix">
    <div class="left"></div>
    <div class="right"></div>
  </div>
  <div class="bottom"></div>
</body>
</html>
```

**方法三：双伪元素法（推荐）**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>清除浮动-双伪元素法</title>
  <style>
    .father {
      margin: 10px auto;
      width: 1200px;
      /* height: 300px; */
      background-color: pink;
    }

    .left {
      float: left;
      width: 200px;
      height: 300px;
      background-color: skyblue;
    }

    .right {
      float: right;
      width: 950px;
      height: 300px;
      background-color: orange;
    }

    .bottom {
      height: 100px;
      background-color: brown;
    }

    /* before 解决外边距塌陷问题 */
    /* 双伪元素法 */
    .clearfix::before,
    .clearfix::after {
      content: "";
      display: table;
    }

    /* after 清除浮动 */
    .clearfix::after {
      clear: both;
    }
  </style>
</head>
<body>
  <div class="father clearfix">
    <div class="left"></div>
    <div class="right"></div>
  </div>
  <div class="bottom"></div>
</body>
</html>
```

**方法四：overflow**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>清除浮动-overflow</title>
  <style>
    .father {
      margin: 10px auto;
      width: 1200px;
      /* height: 300px; */
      background-color: pink;

      overflow: hidden;
    }

    .left {
      float: left;
      width: 200px;
      height: 300px;
      background-color: skyblue;
    }

    .right {
      float: right;
      width: 950px;
      height: 300px;
      background-color: orange;
    }

    .bottom {
      height: 100px;
      background-color: brown;
    }

  </style>
</head>
<body>
  <div class="father">
    <div class="left"></div>
    <div class="right"></div>
  </div>
  <div class="bottom"></div>
</body>
</html>
```

**浮动 – 总结**

- 浮动属性 float，left 表示左浮动，right 表示右浮动
- 特点
  
  1. 浮动后的盒子顶对齐
  2. 浮动后的盒子具备行内块特点
  3. 父级宽度不够，浮动的子级会换行
  4. 浮动后的盒子脱标

- 清除浮动：子级浮动，父级没有高度，子级无法撑开父级高度，影响布局效果
  1. 双伪元素法
- 拓展：浮动本质作用是实现图文混排效果

## flex布局

**Flex – 认识**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>flex布局-体验</title>
  <style>
    .box {
      display: flex;
      justify-content: space-between;

      /* height: 300px; */
      border: 1px solid #000;
    }

    .box div {
      /* float: left;
      margin: 50px; */

      width: 200px;
      height: 100px;
      background-color: pink;
    }
  </style>
</head>
<body>
  <div class="box">
    <div>1</div>
    <div>2</div>
    <div>3</div>
  </div>
</body>
</html>
```

**Flex – 组成**

设置方式：给父元素设置 display: flex，子元素可以自动挤压或拉伸
组成部分：

- 弹性容器
- 弹性盒子
- 主轴：默认在水平方向
- 侧轴 / 交叉轴：默认在垂直方向

![images](./images/屏幕截图%202023-11-28%20184027.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>flex布局-组成</title>
  <style>
    /* 弹性容器 */
    .box {
      display: flex;

      height: 300px;
      border: 1px solid #000;
    }

    /* 弹性盒子：沿着主轴方向排列 */
    .box div {
      width: 200px;
      /* height: 100px; */
      background-color: pink;
    }
  </style>
</head>
<body>
  <div class="box">
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>1</div>
    <div>2</div>
    <div>3</div>
  </div>
</body>
</html>
```

**主轴对齐方式**

属性名：justify-content

![images](./images/屏幕截图%202023-11-28%20184503.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>flex布局-主轴对齐方式</title>
  <style>
    .box {
      display: flex;
      /* justify-content: flex-start; */

      /* justify-content: flex-end; */

      /* 居中 */
      /* justify-content: center; */

      /* 父级剩余的尺寸分配成间距 */

      /* 弹性盒子之间的间距相等 */
      /* justify-content: space-between; */

      /* 间距出现在弹性盒子两侧 */
      /* 视觉效果：弹性盒子之间的间距是两端间距的2倍 */
      /* justify-content: space-around; */

      /* 各个间距都相等 */
      justify-content: space-evenly;

      height: 300px;
      border: 1px solid #000;
    }

    .box div {
      width: 200px;
      height: 100px;
      background-color: pink;
    }
  </style>
</head>
<body>
  <div class="box">
    <div>1</div>
    <div>2</div>
    <div>3</div>
  </div>
</body>
</html>
```

**侧轴对齐方式**

属性名

- align-items：当前弹性容器内所有弹性盒子的侧轴对齐方式（给弹性容器设置）
- align-self：单独控制某个弹性盒子的侧轴对齐方式（给弹性盒子设置）

![images](./images/屏幕截图%202023-11-28%20184935.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>flex布局-侧轴对齐方式</title>
  <style>
    .box {
      display: flex;
      /* 弹性盒子在侧轴方向没有尺寸才能拉伸 */
      /* align-items: stretch; */

      /* align-items: center; */

      /* align-items: flex-start; */

      align-items: flex-end;

      height: 300px;
      border: 1px solid #000;
    }

    /* 第二个div，侧轴居中对齐 */
    .box div:nth-child(2) {
      align-self: center;
    }

    .box div {
      width: 200px;
      height: 100px;
      background-color: pink;
    }
  </style>
</head>
<body>
  <div class="box">
    <div>1</div>
    <div>2</div>
    <div>3</div>
  </div>
</body>
</html>
```

**修改主轴方向**

主轴默认在水平方向，侧轴默认在垂直方向
属性名：flex-direction
属性值

![images](./images/屏幕截图%202023-11-28%20185502.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>flex布局-修改主轴方向</title>
  <style>
    .box {
      display: flex;

      /* 修改主轴方向 垂直方向；侧轴自动变换到水平方向 */
      flex-direction: column;

      /* 主轴在垂直，视觉效果：垂直居中 */
      justify-content: center;

      /* 侧轴在水平，视觉效果：水平居中 */
      align-items: center;

      width: 150px;
      height: 120px;
      background-color: pink;
    }

    img {
      width: 32px;
      height: 32px;
    }
  </style>
</head>
<body>
  <div class="box">
    <img src="./images/1.png" alt="">
    <span>媒体</span>
  </div>
</body>
</html>
```

**弹性伸缩比**

作用：控制弹性盒子的主轴方向的尺寸。
属性名：flex
属性值：整数数字，表示占用父级剩余尺寸的份数。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>flex布局-弹性伸缩比</title>
  <style>
    /* 默认情况下，主轴方向尺寸是靠内容撑开；侧轴默认拉伸 */
    .box {
      display: flex;
      flex-direction: column;

      height: 300px;
      border: 1px solid #000;
    }

    .box div {
      /* height: 100px; */
      background-color: pink;
    }

    .box div:nth-child(1) {
      width: 200px;
    }

    .box div:nth-child(2) {
      flex: 1;
    }

    .box div:nth-child(3) {
      flex: 2;
    }
  </style>
</head>
<body>
  <div class="box">
    <div>1</div>
    <div>2</div>
    <div>3</div>
  </div>
</body>
</html>
```

**弹性盒子换行**

弹性盒子可以自动挤压或拉伸，默认情况下，所有弹性盒子都在一行显示。
属性名：flex-wrap
属性值

- wrap：换行
- nowrap：不换行（默认）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>flex布局-弹性换行</title>
  <style>
    .box {
      display: flex;
      flex-wrap: wrap;

      /* 不换行 */
      /* flex-wrap: nowrap; */

      justify-content: space-between;

      height: 300px;
      border: 1px solid #000;
    }

    .box div {
      width: 200px;
      height: 100px;
      background-color: pink;
    }
  </style>
</head>
<body>
  <div class="box">
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
    <div>6</div>
    <div>7</div>
    <div>8</div>
    <div>9</div>
    <div>10</div>
    <div>11</div>
    <div>12</div>
  </div>
</body>
</html>
```

**行对齐方式**

属性名：align-content
属性值

![images](./images/屏幕截图%202023-11-28%20190647.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>flex布局-行对齐方式</title>
  <style>
    .box {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;

      /* 调整 行对齐方式：对单行弹性盒子不生效 */
      /* align-content: flex-start; */
      /* align-content: flex-end; */

      /* align-content: center; */

      /* align-content: space-between; */
      /* align-content: space-around; */

      /* 没有代码提示 */
      align-content: space-evenly;


      height: 400px;
      border: 1px solid #000;
    }

    .box div {
      width: 200px;
      height: 100px;
      background-color: pink;
    }
  </style>
</head>
<body>
  <div class="box">
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
    <div>6</div>
    <div>7</div>
    <div>8</div>
  </div>
</body>
</html>
```

注意：该属性对单行弹性盒子模型无效。

## css4

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>抖音解决方案</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    li {
      list-style: none;
    }

    .box {
      margin: 50px auto;
      width: 1200px;
      height: 418px;
      border: 1px solid #ddd;
      border-radius: 10px;
    }

    .box ul {
      display: flex;
      /* 弹性盒子换行 */
      flex-wrap: wrap;
      /* 调整主轴对齐方式 */
      justify-content: space-between;

      /* 调整 行对齐方式 */
      align-content: space-between;

      padding: 90px 40px 90px 60px;
      height: 418px;
    }

    .box li {
      display: flex;
      width: 500px;
      height: 88px;
      /* background-color: pink; */
    }

    .box .pic {
      margin-right: 15px;
    }

    .box .text h4 {
      line-height: 40px;
      font-size: 20px;
      font-weight: 400;
      color: #333;
    }

    .box .text p {
      font-size: 14px;
      color: #666;
    }
  </style>
</head>
<body>
  <div class="box">
    <ul>
      <li>
        <div class="pic">
          <img src="./images/1.svg" alt="">
        </div>
        <div class="text">
          <h4>一键发布多端</h4>
          <p>发布视频到抖音短视频、西瓜视频及今日头条</p>
        </div>
      </li>
      <li>
        <div class="pic">
          <img src="./images/2.svg" alt="">
        </div>
        <div class="text">
          <h4>管理视频内容</h4>
          <p>支持修改已发布稿件状态和实时查询视频审核状态</p>
        </div>
      </li>
      <li>
        <div class="pic">
          <img src="./images/3.svg" alt="">
        </div>
        <div class="text">
          <h4>发布携带组件</h4>
          <p>支持分享内容携带小程序、地理位置信息等组件，扩展内容及突出地域性</p>
        </div>
      </li>
      <li>
        <div class="pic">
          <img src="./images/4.svg" alt="">
        </div>
        <div class="text">
          <h4>数据评估分析</h4>
          <p>获取视频在对应产品内的数据表现、获取抖音热点，及时进行表现评估</p>
        </div>
      </li>
    </ul>
  </div>
</body>
</html>
```

## 定位

**定位**

作用：灵活的改变盒子在网页中的位置
实现：

1. 定位模式：position
2. 边偏移：设置盒子的位置
left
right
top
bottom

**相对定位**

position: relative
特点：

- 不脱标，占用自己原来位置
- 显示模式特点保持不变
- 设置边偏移则相对自己原来位置移动

拓展：很少单独使用相对定位，一般是与其他定位方式配合使用

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>相对定位</title>
  <style>
    * {
      margin: 0;
      padding: 0;
    }

    /* 
      1. 改变位置的参照物是 自己原来的位置
      2. 不脱标，占位
      3. 标签显示模式特点 不变
    */

  div {
    position: relative;
    top: 100px;
    left: 200px;
  }    
  </style>
</head>
<body>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <div><img src="./images/1.webp" alt=""></div>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
</body>
</html>
```

**绝对定位**

position: absolute
使用场景：子级绝对定位，父级相对定位（子绝父相）

特点：

- 脱标，不占位
- 显示模式具备行内块特点
- 设置边偏移则相对最近的已经定位的祖先元素改变位置
- 如果祖先元素都未定位，则相对浏览器可视区改变位置

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>绝对定位</title>
  <style>
    * {
      margin: 0;
      padding: 0;
    }

    img {
      width: 400px;
    }

    .news {
      position: relative;
    
      margin: 100px auto;
      width: 400px;
      height: 350px;
      background-color: #f8f8f8;
    }

    /* 
      1. 脱标，不占位
      2. 参照物：先找最近的已经定位的祖先元素；如果所有祖先元素都没有定位，参照浏览器可视区改位置
      3. 显示模式特点改变：宽高生效（具备了行内块的特点）
    */

    .news span {
      position: absolute;
      top: 0;
      right: 0;

      /* display: block; */
      width: 92px;
      height: 32px;
      background-color: rgba(0,0,0,0.6);
      text-align: center;
      line-height: 32px;
      color: #fff;
    }
  </style>
</head>
<body>
  <div class="news">
    <img src="./images/news.jpg" alt="">
    <span>展会活动</span>
    <h4>2222世界移动大会</h4>
  </div>
</body>
</html>
```

**定位居中**

实现步骤：

1. 绝对定位
2. 水平、垂直边偏移为 50%
3. 子级向左、上移动自身尺寸的一半
左、上的外边距为 –尺寸的一半
transform: translate(-50%, -50%)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>绝对定位-居中</title>
  <style>
    img {
      position: absolute;
      left: 50%;
      top: 50%;

      /* margin-left: -265px;
      margin-top: -127px; */

      /* 方便： 50% 就是自己宽高的一半 */
      transform: translate(-50%, -50%);
    }
  </style>
</head>
<body>
  <img src="./images/login.webp" alt="">
</body>
</html>
```

**固定定位**

场景：元素的位置在网页滚动时不会改变
特点：

- 脱标，不占位
- 显示模式具备行内块特点
- 设置边偏移相对浏览器窗口改变位置

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>固定定位</title>
  <style>
    * {
      margin: 0;
      padding: 0;
    }

    /* 
      1. 脱标，不占位
      2. 参照物：浏览器窗口
      3. 显示模式特点 具备行内块特点
    */

    div {
      position: fixed;
      top: 0;
      right: 0;

      width: 500px;
    }
  </style>
</head>
<body>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <div><img src="./images/1.webp" alt=""></div>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
  <p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。 [5] 与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用（SPA）提供驱动。</p>
</body>
</html>
```

**堆叠层级 z-index**

默认效果：按照标签书写顺序，后来者居上
作用：设置定位元素的层级顺序，改变定位元素的显示顺序
属性名：z-index
属性值：整数数字（默认值为0，取值越大，层级越高）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>堆叠顺序-z-index</title>
  <style>
    div {
      position: absolute;
      width: 200px;
      height: 200px;
    }

    .box1 {
      background-color: pink;
      /* 取值是整数，默认是0，取值越大显示顺序越靠上 */
      z-index: 1;
    }

    .box2 {
      background-color: skyblue;
      left: 100px;
      top: 100px;

      z-index: 2;
    }
  </style>
</head>
<body>
  <div class="box1">box1</div>
  <div class="box2">box2</div>
</body>
</html>
```

![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
![images]()
