# web

## asd

### uri

* URI = Uniform Resource Identifier 统一资源标志符
* URL = Uniform Resource Locator 统一资源定位符
* URN = Uniform Resource Name 统一资源名称

## http

超文本传输协议（Hypertext Transfer Protocol，HTTP）是一个简单的请求-响应协议，它通常运行在TCP之上。它指定了客户端可能发送给服务器什么样的消息以及得到什么样的响应

### 请求报文

```http
GET /s?ie=utf-8&csq=1&pstg=20&mod=2&isbd=1&cqid=95c73d2400013f2f&istc=738&ver=02wgGwBXOO4aje7aoPDSmu9Z0L2rXSqPEIG&chk=64d716d1&isid=c59f24d60001e5d6&wd=rudy&rsv_spt=1&rsv_iqid=0xc2276d1b00014311&issp=1&f=8&rsv_bp=1&rsv_idx=2&ie=utf-8&rqlang=cn&tn=baiduhome_pg&rsv_dl=tb&rsv_enter=1&oq=rudy&rsv_btype=t&inputT=3&rsv_t=b5f7Sm7aKLp818iBSO5cb%2BLhVKbx%2BqvCRy9gF%2FQG2B8dPzsB8sd3sOjUr%2BXtNLHBP2Dv&rsv_pq=c59f24d60001e5d6&rsv_sug3=37&rsv_sug1=25&rsv_sug7=100&rsv_sug2=0&rsv_sug4=1258&rsv_sug=1&bs=rudy&f4s=1&_ck=1200.0.-1.-1.-1.-1.-1&rsv_isid=36553_39107_38831_39114_39039_38917_26350_39138_39100&isnop=0&rsv_stat=-1_-1_1_9.&rsv_bp=1 HTTP/1.1
Accept: */*
Accept-Encoding: gzip, deflate, br
Accept-Language: en,zh-CN;q=0.9,zh-TW;q=0.8,zh;q=0.7
Connection: keep-alive
Cookie: BIDUPSID=6B2F8743DAD88FCA60D63B2308130929; PSTM=1691333308; BD_UPN=123353; BDORZ=B490B5EBF6F3CD402E515D22BCDA1598; BDUSS=zc5MlZrV2FrOUNWUDduRTQ5eUVwTC10UDhQa2hCZXNVREtvVWtqcGlidy1OfmxrRVFBQUFBJCQAAAAAAAAAAAEAAACWts2ucXB6bTE1OTc1M8ur19MAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAD6q0WQ-qtFkY; BDUSS_BFESS=zc5MlZrV2FrOUNWUDduRTQ5eUVwTC10UDhQa2hCZXNVREtvVWtqcGlidy1OfmxrRVFBQUFBJCQAAAAAAAAAAAEAAACWts2ucXB6bTE1OTc1M8ur19MAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAD6q0WQ-qtFkY; BAIDUID=89D20717FEA210B34352D1E0F0D2FB67:FG=1; BA_HECTOR=aga5a02ha404ah0g0ka50g2e1ide4vp1p; BAIDUID_BFESS=89D20717FEA210B34352D1E0F0D2FB67:FG=1; ZFY=V7nfY2n5:B2:BZYwiFTYiWdHPBYH2blcYNKnmOtPi5U:A8:C; delPer=0; BD_CK_SAM=1; PSINO=1; ab_sr=1.0.1_NWJkYWJmNTZjMWRlY2Q5ZmFhNGEwZjExM2U0NWZkNjRlY2ZkYWVlZjdlZTQ3M2Y5MjlhNzM0YzhlMWI3ZWJhYjJhODg2MjI2MTAzM2FhOTEwNjdmMzViMzU4NjM2N2FiMTA0YWE4ZjU2YzFiYWY1Njg4MWM1Y2VkNGUzMWZhNjM2MzQxOTBkZWQ5MTRlYzU4OWNlZjE4ZjRlZmI5MjRlNA==; H_PS_PSSID=36553_39107_38831_39114_39039_38917_26350_39138_39137_39100; baikeVisitId=bfb3a288-4866-4ac7-90f2-ff719dd22da0; H_PS_645EC=528c0c0RPuJEsbIBHDr8dJ%2BolLfGYXcL1a331A8IRWdg7DrsudJlwrLyDG1eOLf2gQEp
Host: www.baidu.com
Ps-Dataurlconfigqid: 0xc2276d1b00014311
Referer: https://www.baidu.com/s?wd=rudy&rsv_spt=1&rsv_iqid=0xc2276d1b00014311&issp=1&f=8&rsv_bp=1&rsv_idx=2&ie=utf-8&rqlang=cn&tn=baiduhome_pg&rsv_dl=tb&rsv_enter=1&oq=rudy&rsv_btype=t&inputT=3&rsv_t=b5f7Sm7aKLp818iBSO5cb%2BLhVKbx%2BqvCRy9gF%2FQG2B8dPzsB8sd3sOjUr%2BXtNLHBP2Dv&rsv_pq=c59f24d60001e5d6&rsv_sug3=37&rsv_sug1=25&rsv_sug7=100&rsv_sug2=0&rsv_sug4=1258&rsv_sug=1
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/115.0.0.0 Safari/537.36
X-Requested-With: XMLHttpRequest
is_referer: https://www.baidu.com/s?wd=rudy&rsv_spt=1&rsv_iqid=0xc2276d1b00014311&issp=1&f=8&rsv_bp=1&rsv_idx=2&ie=utf-8&rqlang=cn&tn=baiduhome_pg&rsv_dl=tb&rsv_enter=1&oq=bash&rsv_btype=t&inputT=3156&rsv_t=7e26lEc0HOPJ4PHxZ%2FGPWbSDgseJr%2B2ZLVPTXqYGrWYSqmpcerKQVNDIH1rOzUc%2FNZi8&rsv_pq=92689e8f0000907f&rsv_sug3=36&rsv_sug1=24&rsv_sug7=100&rsv_sug2=0&rsv_sug4=3156
is_xhr: 1
sec-ch-ua: "Not/A)Brand";v="99", "Google Chrome";v="115", "Chromium";v="115"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Linux"
```

```http
HTTP/1.1 200 OK
Bdpagetype: 3
Bdqid: 0xfc80b9180000dc8b
Connection: keep-alive
Content-Encoding: br
Content-Security-Policy: frame-ancestors 'self' https://chat.baidu.com http://mirror-chat.baidu.com https://fj-chat.baidu.com https://hba-chat.baidu.com https://hbe-chat.baidu.com https://njjs-chat.baidu.com https://nj-chat.baidu.com https://hna-chat.baidu.com https://hnb-chat.baidu.com http://debug.baidu-int.com;
Content-Type: text/html
Date: Sat, 12 Aug 2023 05:21:21 GMT
Is_status: 1
Server: BWS/1.1
Set-Cookie: delPer=0; path=/; domain=.baidu.com
Set-Cookie: BD_CK_SAM=1;path=/
Set-Cookie: PSINO=1; domain=.baidu.com; path=/
Set-Cookie: BDSVRTM=365; path=/
Set-Cookie: H_PS_PSSID=36553_39107_38831_39114_39039_38917_26350_39138_39137_39100; path=/; domain=.baidu.com; Secure; SameSite=None
Strict-Transport-Security: max-age=172800
Traceid: 1691817681060108877818194746007307213963
Vary: Accept-Encoding
X-Ua-Compatible: IE=Edge,chrome=1
Content-Length: 57
<div>
    <div id="__status">0</div>
    <div id="__redirect">0</div>
    <div id="__switchtime">0</div>
</div>
```

## ajax

### xml

xml可拓展标记语言
被设计用来传输数据
用自定义标签表示数据

```xml
<?xml version="1.0" encoding="UTF-8"?>
<list>
    <emp id="1">
        <name>张三</name>
        <age>22</age>
    </emp>
    <emp id="2">
        <name>李四</name>
        <age>46</age>
    </emp>
</list>
```

已经被json取代了

### ajax 优缺点

* 优点
  * 无需刷新页面就可以和服务器端进行通信
  * 允许根据用户事件来跟新页面内容
* 缺点
  * 没有浏览历史不能回退
  * 存在跨域问题
  * SEO不友好

## spring

* Spring框架概述
  spring是一个开源的轻量级Java开发应用框架，可以简化企业级应用开发。Spring解决了开发者在JavaEE开发中遇到的许多常见的问题，提供了功能强大IOC、AOP及Web MVC等功能。是当前企业中Java开发几乎不能缺少的框架之一。Spring的生态及其完善，不管是Spring哪个领域的解决方案都是依附于在SpringFramework基础框架的

### IoC(Inversion of Control)

控制反转，强调的是在原来在程序中创建Bean的权利反转给第三方

### DI(Dependency Injection)

依赖注入，强调的Bean之间的关系，这种关系有第三方负责去设置

### AOP(Aspect Oriented Programming)

面相切面编程，功能的横向抽取，主要实现的方式就是Proxy

## java

### 面向对象

**Java中的Interface与Impl**
在Java编程中，Interface和Impl（即Implementation）是两个重要的概念。Interface是一种定义了一组方法签名的类，这些方法在其衍生类中实现。而Impl则是继承自Interface的类，实现了Interface中所定义的方法。在软件开发过程中，Interface与Impl的使用可以帮助我们更好地实现代码的抽象与复用

**Interface的定义**
Interface（接口）是Java中一种特殊的类，只定义了一系列方法的签名，而没有实际的实现。可以将Interface看作是一份契约，用来规定实现这个接口的类需要实现什么样的方法。例如：

```java
public interface Animal {
public void eat();
public void sleep();
}
```

这里定义了一个名为Animal的Interface，其中包含了两个未实现的方法eat()和sleep()。这样，任何实现了Animal的类都必须提供这两个方法的实现。

**Impl的定义**
Impl（实现）是继承自Interface的类，它实现了Interface中所定义的方法。例如，我们可以定义一个实现Animal接口的Cat类：

```java
public class Cat implements Animal {
public void eat() {
    .out.println("Cat eats fish");
}
public void sleep() {
    System.out.println("Cat sleeps 8 hours a day");
}
}
```
