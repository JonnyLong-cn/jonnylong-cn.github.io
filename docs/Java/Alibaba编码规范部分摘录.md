# 一、编程规约

## 命名风格

- 类名：大驼峰式
  - 使用设计模式：将设计模式体现在名字中`public class OrderFactory;`
- 方法名、参数名、变量：小驼峰式
- 常量：全部大写
- 抽象类：Abstract或Base开头
- 测试类：Test结尾
- 包名：统一小写，用`.`分割层级，**单数**形式

+ 接口
  + 要有Javadoc注释
  + 方法：不加修饰符public，`void f();`
  + 接口常量：`String COMPANY = "alibaba";`

+ 枚举
  + 枚举类带上Enum
  + 枚举成员全部大写：`SUCCESS / UNKNOWN_REASON`

+ 接口和实现类有关系

  + 对于 Service 和 DAO 类，基于 SOA 的理念，暴露出来的服务一定是接口，内部

    的实现类用 Impl 的后缀与接口区别。`CacheServiceImpl`实现`CacheService`接口。

  + 如果是形容能力的接口名称，取对应的形容词做接口名（通常是–able 的形式）。`AbstractTranslator`实现`Translatable`。

+ Service/DAO 层方法命名规约

  + 获取单个对象的方法用 get 做前缀。
  + 获取多个对象的方法用 list 做前缀。
  + 获取统计值的方法用 count 做前缀。
  + 插入的方法用 save/insert 做前缀。
  + 删除的方法用 remove/delete 做前缀。
  + 修改的方法用 update 做前缀。

## 变量定义

1.不允许未经定义的常量直接出现在代码中

```java
//反例
String key = "Id#taobao"+tradeId;
```

2.long 或者 Long 初始赋值时，使用大写的 L，不能是小写的 l，小写容易跟数字 1 混淆，造成误解。

```java
//反例
Long a = 2l;
```

## 代码格式

> 大部分可以使用IDEA的自动对齐功能，以下是需要注意的

1.如果是大括号内为空，则简洁地写成{}即可，不需要换行

2.IDE 的 text file encoding 设置为 UTF-8; IDE 中文件的换行符使用 Unix 格式，不要使用 Windows 格式。

- 第二行相对第一行缩进 4 个空格，从第三行开始，不再继续缩进，参考示例。
- 运算符与下文一起换行。
- 方法调用的点符号与下文一起换行。
- 方法调用时，多个参数，需要换行时，在逗号后进行。 
- 在括号前不要换行，见反例。

```java
// 正例
StringBuffer sb = new StringBuffer(); 
// 超过 120 个字符的情况下，换行缩进 4 个空格，点号和方法名称一起换行
sb.append("zi").append("xin")... 
	.append("huang")... 
	.append("huang")... 
	.append("huang");
```

```java
// 反例
StringBuffer sb = new StringBuffer(); 
// 超过 120 个字符的情况下，不要在括号前换行
sb.append("zi").append("xin")...append 
	("huang"); 
// 参数很多的方法调用可能超过 120 个字符，不要在逗号前换行
method(args1, args2, args3, ... 
	, argsX);
```

## OOP规约

1.用类名来访问一个类的静态变量或静态方法

2.覆写方法，必须加@Override 注解

3.Object 的 equals 方法容易抛空指针异常，应使用常量或确定有值的对象来调用equals。

```java
// 正例：
"test".equals(object);
// 反例
object.equals("test");
```

4.所有的相同类型的包装类对象之间值的比较，全部使用 equals 方法比较。

5.关于基本数据类型与包装数据类型

+ 所有的 POJO 类属性必须使用包装数据类型
+ RPC 方法的返回值和参数必须使用包装数据类型。
+ 所有的局部变量使用基本数据类型。

6.**构造方法里面禁止加入任何业务逻辑**，如果有初始化逻辑，请放在 init 方法中。

7.定义 DO/DTO/VO 等 POJO 类时，不要设定任何属性默认值。