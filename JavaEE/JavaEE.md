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