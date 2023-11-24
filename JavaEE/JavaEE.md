# 1

## 前端

### javascript

#### js中let和const的区别

`let` 和 `const` 是 JavaScript 中声明变量的两种方式，它们有一些重要的区别：

1. **可变性：**
   - `let` 声明的变量是可变的，可以重新赋值。
   - `const` 声明的变量是常量，一旦被赋值，就不能再被重新赋值。

2. **作用域：**
   - `let` 和 `const` 都具有块级作用域，在声明它们的块（例如，函数、循环或花括号 `{}` 内部）中可见。
   - 用 `var` 声明的变量具有函数级作用域，在函数内部可见。

3. **初始化：**
   - 使用 `let` 声明的变量可以先声明后初始化，它们可以在声明之后被赋值。
   - 使用 `const` 声明的变量必须在声明时进行初始化，一旦声明，就必须立即赋值。

4. **全局对象属性：**
   - 用 `let` 声明的变量不会成为全局对象的属性。
   - 用 `const` 声明的变量不会成为全局对象的属性，但如果用 `const` 声明了一个对象，那么该对象的属性可以被修改，但不能重新分配一个新的对象给这个变量。

示例：

```javascript
let a = 1;
a = 2; // 可行

const b = 3;
// b = 4; // 不可行，会抛出错误

let c;
c = 5; // 可行

const d; // 错误，const声明必须进行初始化

// 全局对象属性
let globalVar = 10;
const globalConst = 20;
console.log(window.globalVar); // undefined
console.log(window.globalConst); // undefined
```

选择使用 `let` 还是 `const` 取决于变量是否需要被重新赋值。如果你希望创建一个不会被重新赋值的常量，使用 `const` 是一个很好的选择。

### nodejs

#### 什么是nodejs

nodejs是JavaScript的运行环境(基于chrome v8引擎)
在浏览器中的js代码是运行在浏览器自带的环境上，在自己的电脑上运行的js代码是需要nodejs

#### 使用执行nodejs执行JavaScript代码

终端执行命令 `node 文件名.js`

#### nodejs自带模块

#### fs文件系统模块

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

#### path模块

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

#### HTTP模块

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

#### 模块化

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

#### npm和包

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
- index.js（包的入口文件）
- README.md（包的说明文档）

## 后端

### Java

**== 和 equals 的区别**

![images](./images/屏幕截图%202023-11-05%20132315.png)
原文<https://blog.csdn.net/qq_44543508/article/details/95449363>

### JWT

Json Web Token
定义了一种简洁的、自包含的格式，用于通信双方以json数据格式安全的传输信息

![images](./images/屏幕截图%202023-11-04%20134846.png)
![images](./images/屏幕截图%202023-11-04%20135120.png)
![images](./images/屏幕截图%202023-11-04%20140017.png)
![images](./images/屏幕截图%202023-11-04%20140619.png)

### SpringBoot

**创建SpringBoot工程**

![images](./images/屏幕截图%202023-10-28%20124950.png)
![images](./images/屏幕截图%202023-10-28%20124732.png)
SpringBoot3.0以上的版本不支持Java8

![images]()