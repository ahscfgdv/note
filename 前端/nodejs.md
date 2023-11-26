# nodejs

教程地址
<https://www.bilibili.com/video/BV1a34y167AZ>

## 什么是nodejs

nodejs是JavaScript的运行环境(基于chrome v8引擎)
在浏览器中的js代码是运行在浏览器自带的环境上，在自己的电脑上运行的js代码是需要nodejs

## 使用执行nodejs执行JavaScript代码

终端执行命令 `node 文件名.js`

## nodejs自带模块

## fs文件系统模块

**fs.readFile() 读取文件**

```javascript
const fs = require('fs');

const filePath = 'example.txt'; // 文件路径
fs.readFile(filePath, 'utf8', (error, data) => {
  if (error) {
    console.error('Error reading file:', error);
    return;
  }
  console.log('File content:', data);
});
/**
 * 在上面的示例中，example.txt 是要读取的文件路径。
 * utf8 是可选的字符编码参数，用于指定文件内容的编码格式。
 * 回调函数中的 error 参数将包含可能出现的错误，
 * data 参数包含读取的文件内容。
 * 如果你是在浏览器环境中操作文件，
 * JavaScript 通常不能直接读取本地文件系统中的文件。
 * 浏览器有安全限制，一般情况下不能使用 fs 模块来读取本地文件。
 * 在这种情况下，你可以使用 HTML5 的 File API 来读取用户通过文件输入框选择的文件内容。
 */
```

**读取文件内容**

```javascript
// 1. 导入 fs 模块，来操作文件
const fs = require('fs')

// 2. 调用 fs.readFile() 方法读取文件
//    参数1：读取文件的存放路径
//    参数2：读取文件时候采用的编码格式，一般默认指定 utf8
//    参数3：回调函数，拿到读取失败和成功的结果  err  dataStr
fs.readFile('../code/files/1.txt', 'utf8', function(err, dataStr) {
  // 2.1 打印失败的结果
  // 如果读取成功，则 err 的值为 null
  // 如果读取失败，则 err 的值为 错误对象，dataStr 的值为 undefined
  console.log(err)
  console.log('-------')
  // 2.2 打印成功的结果
  console.log(dataStr)
})

```

**判断文件读取**

```javascript
const fs = require('fs')

fs.readFile('../code/files/1.txt', 'utf8', function(err, dataStr) {
  if (err) {
    return console.log('读取文件失败！' + err.message)
  }
  console.log('读取文件成功！' + dataStr)
})

```

**fs.writeFile()**

```javascript
const fs = require('fs');

const filePath = 'example.txt'; // 文件路径
const content = 'This is the content to write into the file';

fs.writeFile(filePath, content, 'utf8', (error) => {
  if (error) {
    console.error('Error writing file:', error);
    return;
  }
  console.log('File has been written successfully');
});
/**
 * 在这个示例中，example.txt 是要写入的文件路径，
 * content 是要写入文件的内容。
 * 'utf8' 是可选的字符编码参数，用于指定写入文件内容的编码格式。
 * 回调函数中的 error 参数将包含可能出现的错误。
 */
```

**进行写入操作**

```javascript
// 1. 导入 fs 文件系统模块
const fs = require('fs')

// 2. 调用 fs.writeFile() 方法，写入文件的内容
//    参数1：表示文件的存放路径
//    参数2：表示要写入的内容
//    参数3：回调函数
fs.writeFile('./files/3.txt', 'ok123132', function(err) {
  // 2.1 如果文件写入成功，则 err 的值等于 null
  // 2.2 如果文件写入失败，则 err 的值等于一个 错误对象
  // console.log(err)

  if (err) {
    return console.log('文件写入失败！' + err.message)
  }
  console.log('文件写入成功！')
})

```

**成绩测试**

```javascript
// 1. 导入 fs 模块
const fs = require('fs')

// 2. 调用 fs.readFile() 读取文件的内容
fs.readFile('../素材/成绩.txt', 'utf8', function(err, dataStr) {
  // 3. 判断是否读取成功
  if (err) {
    return console.log('读取文件失败！' + err.message)
  }
  // console.log('读取文件成功！' + dataStr)

  // 4.1 先把成绩的数据，按照空格进行分割
  const arrOld = dataStr.split(' ')
  // 4.2 循环分割后的数组，对每一项数据，进行字符串的替换操作
  const arrNew = []
  arrOld.forEach(item => {
    arrNew.push(item.replace('=', '：'))
  })
  // 4.3 把新数组中的每一项，进行合并，得到一个新的字符串
  const newStr = arrNew.join('\r\n')

  // 5. 调用 fs.writeFile() 方法，把处理完毕的成绩，写入到新文件中
  fs.writeFile('./files/成绩-ok.txt', newStr, function(err) {
    if (err) {
      return console.log('写入文件失败！' + err.message)
    }
    console.log('成绩写入成功！')
  })
})

```

**路径问题**

```javascript
const fs = require('fs')

// 出现路径拼接错误的问题，是因为提供了 ./ 或 ../ 开头的相对路径
// 如果要解决这个问题，可以直接提供一个完整的文件存放路径就行
/* fs.readFile('./files/1.txt', 'utf8', function(err, dataStr) {
  if (err) {
    return console.log('读取文件失败！' + err.message)
  }
  console.log('读取文件成功！' + dataStr)
}) */

// 移植性非常差、不利于维护
/* fs.readFile('C:\\Users\\escook\\Desktop\\Node.js基础\\day1\\code\\files\\1.txt', 'utf8', function(err, dataStr) {
  if (err) {
    return console.log('读取文件失败！' + err.message)
  }
  console.log('读取文件成功！' + dataStr)
}) */

// __dirname 表示当前文件所处的目录
// console.log(__dirname)

fs.readFile(__dirname + '/files/1.txt', 'utf8', function(err, dataStr) {
  if (err) {
    return console.log('读取文件失败！' + err.message)
  }
  console.log('读取文件成功！' + dataStr)
})
    
```

## path模块

```javascript
const path = require('path')
const fs = require('fs')

// 注意：  ../ 会抵消前面的路径
// const pathStr = path.join('/a', '/b/c', '../../', './d', 'e')
// console.log(pathStr)  // \a\b\d\e

// fs.readFile(__dirname + '/files/1.txt')

fs.readFile(path.join(__dirname, './files/1.txt'), 'utf8', function(err, dataStr) {
  if (err) {
    return console.log(err.message)
  }
  console.log(dataStr)
})
```

**获取文件名**

```javascript
const path = require('path')

// 定义文件的存放路径
const fpath = '/a/b/c/index.html'

// const fullName = path.basename(fpath)
// console.log(fullName)

const nameWithoutExt = path.basename(fpath, '.html')
console.log(nameWithoutExt)
```

**获取文件扩展名**

```javascript
const path = require('path')

// 这是文件的存放路径
const fpath = '/a/b/c/index.html'

const fext = path.extname(fpath)
console.log(fext)

```

**test**

```javascript
// 1.1 导入 fs 模块
const fs = require('fs')
// 1.2 导入 path 模块
const path = require('path')

// 1.3 定义正则表达式，分别匹配 <style></style> 和 <script></script> 标签
const regStyle = /<style>[\s\S]*<\/style>/
const regScript = /<script>[\s\S]*<\/script>/

// 2.1 调用 fs.readFile() 方法读取文件
fs.readFile(path.join(__dirname, '../素材/index.html'), 'utf8', function(err, dataStr) {
  // 2.2 读取 HTML 文件失败
  if (err) return console.log('读取HTML文件失败！' + err.message)
  // 2.3 读取文件成功后，调用对应的三个方法，分别拆解出 css, js, html 文件
  resolveCSS(dataStr)
  resolveJS(dataStr)
  resolveHTML(dataStr)
})

// 3.1 定义处理 css 样式的方法
function resolveCSS(htmlStr) {
  // 3.2 使用正则提取需要的内容
  const r1 = regStyle.exec(htmlStr)
  // 3.3 将提取出来的样式字符串，进行字符串的 replace 替换操作
  const newCSS = r1[0].replace('<style>', '').replace('</style>', '')
  // 3.4 调用 fs.writeFile() 方法，将提取的样式，写入到 clock 目录中 index.css 的文件里面
  fs.writeFile(path.join(__dirname, './clock/index.css'), newCSS, function(err) {
    if (err) return console.log('写入 CSS 样式失败！' + err.message)
    console.log('写入样式文件成功！')
  })
}

// 4.1 定义处理 js 脚本的方法
function resolveJS(htmlStr) {
  // 4.2 通过正则，提取对应的 <script></script> 标签内容
  const r2 = regScript.exec(htmlStr)
  // 4.3 将提取出来的内容，做进一步的处理
  const newJS = r2[0].replace('<script>', '').replace('</script>', '')
  // 4.4 将处理的结果，写入到 clock 目录中的 index.js 文件里面
  fs.writeFile(path.join(__dirname, './clock/index.js'), newJS, function(err) {
    if (err) return console.log('写入 JavaScript 脚本失败！' + err.message)
    console.log('写入 JS 脚本成功！')
  })
}

// 5.1 定义处理 HTML 结构的方法
function resolveHTML(htmlStr) {
  // 5.2 将字符串调用 replace 方法，把内嵌的 style 和 script 标签，替换为外联的 link 和 script 标签
  const newHTML = htmlStr.replace(regStyle, '<link rel="stylesheet" href="./index.css" />').replace(regScript, '<script src="./index.js"></script>')
  // 5.3 写入 index.html 这个文件
  fs.writeFile(path.join(__dirname, './clock/index.html'), newHTML, function(err) {
    if (err) return console.log('写入 HTML 文件失败！' + err.message)
    console.log('写入 HTML 页面成功！')
  })
}
// fs.writeFile是覆盖写
// fs.writeFile只能创建文件，不能创建路径
```

## HTTP模块

**创建最基础的web服务器**

```js
// 1. 导入 http 模块
const http = require('http')
// 2. 创建 web 服务器实例
const server = http.createServer()
// 3. 为服务器实例绑定 request 事件，监听客户端的请求
server.on('request', function (req, res) {
  console.log('Someone visit our web server.')
})
// 4. 启动服务器
server.listen(8080, function () {  
  console.log('server running at http://127.0.0.1:8080')
})

```

**req，res**

```js
const http = require('http')
const server = http.createServer()
// req 是请求对象，包含了与客户端相关的数据和属性
server.on('request', (req, res) => {
  // req.url 是客户端请求的 URL 地址
  const url = req.url
  // req.method 是客户端请求的 method 类型
  const method = req.method
  const str = `Your request url is ${url}, and request method is ${method}`
  console.log(str)
  // 调用 res.end() 方法，向客户端响应一些内容
  res.end(str)
})
server.listen(80, () => {
  console.log('server running at http://127.0.0.1')
})

```

**解决中文乱码问题**

```js
const http = require('http')
const server = http.createServer()

server.on('request', (req, res) => {
  // 定义一个字符串，包含中文的内容
  const str = `您请求的 URL 地址是 ${req.url}，请求的 method 类型为 ${req.method}`
  // 调用 res.setHeader() 方法，设置 Content-Type 响应头，解决中文乱码的问题
  res.setHeader('Content-Type', 'text/html; charset=utf-8')
  // res.end() 将内容响应给客户端
  res.end(str)
})

server.listen(80, () => {
  console.log('server running at http://127.0.0.1')
})

```

**根据不同的url响应不同的html内容**

```js
const http = require('http')
const server = http.createServer()

server.on('request', (req, res) => {
  // 1. 获取请求的 url 地址
  const url = req.url
  // 2. 设置默认的响应内容为 404 Not found
  let content = '<h1>404 Not found!</h1>'
  // 3. 判断用户请求的是否为 / 或 /index.html 首页
  // 4. 判断用户请求的是否为 /about.html 关于页面
  if (url === '/' || url === '/index.html') {
    content = '<h1>首页</h1>'
  } else if (url === '/about.html') {
    content = '<h1>关于页面</h1>'
  }
  // 5. 设置 Content-Type 响应头，防止中文乱码
  res.setHeader('Content-Type', 'text/html; charset=utf-8')
  // 6. 使用 res.end() 把内容响应给客户端
  res.end(content)
})

server.listen(80, () => {
  console.log('server running at http://127.0.0.1')
})

```

**test**

```js
// 1.1 导入 http 模块
const http = require('http')
// 1.2 导入 fs 模块
const fs = require('fs')
// 1.3 导入 path 模块
const path = require('path')

// 2.1 创建 web 服务器
const server = http.createServer()
// 2.2 监听 web 服务器的 request 事件
server.on('request', (req, res) => {
  // 3.1 获取到客户端请求的 URL 地址
  //     /clock/index.html
  //     /clock/index.css
  //     /clock/index.js
  const url = req.url
  // 3.2 把请求的 URL 地址映射为具体文件的存放路径
  // const fpath = path.join(__dirname, url)
  // 5.1 预定义一个空白的文件存放路径
  let fpath = ''
  if (url === '/') {
    fpath = path.join(__dirname, './clock/index.html')
  } else {
    //     /index.html
    //     /index.css
    //     /index.js
    fpath = path.join(__dirname, '/clock', url)
  }

  // 4.1 根据“映射”过来的文件路径读取文件的内容
  fs.readFile(fpath, 'utf8', (err, dataStr) => {
    // 4.2 读取失败，向客户端响应固定的“错误消息”
    if (err) return res.end('404 Not found.')
    // 4.3 读取成功，将读取成功的内容，响应给客户端
    res.end(dataStr)
  })
})
// 2.3 启动服务器
server.listen(80, () => {
  console.log('server running at http://127.0.0.1')
})

```

## 模块化

**加载自定义模块**

模块名：06.m1.js

```js
// 当前这个文件，就是一个用户自定义模块
console.log('加载了06这个用户自定义模块')
```

通过require加载模块会自动执行其中的代码
可以省略文件后缀

```js
// 注意：在使用 require 加载用户自定义模块期间，
// 可以省略 .js 的后缀名
const m1 = require('./06.m1.js')
console.log(m1)

```

**模块的作用域**

无法访问模块内部的属性和方法只能执行可执行代码

```js
const username = '张三'

function sayHello() {
  console.log('大家好，我是' + username)
}
```

```js
const custom = require('./08.模块作用域')

console.log(custom)
```

**暴露模块中的成员**

打印模块对象

```js
console.log(module)

```

运行结果

```result
Module {
  id: '.',
  path: 'E:\\资料\\黑马nodejs\\day2\\code',
  exports: {},
  filename: 'E:\\资料\\黑马nodejs\\day2\\code\\10.演示module对象.js',
  loaded: false,
  children: [],
  paths: [
    'E:\\资料\\黑马nodejs\\day2\\code\\node_modules',
    'E:\\资料\\黑马nodejs\\day2\\node_modules',
    'E:\\资料\\黑马nodejs\\node_modules',
    'E:\\资料\\node_modules',
    'E:\\node_modules'
  ]
}
```

暴露模块中的成员

```js
// 在一个自定义模块中，默认情况下， module.exports = {}

const age = 20

// 向 module.exports 对象上挂载 username 属性
module.exports.username = 'zs'
// 向 module.exports 对象上挂载 sayHello 方法
module.exports.sayHello = function() {
  console.log('Hello!')
}
module.exports.age = age

// 让 module.exports 指向一个全新的对象
module.exports = {
  nickname: '小黑',
  sayHi() {
    console.log('Hi!')
  }
}
```

调用模块

```js
// 在外界使用 require 导入一个自定义模块的时候，得到的成员，
// 就是 那个模块中，通过 module.exports 指向的那个对象
const m = require('./11.自定义模块')

console.log(m)
```

运行结果

```result

{ nickname: '小黑', sayHi: [Function: sayHi] }
```

**export对象**

```js
// console.log(exports)
// console.log(module.exports)

// console.log(exports === module.exports)

const username = 'zs'

module.exports.username = username
exports.age = 20
exports.sayHello = function() {
  console.log('大家好！')
}

// 最终，向外共享的结果，永远都是 module.exports 所指向的对象

```

exports 和 module.exports 的区别
在 Node.js 中，`exports` 和 `module.exports` 是用于导出模块内容的关键字，用于在模块之间共享变量、函数、对象或类等。

- **`module.exports`：** 是实际导出模块内容的对象。当你希望整个模块作为一个对象被导出时，你可以直接赋值给 `module.exports`。例如：
  
  ```javascript
  // moduleA.js
  module.exports = {
      foo: 'bar',
      someFunction: function() {
          // do something
      }
  };
  ```

- **`exports`：** 是 `module.exports` 的一个引用。它是一个特殊的对象，如果你直接给 `exports` 赋值，它会改变引用，但不会改变模块的导出结果。默认情况下，`exports` 指向的是 `module.exports`。例如：

  ```javascript
  // moduleB.js
  exports.name = 'John';

  // 这等同于：
  // module.exports.name = 'John';
  ```

如果你只是给 `exports` 添加属性或方法，它会被添加到 `module.exports` 对象中。但如果你直接给 `exports` 赋予一个新的对象，它会覆盖 `module.exports` 的引用，这可能导致你的导出结果不如预期。

因此，当你希望导出一个单独的对象（例如，一个函数、一个类、一个对象字面量等），最好直接赋值给 `module.exports`。如果你希望导出多个变量或函数，可以使用 `exports` 的属性来添加到 `module.exports` 上。

**module.exports和exports指向的是同一个对象**

## npm和包

**安装包**

`npm install 包名`或者`npm i 包名`

`npm i moment@2.22.2`安转指定版本的包

`npm i nrm -g`安装全局包

`npm install -g pnpm@latest`安装最新版本

**包的语义化规范**

- 第一位数字：大版本
- 第二位数字：小版本
- 第三位数字：bug修复

版本号提升规则：只要前面的版本号增长了后面的数字就要归零

**node_modules**

用来存放已安装到项目中的包

**package-lock.json**

- 记录每个包的信息例如：包名，版本，下载地址
- 项目中都用到了那些包
- 那些包会在开发期间用到
- 那些包会在开发和部署时用到

**package.json包管理配置文件**

package.json便于进行包管理完成合作开发  

`npm init -y`创建package.json文件记录安装的包

dependencies节点记录安装了那些包

`npm i`安装package.json中记录的包

`npm uninstall 包名`卸载安装的包

`npm i 包名 -D`或者`npm i 包名 --save-dev`安装包到开发环境

`npm config get registry`查看下载源

`npm config set registry https://npm.aliyun.com`设置镜像源

**nrm**

`nrm ls`查看所有可用镜像源

`nrm use taobao`切换镜像源

**包的分类**

- 项目包：被安装在node_modules目录下的包
  - 开发依赖包：被记录在devDependencies节点下的包，只在开发期间会用到
  - 核心依赖包：被记录在dependencies节点下的包，在开发期间和部署之后都会用到
- 全局包：安装在C:\Users\Lenovo\AppData\Roaming\npm\node_modules

**开发属于自己的包**

包的基本结构

- package.json（包管理配置文件）

```json
{
  "name": "itheima-tools",
  "version": "1.1.0",
  "main": "index.js", // 当导入文件时自动加载main属性的index.js文件
  "description": "提供了格式化时间、HTMLEscape相关的功能",
  "keywords": [
    "itheima",
    "dateFormat",
    "escape"
  ],
  "license": "ISC"
}
```

- index.js（包的入口文件）

```js
// 这是包的入口文件

const date = require('./src/dateFormat')
const escape = require('./src/htmlEscape')

// 向外暴露需要的成员
module.exports = {
  ...date,
  ...escape
}

```

**包的目录结构**

```result
├─index.js
├─package.json
├─README.md
├─src
|  ├─dateFormat.js
|  └htmlEscape.js
```

- README.md（包的说明文档）

```md
    ## 安装
    ```
    npm install itheima-tools
    ```

    ## 导入
    ```js
    const itheima = require('itheima-tools')
    ```

    ## 格式化时间

    ```js
    // 调用 dateFormat 对时间进行格式化
    const dtStr = itheima.dateFormat(new Date())
    // 结果  2020-04-03 17:20:58
    console.log(dtStr)
    ```

    ## 转义 HTML 中的特殊字符

    ```js
    // 带转换的 HTML 字符串
    const htmlStr = '<h1 title="abc">这是h1标签<span>123&nbsp;</span></h1>'
    // 调用 htmlEscape 方法进行转换
    const str = itheima.htmlEscape(htmlStr)
    // 转换的结果 &lt;h1 title=&quot;abc&quot;&gt;这是h1标签&lt;span&gt;123&amp;nbsp;&lt;/span&gt;&lt;/h1&gt;
    console.log(str)
    ```

    ## 还原 HTML 中的特殊字符

    ```js
    // 待还原的 HTML 字符串
    const str2 = itheima.htmlUnEscape(str)
    // 输出的结果 <h1 title="abc">这是h1标签<span>123&nbsp;</span></h1>
    console.log(str2)
    ```

    ## 开源协议

    ISC
```

**发布包**

发布包时的npm服务器必须是官方服务器

在终端登录npm账户`npm login`
发布包在包的根目录运行`npm publish`
删除已发布的包`npm unpublish 包名 --force`

- 只能删除72小时内发布的包
- 被删除掉包24小时内不能重新发布

**模块的加载机制**

优先从缓存加载，提高模块的加载效率

**内置模块的加载机制**

内置模块加载的优先级是最高的，如果有和内置模块同名的模块永远优先加载内置模块

**自定义模块的加载机制**

在加载自定义模块式必须以路径标识符为开头，否则会被识别为内置模块或者第三方模块
如果省略了模块的扩展名nodejs会按以下顺序加载文件

1. 按照确切文件名加载
2. 补js后缀
3. 补json后缀
4. 补node后缀
5. 保存

**第三方模块的加载机制**

如果传递给 require() 的模块标识符不是一个内置模块，也没有以 ‘./’ 或 ‘../’ 开头，则 Node.js 会从当前模块的父
目录开始，尝试从 /node_modules 文件夹中加载第三方模块。
如果没有找到对应的第三方模块，则移动到再上一层父目录中，进行加载，直到文件系统的根目录。
例如，假设在 'C:\Users\itheima\project\foo.js' 文件里调用了 require('tools')，则 Node.js 会按以下顺序查找：

1. C:\Users\itheima\project\node_modules\tools
2. C:\Users\itheima\node_modules\tools
3. C:\Users\node_modules\tools
4. C:\node_modules\tools

**目录作为模块**

当把目录作为模块标识符，传递给 require() 进行加载的时候，有三种加载方式：

1. 在被加载的目录下查找一个叫做 package.json 的文件，并寻找 main 属性，作为 require() 加载的入口
2. 如果目录里没有 package.json 文件，或者 main 入口不存在或无法解析，则 Node.js 将会试图加载目录下的 index.js 文件。
3. 如果以上两步都失败了，则 Node.js 会在终端打印错误消息，报告模块的缺失：Error: Cannot find module 'xxx'

## express

**创建web服务器监听get和post请求**

```js
// 1. 导入 express
const express = require('express')
// 2. 创建 web 服务器
const app = express()

// 4. 监听客户端的 GET 和 POST 请求，并向客户端响应具体的内容
app.get('/user', (req, res) => {
  // 调用 express 提供的 res.send() 方法，向客户端响应一个 JSON 对象
  res.send({ name: 'zs', age: 20, gender: '男' })
})
app.post('/user', (req, res) => {
  // 调用 express 提供的 res.send() 方法，向客户端响应一个 文本字符串
  res.send('请求成功')
})
app.get('/', (req, res) => {
  // 通过 req.query 可以获取到客户端发送过来的 查询参数
  // 注意：默认情况下，req.query 是一个空对象
  console.log(req.query)
  res.send(req.query)
})
// 注意：这里的 :id 是一个动态的参数
app.get('/user/:ids/:username', (req, res) => {
  // req.params 是动态匹配到的 URL 参数，默认也是一个空对象
  console.log(req.params)
  res.send(req.params)
})

// 3. 启动 web 服务器
app.listen(80, () => {
  console.log('express server running at http://127.0.0.1')
})

```

**托管静态资源**

```js
const express = require('express')
const app = express()

// 在这里，调用 express.static() 方法，快速的对外提供静态资源
// /files 添加访问前缀
app.use('/files', express.static('./files'))
app.use(express.static('./clock'))

app.listen(80, () => {
  console.log('express server running at http://127.0.0.1')
})
```

**nodemon**

监听项目的代码当代码改变后自动重新运行项目
使用方法使用`nodemon 项目`运行项目

**express路由**

```js
const express = require('express')
const app = express()

// 挂载路由
app.get('/', (req, res) => {
  res.send('hello world.')
})
app.post('/', (req, res) => {
  res.send('Post Request.')
})

app.listen(80, () => {
  console.log('http://127.0.0.1')
})

```

**模块化路由**

```js
const express = require('express')
const app = express()

// app.use('/files', express.static('./files'))

// 1. 导入路由模块
const router = require('./03.router')
// 2. 注册路由模块
// 添加访问前缀
app.use('/api', router)

// 注意： app.use() 函数的作用，就是来注册全局中间件

app.listen(80, () => {
  console.log('http://127.0.0.1')
})

```

路由模块

```js
// 这是路由模块
// 1. 导入 express
const express = require('express')
// 2. 创建路由对象
const router = express.Router()

// 3. 挂载具体的路由
router.get('/user/list', (req, res) => {
  res.send('Get user list.')
})
router.post('/user/add', (req, res) => {
  res.send('Add new user.')
})

// 4. 向外导出路由对象
module.exports = router

```

**express中间件**

在前端开发中，中间件（middleware）是一种常见的软件设计模式，用于在处理请求或操作执行前后执行一些额外的逻辑。在前端中，特别是在一些框架或库中，中间件被用来处理诸如路由、状态管理、日志记录等方面的操作

![images](./images/屏幕截图%202023-11-26%20164005.png)

**中间价的格式**

![images](./images/屏幕截图%202023-11-26%20164134.png)

next()函数的作用

![images](./images/屏幕截图%202023-11-26%20164330.png)

**定义最简单的中间件并注册为全局使用**

```js
const express = require('express')
const app = express()

// // 定义一个最简单的中间件函数
// const mw = function (req, res, next) {
//   console.log('这是最简单的中间件函数')
//   // 把流转关系，转交给下一个中间件或路由
//   next()
// }

// // 将 mw 注册为全局生效的中间件
// app.use(mw)

// 这是定义全局中间件的简化形式
app.use((req, res, next) => {
  console.log('这是最简单的中间件函数')
  next()
})

app.get('/', (req, res) => {
  console.log('调用了 / 这个路由')
  res.send('Home page.')
})
app.get('/user', (req, res) => {
  console.log('调用了 /user 这个路由')
  res.send('User page.')
})

app.listen(80, () => {
  console.log('http://127.0.0.1')
})

```

**体验中间件的作用类似后端spring的AOP**

```js
const express = require('express')
const app = express()

// 这是定义全局中间件的简化形式
app.use((req, res, next) => {
  // 获取到请求到达服务器的时间
  const time = Date.now()
  // 为 req 对象，挂载自定义属性，从而把时间共享给后面的所有路由
  req.startTime = time
  next()
})

app.get('/', (req, res) => {
  res.send('Home page.' + req.startTime)
})
app.get('/user', (req, res) => {
  res.send('User page.' + req.startTime)
})

app.listen(80, () => {
  console.log('http://127.0.0.1')
})

```

**定义多个全局中间件**

```js
const express = require('express')
const app = express()

// 定义第一个全局中间件
app.use((req, res, next) => {
  console.log('调用了第1个全局中间件')
  next()
})
// 定义第二个全局中间件
app.use((req, res, next) => {
  console.log('调用了第2个全局中间件')
  next()
})

// 定义一个路由
app.get('/user', (req, res) => {
  res.send('User page.')
})

app.listen(80, () => {
  console.log('http://127.0.0.1')
})

```

**局部生效的中间件**

```js
// 导入 express 模块
const express = require('express')
// 创建 express 的服务器实例
const app = express()

// 1. 定义中间件函数
const mw1 = (req, res, next) => {
  console.log('调用了局部生效的中间件')
  next()
}

// 2. 创建路由
app.get('/', mw1, (req, res) => {
  res.send('Home page.')
})
app.get('/user', (req, res) => {
  res.send('User page.')
})

// 调用 app.listen 方法，指定端口号并启动web服务器
app.listen(80, function () {
  console.log('Express server running at http://127.0.0.1')
})

```

**多个局部生效的中间件**

```js
// 导入 express 模块
const express = require('express')
// 创建 express 的服务器实例
const app = express()

// 1. 定义中间件函数
const mw1 = (req, res, next) => {
  console.log('调用了第一个局部生效的中间件')
  next()
}

const mw2 = (req, res, next) => {
  console.log('调用了第二个局部生效的中间件')
  next()
}

// 2. 创建路由
app.get('/', [mw1, mw2], (req, res) => {
  res.send('Home page.')
})
app.get('/user', (req, res) => {
  res.send('User page.')
})

// 调用 app.listen 方法，指定端口号并启动web服务器
app.listen(80, function () {
  console.log('Express server running at http://127.0.0.1')
})

```

**中间件的注意事项**

1. 在路由之前注册中间件
2. 客户端发来请求，可以调用多个中间件进行处理
3. 执行完中间件的业务代码不要忘记next()函数
4. 调用完next()函数后不在在写额外的代码
5. 连续调用多个中间件，共享req和res对象

**中间件的分类**

1. 应用级别的中间件
    通过 app.use() 或 app.get() 或 app.post() ，绑定到 app 实例上的中间件，叫做应用级别的中间件
2. 路由级别的中间件
    绑定到 express.Router() 实例上的中间件，叫做路由级别的中间件。它的用法和应用级别中间件没有任何区别。只不过，应用级别中间件是绑定到 app 实例上，路由级别中间件绑定到 router 实例上
3. 错误级别的中间件
    错误级别中间件的作用：专门用来捕获整个项目中发生的异常错误，从而防止项目异常崩溃的问题。
    格式：错误级别中间件的 function 处理函数中，必须有 4 个形参，形参顺序从前到后，分别是 (err, req, res, next)。
    **注意：错误级别的中间件，必须注册在所有路由之后！**

    ```js
    // 导入 express 模块
    const express = require('express')
    // 创建 express 的服务器实例
    const app = express()

    // 1. 定义路由
    app.get('/', (req, res) => {
    // 1.1 人为的制造错误
    throw new Error('服务器内部发生了错误！')
    res.send('Home page.')
    })
    
    // 2. 定义错误级别的中间件，捕获整个项目的异常错误，从而防止程序的崩溃
    app.use((err, req, res, next) => {
    console.log('发生了错误！' + err.message)
    res.send('Error：' + err.message)
    })

    // 调用 app.listen 方法，指定端口号并启动web服务器
    app.listen(80, function () {
    console.log('Express server running at http://127.0.0.1')
    })
    ```

4. Express 内置的中间件
    自 Express 4.16.0 版本开始，Express 内置了 3 个常用的中间件，极大的提高了 Express 项目的开发效率和体验：
    express.static 快速托管静态资源的内置中间件，例如： HTML 文件、图片、CSS 样式等（无兼容性）
    express.json 解析 JSON 格式的请求体数据（有兼容性，仅在 4.16.0+ 版本中可用）
    express.urlencoded 解析 URL-encoded 格式的请求体数据（有兼容性，仅在 4.16.0+ 版本中可用）
    **内置中间件的使用**

    ```js
    // 导入 express 模块
    const express = require('express')
    // 创建 express 的服务器实例
    const app = express()

    // 注意：除了错误级别的中间件，其他的中间件，必须在路由之前进行配置
    // 通过 express.json() 这个中间件，解析表单中的 JSON 格式的数据
    app.use(express.json())
    // 通过 express.urlencoded() 这个中间件，来解析 表单中的 url-encoded 格式的数据
    app.use(express.urlencoded({ extended: false }))

    app.post('/user', (req, res) => {
      // 在服务器，可以使用 req.body 这个属性，来接收客户端发送过来的请求体数据
      // 默认情况下，如果不配置解析表单数据的中间件，则 req.body 默认等于 undefined
      console.log(req.body)
      res.send('ok')
    })

    app.post('/book', (req, res) => {
      // 在服务器端，可以通过 req,body 来获取 JSON 格式的表单数据和 url-encoded 格式的数据
      console.log(req.body)
      res.send('ok')
    })

    // 调用 app.listen 方法，指定端口号并启动web服务器
    app.listen(80, function () {
      console.log('Express server running at http://127.0.0.1')
    })

    ```

5. 第三方的中间件

    非 Express 官方内置的，而是由第三方开发出来的中间件，叫做第三方中间件。在项目中，大家可以按需下载并配置
    第三方中间件，从而提高项目的开发效率。
    例如：在 express@4.16.0 之前的版本中，经常使用 body-parser 这个第三方中间件，来解析请求体数据。使用步骤如下：
    运行 `npm install body-parser` 安装中间件
    使用 `require` 导入中间件
    调用 `app.use()` 注册并使用中间件

    ```js
    // 导入 express 模块
    const express = require('express')
    // 创建 express 的服务器实例
    const app = express()

    // 1. 导入解析表单数据的中间件 body-parser
    const parser = require('body-parser')
    // 2. 使用 app.use() 注册中间件
    app.use(parser.urlencoded({ extended: false }))
    // app.use(express.urlencoded({ extended: false }))

    app.post('/user', (req, res) => {
      // 如果没有配置任何解析表单数据的中间件，则 req.body 默认等于 undefined
      console.log(req.body)
      res.send('ok')
    })

    // 调用 app.listen 方法，指定端口号并启动web服务器
    app.listen(80, function () {
      console.log('Express server running at http://127.0.0.1')
    })
    ```

**自定义解析表单数据中间件**

```js
// 导入 express 模块
const express = require('express')
// 创建 express 的服务器实例
const app = express()
// 导入 Node.js 内置的 querystring 模块
const qs = require('querystring')

// 这是解析表单数据的中间件
app.use((req, res, next) => {
  // 定义中间件具体的业务逻辑
  // 1. 定义一个 str 字符串，专门用来存储客户端发送过来的请求体数据
  let str = ''
  // 2. 监听 req 的 data 事件
  req.on('data', (chunk) => {
    str += chunk
  })
  // 3. 监听 req 的 end 事件
  req.on('end', () => {
    // 在 str 中存放的是完整的请求体数据
    // console.log(str)
    // TODO: 把字符串格式的请求体数据，解析成对象格式
    const body = qs.parse(str)
    req.body = body
    next()
  })
})

app.post('/user', (req, res) => {
  res.send(req.body)
})

// 调用 app.listen 方法，指定端口号并启动web服务器
app.listen(80, function () {
  console.log('Express server running at http://127.0.0.1')
})

```

**对自定义中间件模块化拆分**

```js
// 导入 express 模块
const express = require('express')
// 创建 express 的服务器实例
const app = express()

// 1. 导入自己封装的中间件模块
const customBodyParser = require('./14.custom-body-parser')
// 2. 将自定义的中间件函数，注册为全局可用的中间件
app.use(customBodyParser)

app.post('/user', (req, res) => {
  res.send(req.body)
})

// 调用 app.listen 方法，指定端口号并启动web服务器
app.listen(80, function () {
  console.log('Express server running at http://127.0.0.1')
})

```

```js
// 14.custom-body-parser模块
// 导入 Node.js 内置的 querystring 模块
const qs = require('querystring')

const bodyParser = (req, res, next) => {
  // 定义中间件具体的业务逻辑
  // 1. 定义一个 str 字符串，专门用来存储客户端发送过来的请求体数据
  let str = ''
  // 2. 监听 req 的 data 事件
  req.on('data', (chunk) => {
    str += chunk
  })
  // 3. 监听 req 的 end 事件
  req.on('end', () => {
    // 在 str 中存放的是完整的请求体数据
    // console.log(str)
    // TODO: 把字符串格式的请求体数据，解析成对象格式
    const body = qs.parse(str)
    req.body = body
    next()
  })
}

module.exports = bodyParser

```

**使用express编写接口**

```js
// 导入 express
const express = require('express')
// 创建服务器实例
const app = express()

// 配置解析表单数据的中间件
app.use(express.urlencoded({ extended: false }))

// 必须在配置 cors 中间件之前，配置 JSONP 的接口
app.get('/api/jsonp', (req, res) => {
  // TODO: 定义 JSONP 接口具体的实现过程
  // 1. 得到函数的名称
  const funcName = req.query.callback
  // 2. 定义要发送到客户端的数据对象
  const data = { name: 'zs', age: 22 }
  // 3. 拼接出一个函数的调用
  const scriptStr = `${funcName}(${JSON.stringify(data)})`
  // 4. 把拼接的字符串，响应给客户端
  res.send(scriptStr)
})

// 一定要在路由之前，配置 cors 这个中间件，从而解决接口跨域的问题
const cors = require('cors')
app.use(cors())

// 导入路由模块
const router = require('./16.apiRouter')
// 把路由模块，注册到 app 上
app.use('/api', router)

// 启动服务器
app.listen(80, () => {
  console.log('express server running at http://127.0.0.1')
})
```

接口

```js
const express = require('express')
const router = express.Router()

// 在这里挂载对应的路由
router.get('/get', (req, res) => {
  // 通过 req.query 获取客户端通过查询字符串，发送到服务器的数据
  const query = req.query
  // 调用 res.send() 方法，向客户端响应处理的结果
  res.send({
    status: 0, // 0 表示处理成功，1 表示处理失败
    msg: 'GET 请求成功！', // 状态的描述
    data: query, // 需要响应给客户端的数据
  })
})

// 定义 POST 接口
router.post('/post', (req, res) => {
  // 通过 req.body 获取请求体中包含的 url-encoded 格式的数据
  const body = req.body
  // 调用 res.send() 方法，向客户端响应结果
  res.send({
    status: 0,
    msg: 'POST 请求成功！',
    data: body,
  })
})

// 定义 DELETE 接口
router.delete('/delete', (req, res) => {
  res.send({
    status: 0,
    msg: 'DELETE请求成功',
  })
})

module.exports = router

```

## 跨域问题

![images](./images/屏幕截图%202023-11-26%20183838.png)

**cors注意事项**

CORS 主要在服务器端进行配置。客户端浏览器无须做任何额外的配置，即可请求开启了 CORS 的接口。
CORS 在浏览器中有兼容性。只有支持 XMLHttpRequest Level2 的浏览器，才能正常访问开启了 CORS 的服务端接口（例如：IE10+、Chrome4+、FireFox3.5+）

**CORS 响应头部 - Access-Control-Allow-Origin**

响应头部中可以携带一个 Access-Control-Allow-Origin 字段，其语法如下:
其中，origin 参数的值指定了允许访问该资源的外域 URL。
例如，下面的字段值将只允许来自 <http://itcast.cn> 的请求：

```js
res.setHeader('Access-Control-Allow-Origin', 'http://itcast.cn')
```

如果指定了 Access-Control-Allow-Origin 字段的值为通配符 *，表示允许来自任何域的请求，示例代码如下：

```js
res.setHeader('Access-Control-Allow-Origin', '*')
```

**CORS 响应头部 - Access-Control-Allow-Headers**

默认情况下，CORS 仅支持客户端向服务器发送如下的 9 个请求头：
Accept、Accept-Language、Content-Language、DPR、Downlink、Save-Data、Viewport-Width、Width 、Content-Type （值仅限于 text/plain、multipart/form-data、application/x-www-form-urlencoded 三者之一）
如果客户端向服务器发送了额外的请求头信息，则需要在服务器端，通过 Access-Control-Allow-Headers 对额外的请求头进行声明，否则这次请求会失败！

```js
// 允许客户端额外向服务器发送Context-Type和X-Custom-Header请求头
// 多个请求头之间用逗号分割
res.setHeader('Access-Control-Allow-Headers','Context-Type', 'X-Custom-Header')
```

**CORS 响应头部 - Access-Control-Allow-Methods**

默认情况下，CORS 仅支持客户端发起 GET、POST、HEAD 请求。
如果客户端希望通过 PUT、DELETE 等方式请求服务器的资源，则需要在服务器端，通过 Access-Control-Alow-Methods
来指明实际请求所允许使用的 HTTP 方法。

```js
// 允许制定方法
res.setHeader('Access-Control-Allow-Methods', 'POST, GET, DELETE, HEAD')
// 允许所有方法
res.setHeader('Access-Control-Allow-Methods', '*')
```

**CORS请求的分类**

客户端在请求 CORS 接口时，根据请求方式和请求头的不同，可以将 CORS 的请求分为两大类，分别是：

1. 简单请求
    同时满足以下两大条件的请求，就属于简单请求：
    ① 请求方式：GET、POST、HEAD 三者之一
    ② HTTP 头部信息不超过以下几种字段：无自定义头部字段、Accept、Accept-Language、Content-Language、DPR、
    Downlink、Save-Data、Viewport-Width、Width 、Content-Type（只有三个值application/         x-www-formurlencoded、multipart/form-data、text/plain）
2. 预检请求
    只要符合以下任何一个条件的请求，都需要进行预检请求：
    ① 请求方式为 GET、POST、HEAD 之外的请求 Method 类型
    ② 请求头中包含自定义头部字段
    ③ 向服务器发送了 application/json 格式的数据
    **在浏览器与服务器正式通信之前，浏览器会先发送 OPTION 请求进行预检，以获知服务器是否允许该实际请求，所以这一次的 OPTION 请求称为“预检请求”。服务器成功响应预检请求后，才会发送真正的请求，并且携带真实数据。**

**简单请求和预检请求的区别**

简单请求的特点：客户端与服务器之间只会发生一次请求。
预检请求的特点：客户端与服务器之间会发生两次请求，OPTION 预检请求成功之后，才会发起真正的请求。

![images]()
