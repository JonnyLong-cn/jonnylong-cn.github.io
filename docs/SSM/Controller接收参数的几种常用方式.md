# 请求路径参数

## @PathVariable

获取路径参数。即`url/{id}`这种形式。

## @RequestParam

获取查询参数。即`url?name=*`这种形式

```java
@GetMapping("/demo/{id}")
public void demo(@PathVariable(name = "id") String id, @RequestParam(name = "name") String name) {
    System.out.println("id="+id);
    System.out.println("name="+name);
}
```

访问：`http://localhost:8080/demo/123?name=suki_rong`

得到结果：

```
id=123
name=suki_rong
```

# Body参数

## @RequestBody

方式一：使用对象

```java
@PostMapping(path = "/demo1")
public void demo1(@RequestBody Person person) {
    System.out.println(person.toString());
}
```

输出结果：

```
name:suki_rong;age=18;hobby:programing
```

方式二：使用Map键值对

```java
@PostMapping(path = "/demo1")
public void demo1(@RequestBody Map<String, String> person) {
    System.out.println(person.get("name"));
}
```

输出结果：

```
suki_rong
```

!> @RequestBody可以设置相关参数

可以设置：

+ 是否可以为空
+ 默认信息

```java
public String requestParam(@RequestParam(value = "name") String name,
                           @RequestParam(value = "age") String age,
                           @RequestParam(value = "extra",required = false,defaultValue = "没有额外信息吖") String extra){
}
```

## 无注解

```java
/*
* 无注解
* GET请求时直接读取url中的参数
* POST请求时接收application/x-www-form-urlencoded和multipart/form-data
* form表单提交默认使用application/x-www-form-urlencoded
* 处理长字节文件时应使用multipart/form-data
* 获取参数的时候可以自动装入对象也可以单个接收
* */
@PostMapping(path = "/demo2")
public void demo2(Person person) {
    System.out.println(person.toString());
}
```

得到结果：

```
name:suki_rong;age=18;hobby:programing
```

# 请求头参数以及Cookie

## @RequestHeader和@CookieValue

```java
@GetMapping("/demo3")
public void demo3(@RequestHeader(name = "myHeader") String myHeader,
        @CookieValue(name = "myCookie") String myCookie) {
    System.out.println("myHeader=" + myHeader);
    System.out.println("myCookie=" + myCookie);
}
```

也可以这样：

```java
@GetMapping("/demo3")
public void demo3(HttpServletRequest request) {
    System.out.println(request.getHeader("myHeader"));
    for (Cookie cookie : request.getCookies()) {
        if ("myCookie".equals(cookie.getName())) {
            System.out.println(cookie.getValue());
        }
    }
}
```

> `HttpServletRequest`对象代表客户端的请求，当客户端通过HTTP协议访问服务器时，HTTP请求头中的所有信息都封装在这个对象中，通过这个对象提供的方法，可以获得客户端请求的所有信息。

| 方法            | 作用                            |
| --------------- | ------------------------------- |
| `getRequestURL()` | 返回客户端发出请求时的完整URL。 |
| `getRequestURI()` | 返回请求行中的参数部分。        |
|`getQueryString ()` | 方法返回请求行中的参数部分（参数名+值）|
|`getRemoteHost()` | 返回发出请求的客户机的完整主机名。|
|`getRemoteAddr()` | 返回发出请求的客户机的IP地址。|
|`getPathInfo()` | 返回请求URL中的额外路径信息。额外路径信息是请求URL中的位于Servlet的路径之后和查询参数之前的内容，它以"/"开头。|
|`getRemotePort()` | 返回客户机所使用的网络端口号。|
|`getLocalAddr()` | 返回WEB服务器的IP地址。|
|`getLocalName()` | 返回WEB服务器的主机名。|