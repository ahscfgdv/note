# 移动web

## 平面渐变

**平面转换 transform**

作用：为元素添加动态效果，一般与过渡配合使用
概念：改变盒子在平面内的形态（位移、旋转、缩放、倾斜）
平面转换又叫 2D 转换

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>体验平面转换</title>
  <style>
    div {
      margin: 100px 0;

      width: 100px;
      height: 100px;
      background-color: pink;
      
      transition: all 1s;
    }

    /* 鼠标滑过：添加动态效果 */
    div:hover {
      transform: translate(800px) rotate(360deg) scale(2) skew(180deg);
    }
    
  </style>
</head>
<body>
  <div></div>
</body>
</html>
```

**平面转换 – 平移**

属性
- transform: translate(X轴移动距离, Y轴移动距离);

取值
- 像素单位数值
- 百分比（参照盒子自身尺寸计算结果）
- 正负均可

技巧
- translate() 只写一个值，表示沿着 X 轴移动
- 单独设置 X 或 Y 轴移动距离：translateX() 或 translateY()

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>平移效果</title>
    <style>
        .father {
            width: 500px;
            height: 300px;
            margin: 100px auto;
            border: 1px solid #000;
        }
        
        .son {
            width: 200px;
            height: 100px;
            background-color: pink;
            transition: all 0.5s;
        }
    
        /* 鼠标移入到父盒子，son改变位置 */
        .father:hover .son {
            transform: translate(200px, 100px);

            /* 百分比：参照盒子自身尺寸计算结果 */
            transform: translate(50%, 100%);
            transform: translate(-50%, 100%);

            /* 只写一个数表示水平方向 */
            transform: translate(100px);

            transform: translateY(100px);
            transform: translateX(100px);
        }
        
    </style>
</head>

<body>
    <div class="father">
        <div class="son"></div>
    </div>
</body>
</html>
```

**平移实现居中效果**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>绝对定位元素居中效果</title>
    <style>
        .box {
            position: absolute;
            left: 50%;
            top: 50%;

            /* 向左向上移动自身尺寸的一半 */
            transform: translate(-50%, -50%);

            width: 200px;
            height: 100px;
            background-color: pink;          
        }
    </style>
</head>
<body>
    <div class="box"></div>
</body>
</html>
```

**平面转换 – 旋转**

属性
- transform: rotate(旋转角度);
- 角度单位是 deg

技巧
- 取值正负均可
- 取值为正，顺时针旋转
- 取值为负，逆时针旋转

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>旋转效果</title>
  <style>
    img {
      width: 200px;
      transition: all 2s;
    }

    /* 鼠标悬停到图片上面，添加旋转效果 */
    img:hover {
      /* 正数：顺时针旋转；负数：逆时针旋转 */
      transform: rotate(360deg);
      transform: rotate(-360deg);
    }
  </style>
</head>
<body>
  <img src="./images/rotate.png" alt="">
</body>
</html>
```

**平面转换 – 改变转换原点**

默认情况下，转换原点是盒子中心点
属性
- transform-origin: 水平原点位置 垂直原点位置;

取值
- 方位名词（left、top、right、bottom、center）
- 像素单位数值
- 百分比

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>转换原点</title>
  <style>
    img {
      width: 200px;
      border: 1px solid #000;
      transition: all 1s;

      transform-origin: right bottom;
    }

    img:hover {
      transform: rotate(360deg);
    }
  </style>
</head>
<body>
  <img src="./images/rotate.png" alt="">
</body>
</html>
```

**平面转换 – 多重转换**

多重转换技巧：先平移再旋转
- transform: translate() rotate();

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>多重转换</title>
    <style>
      .box {
        width: 800px;
        height: 200px;
        border: 1px solid #000;
      }

      img {
        width: 200px;
        transition: all 5s;
      }

      /* 鼠标移入box，图片边走边转 */
      .box:hover img {
        /* 先平移再旋转 */
        transform: translate(600px) rotate(360deg);

        /* 旋转会改变坐标轴向 */
        /* 多重转换：以第一种转换形态的坐标轴为准 */
        /* transform: rotate(360deg) translate(600px); */

        /* 层叠性 */
        /* transform: translate(600px);
        transform: rotate(360deg); */
      }
    </style>
  </head>

  <body>
    <div class="box">
      <img src="./images/tyre1.png" alt="" />
    </div>
  </body>
</html>
```

**平面转换 – 缩放**

思考: 改变元素的width或height属性能实现吗？
属性
- transform: scale(缩放倍数);
- transform: scale(X轴缩放倍数, Y轴缩放倍数);

技巧
- 通常，只为 scale() 设置一个值，表示 X 轴和 Y 轴等比例缩放
- 取值大于1表示放大，取值小于1表示缩小

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>缩放效果</title>
    <style>
      .box {
        width: 300px;
        height: 210px;
        margin: 100px auto;
        background-color: pink;
      }

      .box img {
        width: 100%;
        transition: all 0.5s;
      }

      .box:hover img {
        /* 修改宽高尺寸，从左上角开始缩放 */
        /* width: 500px;
        height: 400px; */

        /* 大于1，表示放大 */
        transform: scale(2);

        /* 小于1，表示缩小 */
        transform: scale(0.5);

        /* 等于1，不变 */
        transform: scale(1);
      }
    </style>
  </head>

  <body>
    <div class="box">
      <img src="./images/product.jpeg" alt="" />
    </div>
  </body>
</html>

```

**平面转换 – 倾斜**

属性
- transform: skew();

取值
- 角度度数 deg

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>倾斜效果</title>
    <style>
      div {
        margin: 100px auto;
        width: 100px;
        height: 200px;
        background-color: pink;
        transition: all 0.5s;
      }

      div:hover {
        transform: skew(30deg);
        transform: skew(-30deg);
      }
    </style>
  </head>
  <body>
    <div></div>
  </body>
</html>
```

**渐变**

渐变是多个颜色逐渐变化的效果，一般用于设置盒子背景
分类
- 线性渐变
- 径向渐变

**线性渐变**
属性
background-image: linear-gradient(
渐变方向,
颜色1 终点位置,
颜色2 终点位置,
......
);

取值
渐变方向：可选
- to 方位名词
-  角度度数

终点位置：可选
- 百分比

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      div {
        width: 200px;
        height: 200px;
        background-color: green;
        background-image: linear-gradient(
          red,
          green
        );
        background-image: linear-gradient(
          to right,
          red,
          green
        );
        background-image: linear-gradient(
          45deg,
          red,
          green
        );
        background-image: linear-gradient(
          red 80%,
          green
        );
      }
    </style>
  </head>
  <body>
    <div></div>
  </body>
</html>
```

**径向渐变**

作用：给按钮添加高光效果
属性
background-image: radial-gradient(
半径 at 圆心位置,
颜色1 终点位置,
颜色2 终点位置,
......
);

取值
- 半径可以是2条，则为椭圆
- 圆心位置取值：像素单位数值 / 百分比 / 方位名词

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    div {
      width: 100px;
      height: 100px;
      background-color: pink; 
      border-radius: 50%;
      background-image: radial-gradient(
        50px at center center,
        red,
        pink
      );
      background-image: radial-gradient(
        50px 20px at center center,
        red,
        pink
      );
      background-image: radial-gradient(
        50px at 50px 30px,
        red,
        pink 50%
      );
    }

    button {
      width: 100px;
      height: 40px;
      background-color: green;
      border: 0;
      border-radius: 5px;
      color: #fff;
      background-image: radial-gradient(
        30px at 30px 20px,
        rgba(255, 255, 255, 0.2),
        transparent
      );
    }
  </style>
</head>
<body>
  <div></div>
  <button>按钮</button>
</body>
</html>
```

## 空间转换

**空间转换**

空间：是从坐标轴角度定义的 X 、Y 和 Z 三条坐标轴构成了一个立体空间，Z 轴位置与视线方向相同。
空间转换也叫 3D转换
属性：transform

**空间转换 – 平移**

属性
transform: translate3d(x, y, z);
transform: translateX();
transform: translateY();
transform: translateZ();

取值（正负均可）
- 像素单位数值
- 百分比（参照盒子自身尺寸计算结果）

提示
- 默认情况下，Z 轴平移没有效果

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <title>空间平移</title>
  <style>
    .box {
      width: 200px;
      height: 200px;
      margin: 100px auto;
      background-color: pink;
      transition: all 0.5s;
    }

    .box:hover {
      /* 电脑是平面，默认无法观察 Z 轴平移效果 */
      /* transform: translate3d(100px, 200px, 300px); */

      /* 3d 小括号里面必须逗号隔开三个数 */
      /* transform: translate3d(100px, 200px); */

      transform: translateX(100px);
      transform: translateY(-100%);
      transform: translateZ(300px);
    }
  </style>
</head>

<body>
  <div class="box"></div>
</body>
</html>
```

**视距 perspective**

作用：指定了观察者与 Z=0 平面的距离，为元素添加透视效果
透视效果：近大远小、近实远虚
属性：(添加给父级，取值范围 800-1200)
perspective: 视距;

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <title>透视效果</title>
  <style>
    /* 视距属性必须添加给 直接父级 */
    .father {
      perspective: 1000px;
      /* perspective: 10000px;
      perspective: 100px; */
    }

    .son {
      width: 200px;
      height: 200px;
      margin: 100px auto;
      background-color: pink;
      transition: all 0.5s;
    }

    .son:hover{
      transform: translateZ(-300px);
      transform: translateZ(300px);
    }
  </style>
</head>

<body>
  <div class="father">
    <div class="son"></div>
  </div>
</body>

</html>
```

**空间 – 旋转**

transform: rotateZ(值);
transform: rotateX(值);
transform: rotateY(值);

**Z轴旋转**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>空间旋转-Z轴</title>
    <style>
      .box {
        width: 300px;
        margin: 100px auto;
      }

      img {
        width: 300px;
        transition: all 2s;
      }

      .box img:hover {
        transform: rotateZ(360deg);
      }
    </style>
  </head>
  <body>
    <div class="box">
      <img src="./images/hero.jpeg" alt="" />
    </div>
  </body>
</html>
```

**X轴旋转**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>空间旋转-X轴</title>
    <style>
      .box {
        width: 300px;
        margin: 100px auto;
      }

      img {
        width: 300px;
        transition: all 2s;
      }

      .box {
        /* 透视效果：近大远小，近实远虚 */
        perspective: 1000px;
      }

      .box img:hover {
        transform: rotateX(60deg);
        transform: rotateX(-60deg);
      }
    </style>
  </head>
  <body>
    <div class="box">
      <img src="./images/hero.jpeg" alt="" />
    </div>
  </body>
</html>
```

**Y轴旋转**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>空间旋转-Y轴</title>
    <style>
      .box {
        width: 300px;
        margin: 100px auto;
      }

      img {
        width: 300px;
        transition: all 2s;
      }

      .box {
        /* 透视效果：近大远小，近实远虚 */
        perspective: 1000px;
      }

      .box img:hover {
        transform: rotateY(60deg);
        transform: rotateY(-60deg);
      }
    </style>
  </head>
  <body>
    <div class="box">
      <img src="./images/hero.jpeg" alt="" />
    </div>
  </body>
</html>
```

**空间 – 旋转**

