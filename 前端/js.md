# js

## js的引入方式

JavaScript 可以通过多种方式引入到网页中，常见的方法包括：

### 1. 内联脚本 (Inline Script)

直接在 HTML 文件中的 `<script>` 标签内编写 JavaScript 代码。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Inline Script Example</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <script>
        console.log('Hello from inline script!');
    </script>
</body>
</html>
```

### 2. 内部脚本 (Internal Script)

将 JavaScript 代码放在 `<script>` 标签中，但在 `<head>` 或 `<body>` 的任何位置。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Internal Script Example</title>
    <script>
        function greet() {
            console.log('Hello from internal script!');
        }
    </script>
</head>
<body>
    <h1>Hello, World!</h1>
    <button onclick="greet()">Greet</button>
</body>
</html>
```

### 3. 外部脚本 (External Script)

将 JavaScript 代码放在单独的 `.js` 文件中，并在 HTML 中通过 `<script>` 标签的 `src` 属性引用该文件。

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>External Script Example</title>
    <script src="script.js"></script>
</head>
<body>
    <h1>Hello, World!</h1>
</body>
</html>
```

```javascript
// script.js
console.log('Hello from external script!');
```

### 4. 模块化脚本 (Module Script)

使用 `type="module"` 属性引入模块化的 JavaScript 文件，这种方式支持使用 ES6 模块特性。

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Module Script Example</title>
    <script type="module" src="module.js"></script>
</head>
<body>
    <h1>Hello, World!</h1>
</body>
</html>
```

```javascript
// module.js
import { greet } from './greet.js';
greet();
```

```javascript
// greet.js
export function greet() {
    console.log('Hello from module script!');
}
```

### 5. 动态脚本 (Dynamic Script)

使用 JavaScript 动态地创建并插入 `<script>` 标签。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Dynamic Script Example</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <script>
        const script = document.createElement('script');
        script.src = 'dynamic.js';
        document.body.appendChild(script);
    </script>
</body>
</html>
```

```javascript
// dynamic.js
console.log('Hello from dynamic script!');
```

### 6. Deferred 和 Async 属性

外部脚本可以使用 `defer` 或 `async` 属性来控制脚本加载和执行的时机。

- `defer`: 脚本会被延迟执行，直到整个页面都解析完毕。
- `async`: 脚本会异步加载，并在加载完成后立即执行。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Deferred and Async Scripts Example</title>
    <script src="deferred.js" defer></script>
    <script src="async.js" async></script>
</head>
<body>
    <h1>Hello, World!</h1>
</body>
</html>
```

```javascript
// deferred.js
console.log('Hello from deferred script!');
```

```javascript
// async.js
console.log('Hello from async script!');
```

这些方式各有其应用场景，根据实际需求选择合适的引入方式可以提高页面的性能和可维护性。

## js变量

在 JavaScript 中，定义变量的三个关键字是 `var`、`let` 和 `const`。每个关键字都有其特定的作用域和行为特性。以下是对这三个关键字的详细解释：

### 1. `var`

#### 特点：
- **函数作用域**：`var` 声明的变量在函数内部是局部的，但在其他任何地方（如块作用域）则是全局的。
- **变量提升**：`var` 声明的变量会被提升到函数或全局作用域的顶部，但不会提升其赋值。

#### 示例：
```javascript
function example() {
    console.log(a); // undefined
    var a = 10;
    console.log(a); // 10
}
example();
```

在这个例子中，变量 `a` 在函数作用域内被提升了，但由于赋值在 `console.log(a)` 之后，所以第一次输出是 `undefined`。

### 2. `let`

#### 特点：
- **块作用域**：`let` 声明的变量只在其所在的块作用域内有效。
- **不允许重复声明**：在同一作用域内，不能使用 `let` 重新声明一个已经用 `let` 声明过的变量。
- **变量提升**：`let` 声明的变量也会提升，但在声明之前不能访问（即“暂时性死区”）。

#### 示例：
```javascript
function example() {
    console.log(a); // ReferenceError: Cannot access 'a' before initialization
    let a = 10;
    console.log(a); // 10
}
example();
```

在这个例子中，由于 `a` 在声明之前不能被访问，所以第一次输出会抛出一个 `ReferenceError`。

### 3. `const`

#### 特点：
- **块作用域**：`const` 声明的变量只在其所在的块作用域内有效。
- **不允许重复声明**：在同一作用域内，不能使用 `const` 重新声明一个已经用 `const` 声明过的变量。
- **必须初始化**：使用 `const` 声明变量时，必须同时进行初始化。
- **不可变引用**：`const` 声明的变量不能被重新赋值，但如果变量引用的是一个对象或数组，修改对象或数组的内容是允许的。

#### 示例：
```javascript
function example() {
    const a = 10;
    console.log(a); // 10
    a = 20; // TypeError: Assignment to constant variable.
}
example();
```

在这个例子中，尝试重新赋值 `a` 会抛出一个 `TypeError`。

对于对象或数组的示例：
```javascript
const obj = { key: 'value' };
obj.key = 'new value'; // 允许
console.log(obj.key); // 'new value'

const arr = [1, 2, 3];
arr.push(4); // 允许
console.log(arr); // [1, 2, 3, 4]
```

在这两个例子中，虽然 `obj` 和 `arr` 是用 `const` 声明的，但我们可以修改它们的内容。

