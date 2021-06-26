# 1. 开篇：这一次，让我们从小白开始

### 小伙伴的迷茫

> 我刚学完 JavaWeb 基础，接下来要学什么框架啊，感觉一头雾水。。。
>
> 我都学完 Spring 了，可感觉也只会用，稍微碰到一点问题就不会处理了。。。
>
> 看了大佬的 **《SpringBoot 源码解读与原理分析》** 小册，感觉自己根本就不会 SpringFramework ，想重新学一遍。。。

这几种言论，是我自出品《SpringBoot 源码解读与原理分析》小册之后，收到的最多的几种呼声（这种呼声在 SpringCloud 小册发布之后更多了）。确实如此，很多小伙伴都说看了原理小册，发现自己原来好多东西都没学 / 没怎么接触（诸如 SpringFramework 事件机制、后置处理器、`BeanDefinition` 等），那就更别谈深入原理了。

### SpringFramework到底有多重要

另外，还有更多的小伙伴，属于刚刚学完 JavaSE ，或者 JavaWeb 的基础知识，刚学会使用 Servlet 来开发简单的小 Web 应用。学完了基础，自然要开始接触框架了，可是框架那么多，从哪个先开始学呢？以小册编写的时间节点来看，2020年的风向，对于第一个框架的学习，大多数以推荐 MyBatis 为主，当然也有部分推荐先学习 SpringFramework 。以作者的观点，作为入门的框架，你更应该先学习 SpringFramework ，原因大致如下：

- **几乎当下所有**的企业级 JavaEE 开发**都离不开** SpringFramework ；
- SpringFramework **不局限于某一个部分** / 模块的技术，对于表现层、业务层、持久层等都有提供解决方案；
- SpringFramework 最最强大的地方在于**与其他技术的整合**，别人一开始推荐学习的 MyBatis 属于持久层解决方案，SpringFramework 能跟 MyBatis 很好地整合在一起，最终你还是得用 SpringFramework ，那为什么不先学这个中心呢？
- SpringFramework 是后续 SpringBoot 、乃至微服务 SpringCloud 的最最基础，**早早地打下基础，可以更好地为以后更高阶的技术学习铺路**；
- SpringFramework 被很多面试官拿来作为**经典面试考题**，且**难度有逐年上升的趋势**。。。

事实上，无论是国内还是国外，SpringFramework 的热度和走势一直都是特别健康的，我们可以这么说，SpringFramework 已然成为了 Java 开发的标杆、灯塔级别的“**标准**”，熟练掌握 SpringFramework ，甚至精通它，对于进军大厂，获取高薪来说是相当的有必要。

### 小册涉及的广度与深度

正如小册的名称一样，小册会带你从 SpringFramework 的小白一步一步走向大佬，自然深度不用多废话。关于广度的部分，作者收集了目前市面上和各大论坛等网站关于 SpringFramework 基础的热点，大体分为如下几个部分：IOC 、AOP 、JDBC 与事务、SpringWebMvc 和一些其他功能。其中对于 IOC 部分，展开的内容会相当多，包括容器、事件、高级特性和概念等等。

小伙伴们可以通过本小册，学习到 SpringFramework 中尽可能多而全的知识，获得知识面的广度；同时对于重点知识又能了解到它的原理，获得知识层的深度。希望能通过小册对 SpringFramework 的知识讲解，帮助小伙伴们一步一步，从小白成长为大佬，走向人生巅峰，迎娶白富美（划掉...）。

### 从小白开始吧

可能有些小伙伴对 SpringFramework 有一定的了解或者使用经验，也或者小伙伴真的就是 SpringFramework 的小白，接下来小册希望小伙伴能忘掉之前对 SpringFramework 的认识和使用经历，投入到小册中来学习吧！

# 2. 开始前的约定：关于本小册的一些前置说明

跟往常一样，咱还是有些话放在前面，小伙伴们一定要仔细阅读哦！

### 关于本小册的内容

- 小册会带你从完全不了解 SpringFramework 、完全不会使用 SpringFramework 开始，一步一步来学习，所以小伙伴不需要担心。不过，也不是什么都不会就可以学的，**最起码的 JavaSE 知识、JavaWeb 知识你得会**，**对于 Servlet 、三层架构的设计相关知识你得知道**。如果小伙伴对于这些前置知识还不太了解，小册建议你先去补足基础。
- 小册会从你熟悉的 Servlet 和三层架构开始，逐渐引导你进入 SpringFramework 的学习，所以需要小伙伴跟紧小册的思路。当然对于已经比较熟悉 SpringFramework 的小伙伴，小册同样可以**作为一本类似于“工具书”的角色**帮助你掌握某一些特定的知识。所以**无论小伙伴是初学、还是进阶，小册都非常适合你**。
- 小册目前基于 **SpringFramework 5.2.x**，当然后续的编写期间也有可能伴随 SpringFramework 5.3 的发布，**具体版本以最终小册发行时间为准**（根据官方的说法，SpringFramework 5.3 对性能有不错的提升，所以还蛮值得期待的）。
- 小册中对一些可能出现混淆意义的概念作了更清晰的概念处理（如普遍意义上开发中称呼的 Spring 一般都是 **SpringFramework** ，故本小册中提到的所有 Spring 基础框架统称 SpringFramework）。
- 小册在进阶和高级等部分的讲解中可能会引用 SpringFramework 中源码的 javadoc ，对于这些出现的文档注释，小册统一使用**原文 + 翻译**的方式，这样做的目的是**保留原作者想表达的原汁原味的东西**，而不是直接贴上我的翻译，**人的翻译总是会带入一些个人的主观色彩，会影响原文内容的理解**。小伙伴们在看文档注释的时候可以结合原文和小册的翻译注释来看，可以更助于理解。

### 关于本小册的作者

- 作者不是什么专业大佬，大厂P8P9之类的，也没什么高端的职称，只是喜欢深扒原理，了解底层的东西（已读过很多框架的源码，包括出版 SpringBoot 、SpringCloud 源码分析）。所以喜欢作者头衔是什么什么架构师，什么大厂高级工程师，几十年工作经验的童鞋们请三思￣へ￣。
- 在作者看来，学习一门技术，想要从入门到熟悉，再到进阶、掌握，最终冲刺高级和原理，这是一个循序渐进的过程，这个过程最好跟着一个既定的主线走，可以减少一些不必要的额外的成本。作者也在不断思考和改进小册的设计，如何做到能更容易的学习新的技术，或者加强已经学过的技术。有主意的小伙伴可以多多帮作者支招啊，不胜感激。

### 关于阅读小册的几点建议

- 小册都是用 Markdown 语法编写，**PC、平板电脑的阅读效果会更好一些**。小册中对于代码编写、框架源码的粘贴部分可能很大很宽，如果用手机阅读需要频繁左右滑动，暂且先不说阅读内容和收获，首先从时间上你就多余的浪费了不少，而且不容易连贯的阅读。
- 如果小伙伴是刚开始学 SpringFramework 的话，强烈建议从头开始按顺序往下看，因为**进阶和高级的部分通常会依赖基础部分的讲解**，所以，不要 “没学会走就想着跑，甚至飞” 。
- 小册里讲解的知识，以及高级和原理部分的剖析，我都会尽可能写的明白，但写得明白终究是我觉得明白，以及部分人的明白。如果小伙伴在阅读小册时发现有困惑或者疑问，最好是去群里问问题嗷，只要是我能帮的我都尽可能的帮。

### 关于IDE、环境和源码

- 不得不说，**IDEA** 的强大真的比 eclipse 高出太多了，它不仅仅是强大，更是**智慧、聪明的 IDE** 。一个聪明的 IDE ，可以帮助小伙伴在学习时减少一些不必要的错误，所以作者在这里**强烈建议小伙伴使用 IDEA 学习 SpringFramework** 。
- 对于环境和工程的搭建，我不打算在整个学习过程中使用任何普通的工程构建，而是**全部基于 Maven 构建**。作为一个**项目构建和管理工具**，它可以帮助开发者维护项目中使用的依赖，省去很多之前构建普通工程时导 jar 包不全，以及版本不匹配的问题。当然如果小伙伴使用 **Gradle** 构建项目也是完全可以的，二者选其一即可。
- 所以，如果小伙伴使用如下的开发环境，那么你可以非常愉快的跟着小册来学习 SpringFramework 啦：
  - jdk 1.8 + ( Maven 3.3.9 / Gradle 4.0 ) 或更高版本
  - IDEA（作者目前使用的是 2019.1 ）
- 本小册中讲解的所有示例源码均可从 GitHub 上找到：[github.com/LinkedBear/…](https://github.com/LinkedBear/spring-framework-learning-code)

### 补充几句

- 作者是人，不是神仙，不能完全 100% 保证小册中没有问题。如果小伙伴们发现了小册中出现错误和准确性问题，请通过群及时联系我，我会及时尽快的修改订正的。
- 小伙伴们可以多多在小册评论区留言，或者加群咱们一起讨论！

# 3. 入门-IOC是怎么来的

好了咱开始进入正题了，在开始学习 SpringFramework 之前，咱先看一个场景。

【小伙伴最好设身处地的代入本章的场景中，这样更有利于体会 IOC 的由来，也更容易理解】

## 1. 原生Servlet时代的三层架构

下面咱实际动手搭建一个在原生 Servlet 时代的 MVC 三层架构的工程，以此为背景板。

（为方便后续内容演示，使用 IDEA 创建工程前，先创建一个空工程 `spring-framework-projects` ，用来存放接下来的所有工程）

### 1.1 构建基于Maven的原生Servlet工程

使用 Maven 构建项目那是最基本的能力了，咱使用 IDEA 快速搭建一个原生的 Servlet 工程。

pom 依赖中，只需要引入 Servlet 的 api 即可：（此处我使用了 Servlet3.1 ，这个倒是无所谓，只是用 **Servlet3.0+** 的版本可以基于注解开发，效率较快）

```xml
<dependencies>
    <dependency>
        <groupId>javax.servlet</groupId>
        <artifactId>javax.servlet-api</artifactId>
        <version>3.1.0</version>
        <scope>provided</scope>
    </dependency>
</dependencies>
```

当然，为了使工程的编译级别在 1.8 级别，还需要加入 Maven 的编译插件：（版本不要太老就好，此处我选用 3.2 版本）

```xml
<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>3.2</version>
            <configuration>
                <source>1.8</source>
                <target>1.8</target>
                <encoding>UTF-8</encoding>
            </configuration>
        </plugin>
    </plugins>
</build>
```

最后，不要忘记调整打包方式为 war 包：

```xml
<packaging>war</packaging>
```

### 1.2 将工程部署到Servlet容器

创建好工程后，下一步先不要着急写代码，咱先把工程部署到 Servlet 容器中，保证能正常运行。这里咱使用 Tomcat 作为 Servlet 容器来运行工程。

在 IDEA 中依次打开 **“File -> Project Structure”** ，选中 **Artifacts** 标签，并添加 **Web Application: Exploded** 类型的输出类型，配置好对应的路径与名称，即可设置好编译打包输出配置。如下图所示：

![](《从0开始深入学习Spring》/d95d13e9fe1d48cd98c4dd9e5602e037~tplv-k3u1fbpfcp-zoom-1.image)

接下来，在 IDEA 的运行栏中选择 **Add Configuration...** ，并添加本地的 Tomcat ：

![](《从0开始深入学习Spring》/31aa147ff1cb4f56be12b111861c7306~tplv-k3u1fbpfcp-zoom-1.image)

接下来在新建的 Tomcat 中选择 **Deployment** ，并添加刚配置好的 **Artifact** ：

![](《从0开始深入学习Spring》/14ac30da10b84813be0abbadbe6f83b4~tplv-k3u1fbpfcp-zoom-1.image)

添加完成后，即可保存确定。

### 1.3 编写Servlet测试可用

在 `src/main/java` 中新建一个 `DemoServlet` ，标注 `@WebServlet` 注解，并继承 `HttpServlet` ，重写 `doGet` 方法：

```java
@WebServlet(urlPatterns = "/demo1")
public class DemoServlet1 extends HttpServlet {
    
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        response.getWriter().println("DemoServlet1 run ......");
    }
    
}
```

编写完毕后直接启动 Tomcat ，此时 IDEA 会自动编译工程并部署到 Tomcat 中。

打开浏览器，地址栏输入 http://localhost:8080/spring_00_introduction_architecture/demo1 （每个人搭建的工程名可能不一致，context-path 记得修改），发现可以正常打印 `DemoServlet1 run ......` 的输出，证明工程搭建并配置成功。

### 1.4 编写Service与Dao

因为一开始 pom 中没有导入与数据库相关的依赖，故此处的 Dao 只是空壳，并没有实际的 jdbc 相关操作。

在工程目录下新建以下几个类和接口，这些都是老生常谈了，都很简单：

![img](《从0开始深入学习Spring》/9e316ba2558a4c36ae32d473cf4e63df~tplv-k3u1fbpfcp-zoom-1.image)

对应的三层架构中的组件及依赖就应该是这样：（ Dao 连接数据库的部分不实现）

![img](《从0开始深入学习Spring》/bd19682e7682438fb4ddd1460342ac23~tplv-k3u1fbpfcp-zoom-1.image)

#### 1.4.1 Dao与DaoImpl

简单定义一个 `DemoDao` 接口，并声明一个 `findAll` 方法模拟从数据库查询一组数据：

```java
public interface DemoDao {
    List<String> findAll();
}
```

编写它对应的实现类 `DemoDaoImpl` ，由于没有引入数据库的相关驱动，故这里只是用写死的临时数据模拟 Dao 与数据库的交互：

```java
public class DemoDaoImpl implements DemoDao {
    
    @Override
    public List<String> findAll() {
        // 此处应该是访问数据库的操作，用临时数据代替
        return Arrays.asList("aaa", "bbb", "ccc");
    }
}
```

至此，Dao 层的接口与实现类定义完成。

#### 1.4.2 Service与ServiceImpl

编写一个 `DemoService` 接口，并声明 `findAll` 方法：

```java
public interface DemoService {
    List<String> findAll();
}
```

编写它对应的实现类 `DemoServiceImpl` ，并在内部依赖 `DemoDao` 接口：

```java
public class DemoServiceImpl implements DemoService {
    
    private DemoDao demoDao = new DemoDaoImpl();
    
    @Override
    public List<String> findAll() {
        return demoDao.findAll();
    }
}
```

至此，Service 层的接口与实现类定义完成。

### 1.5 修改DemoServlet

由于要模拟整体的三层架构，故 `DemoServlet1` 要依赖 `DemoService` ：

```java
@WebServlet(urlPatterns = "/demo1")
public class DemoServlet1 extends HttpServlet {
    
    DemoService demoService = new DemoServiceImpl();
    
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        resp.getWriter().println(demoService.findAll().toString());
    }
}
```

### 1.6 重新运行应用并测试可用

重新部署到 Tomcat 并运行，访问 `/demo1` 路径，浏览器中会打印 `['aaa', 'bbb', 'ccc']` ，说明编写正确且运行正常。

------

以上部分是咱在 JavaWeb 基础中最熟悉不过的东西了，好了到这里咱停下来，代入一个场景。

## 2. 【问题】需求变更

现在你的手头上已经基本上开发完成了，数据库用的 MySQL 很舒服，临近交付项目，客户一个电话打过来了：

> 哎呦我去这瞧谁不起啊？我可是大老板，给老子换 Oracle 的数据库！

挂掉电话的你内心一万只草泥马呼啸而去：

没招啊，客户是上帝啊，咱也是要恰饭的嘛，客户要啥咱就得改啥啊！那改吧：

### 2.1 修改数据库

咱都知道，对于 MySQL 跟 Oracle ，在有一些**特定的 SQL 上是不一样的**（比如分页），这样我还不能只把数据库连接池的相关配置改了就好使，每个 DaoImpl 也得改啊！于是乎，你开始修改起工程里所有的 DaoImpl ：

```java
public class DemoDaoImpl implements DemoDao {
    
    @Override
    public List<String> findAll() {
        // 模拟修改SQL的动作
        return Arrays.asList("oracle", "oracle", "oracle");
    }
}
```

### 2.2 需求再次变更

你好不容易熬夜两个晚上，头发掉了一把又一把，终于要给客户部署工程了，客户笑眯眯的跟你说了一句话：

> 那个啥，最近炒股。。。呃不是，财务支出有点严重，这不有点囊中羞涩，数据库就换回 MySQL 吧！

此时的你一定是：

![](《从0开始深入学习Spring》/6c2134037635436493b6ad12aa4043d6~tplv-k3u1fbpfcp-zoom-1.image)

你已经受够了这种改过来改过去的破事了，毕竟狗命要紧（杀死程序猿最简单的办法：改三次需求），那这个时候你就得想啊，怎么解决这个问题呢？

### 2.3 【方案】引入静态工厂

苦思良久，你终于想到了一个好办法：如果我**事先把这些 Dao 都写好**了，之后**用一个静态工厂来创建特定类型的实现类**，这样万一发生需求变更，是不是就可以做到只改一次代码就可以了！

于是按照这个想法，有如下改造：

#### 2.3.1 构造静态工厂

声明一个静态工厂，起个比较别致的名字吧：`BeanFactory` （不要问我为什么这么别致，这是一个伏笔）

```java
public class BeanFactory {
    public static DemoDao getDemoDao() {
        // return new DemoDaoImpl();
        return new DemoOracleDao();
    }
}
```

#### 2.3.2 改造ServiceImpl

ServiceImpl 中引用的 Dao 不再是手动 new ，而是由 `BeanFactory` 的静态方法返回而得：

```java
public class DemoServiceImpl implements DemoService {
    
    DemoDao demoDao = BeanFactory.getDemoDao();
    
    @Override
    public List<String> findAll() {
        return demoDao.findAll();
    }
}
```

如此这般，即便 ServiceImpl 再多，Dao 再多，**发生需求更改**，我也**只需要改动 BeanFactory 中的静态方法返回值即可**！

问题解决，皆大欢喜，客户也很满意，项目交付完成。

## 3. 【问题】源码丢失

项目上线运行一段时间后，客户对系统中的一些功能提出了优化和扩展需求，那这个时候你就来维护呗，毕竟你最熟悉这个项目。不过之前好一段时间你都去负责别的项目去了，维护工作都是由你同事负责着。

当你重新打开工程时，想先拉起来看看要扩展的需求具体的位置，居然发现项目连编译都无法通过了！（为演示无法编译的现象，删除 `DemoDaoImpl.java` ）

此时的你肯定是一脸黑人问号啊！怎么之前好使的现在就不好使了？再仔细一看报错位置，`BeanFactory` ！哎不大对劲啊，我这之前封装好的静态工厂就是偷懒用的，怎么会编译出错呢？打开代码看了一眼才知道，合着少了一个 `DemoDaoImpl` 的源文件，导致代码根本无法编译了！

场景演绎到这里，咱先稍微暂停一下，体会一下这里面出现的问题。

### 3.1 【概念】类之间的依赖关系——紧耦合

```java
public class BeanFactory {
    public static DemoDao getDemoDao() {
        return new DemoDaoImpl(); // DemoDaoImpl.java不存在导致编译失败
    }
}
```

当前的代码中，因为源码中真的缺少这个 `DemoDaoImpl` 类，导致编译都无法通过，这种现象就可以描述为 **“ `BeanFactory` 强依赖于 `DemoDaoImpl` ”** ，也就是咱可能听过也可能常说的“**紧耦合**”。

### 3.2 【方案】解决紧耦合

回到刚才的场景中，你这直接懵逼了呀，没有这个 .java 文件，我没法编译，那我不用干活了呗？不行，咱可不能因为这个问题就耽误了整体呀！于是乎你开动脑筋，想一下在现有知识中，有没有一种办法能解决这个编译都没办法编译的问题？

**反射！反射可以声明一个类的全限定名，来获取它的字节码描述，这样也能构造对象！**

于是 `BeanFactory` 可以改造为：

```java
public class BeanFactory {
    
    public static DemoDao getDemoDao() {
        try {
            return (DemoDao) Class.forName("com.linkedbear.architecture.c_reflect.dao.impl.DemoDaoImpl").newInstance();
        } catch (Exception e) {
            e.printStackTrace();
            throw new RuntimeException("DemoDao instantiation error, cause: " + e.getMessage());
        }
    }
}
```

照这样一写，是不是编译的问题就解决了？尽管在 `DemoService` 的初始化时还是会出现问题，但最起码可以把项目拉起来了啊！

于是这个问题就暂时解决了，先放一边了。。。

### 3.3 【概念对比】弱依赖

使用反射之后，错误现象不再是在编译器就出现，而是在工程启动后，由于 `BeanFactory` 要构造 `DemoDaoImpl` 时确实还没有该类，所以抛出 `ClassNotFoundException` 异常。这样 **`BeanFactory` 对 `DemoDaoImpl` 的依赖程度**就相当于**降低**了，也就可以算作“**弱依赖**”了。

## 4. 【问题】硬编码

躲得了初一躲不了十五，这个问题最终还是得解决，你费劲八道的终于把 `DemoDaoImpl.java` 找了回来，这下终于运行期也不报错了。但这样在切换 MySQL 和 Oracle 库时还是会出现一个问题：由于类的全限定名是写死在 `BeanFactory` 的源码中，导致每次切换数据库后还得重新编译工程才可以正常运行，这显得貌似很没必要，应该有更好的处理方案。

### 4.1 【改良】引入外部化配置文件

机智的你利用现有的 JavaSE 知识，立马能想到：哎，我可以**借助 IO 来实现文件存储配置**啊！这样**每次 `BeanFactory` 被初始化时，让它去读配置文件，这样就不会出现硬编码的现象了**！

于是可有如下改造：

#### 4.1.1 加入factory.properties文件

在 `src/main/resource` 目录下新建 `factory.properties` 文件，并在其中声明如下内容：

```properties
demoService=com.linkedbear.architecture.d_properties.service.impl.DemoServiceImpl
demoDao=com.linkedbear.architecture.d_properties.dao.impl.DemoDaoImpl
```

为了方便回头取这些类的全限定名，我**给每一个类名都起一个“小名”**（别名），这样我就可以**根据小名来找到对应的全限定类名**了。

#### 4.1.2 改造BeanFactory

既然配置文件是 properties 类型，在 jdk 中刚好也有一个 API 叫 `Properties` ，它可以解析 `.properties` 文件。

于是可以在 `BeanFactory` 中加入一个静态变量：

```java
public class BeanFactory {
    
    private static Properties properties;
```

下面要在工程刚启动的时候就初始化 `Properties` ，这咱可以使用静态代码块实现吧：

```java
    private static Properties properties;
    
    // 使用静态代码块初始化properties，加载factord.properties文件
    static {
        properties = new Properties();
        try {
            // 必须使用类加载器读取resource文件夹下的配置文件
            properties.load(BeanFactory.class.getClassLoader().getResourceAsStream("factory.properties"));
        } catch (IOException e) {
            // BeanFactory类的静态初始化都失败了，那后续也没有必要继续执行了
            throw new ExceptionInInitializerError("BeanFactory initialize error, cause: " + e.getMessage());
        }
    }
```

配置文件读取到之后，下面的 `getDao` 方法也可以进一步改了：

```java
    public static DemoDao getDemoDao() {
        try {
            Class<?> beanClazz = Class.forName(properties.getProperty("demoDao"));
            return beanClazz.newInstance();
        } catch (ClassNotFoundException e) {
            throw new RuntimeException("BeanFactory have not [" + beanName + "] bean!", e);
        } catch (IllegalAccessException | InstantiationException e) {
            throw new RuntimeException("[" + beanName + "] instantiation error!", e);
        }
    }
```

写到这里，是不是感觉怪怪的。。。都抽象化到这种地步了，还有必要在这里面写死 “demoDao” 吗？肯定没必要了吧，干脆做一个通用得了，你传什么别名，`BeanFactory` 就从配置文件中找对应的全限定类名，反射构造对象返回：

```java
    public static Object getBean(String beanName) {
        try {
            // 从properties文件中读取指定name对应类的全限定名，并反射实例化
            Class<?> beanClazz = Class.forName(properties.getProperty(beanName));
            return beanClazz.newInstance();
        } catch (ClassNotFoundException e) {
            throw new RuntimeException("BeanFactory have not [" + beanName + "] bean!", e);
        } catch (IllegalAccessException | InstantiationException e) {
            throw new RuntimeException("[" + beanName + "] instantiation error!", e);
        }
    }
```

#### 4.1.3 改造ServiceImpl

`DemoServiceImpl` 中不再需要调 `getDao` 方法了（因为被删了...），而是转用 `getBean` 方法，并指定需要获取的指定名称的类的对象：

```java
public class DemoServiceImpl implements DemoService {
    
    DemoDao demoDao = (DemoDao) BeanFactory.getBean("demoDao");
```

到这里，你突然发现一个现象：这下你可以把**所有**想抽取出来的**组件都可以做成外部化配置**了！

### 4.2 【思想】外部化配置

对于这种可能会变化的配置、属性等，通常不会直接硬编码在源代码中，而是抽取为一些配置文件的形式（ properties 、xml 、json 、yml 等），配合程序对配置文件的加载和解析，从而达到动态配置、降低配置耦合的目的。

## 5. 【问题】多重构建

改到这里可能你会感觉，是不是哪里不对劲，是不是还有改进的空间呢？这样，咱在 `ServiceImpl` 的构造方法中连续多次获取 `DemoDaoImpl` ：

```java
public class DemoServiceImpl implements DemoService {
    
    DemoDao demoDao = (DemoDao) BeanFactory.getBean("demoDao");
    
    public DemoServiceImpl() {
        for (int i = 0; i < 10; i++) {
            System.out.println(BeanFactory.getBean("demoDao"));
        }
    }
```

咱只来看打印的这些 `DemoDao` 的内存地址：

```
com.linkedbear.architecture.d_properties.dao.impl.DemoDaoImpl@44548059
com.linkedbear.architecture.d_properties.dao.impl.DemoDaoImpl@5cab632f
com.linkedbear.architecture.d_properties.dao.impl.DemoDaoImpl@24943e59
com.linkedbear.architecture.d_properties.dao.impl.DemoDaoImpl@3f66e016
com.linkedbear.architecture.d_properties.dao.impl.DemoDaoImpl@5f50e9eb
com.linkedbear.architecture.d_properties.dao.impl.DemoDaoImpl@58e55b35
com.linkedbear.architecture.d_properties.dao.impl.DemoDaoImpl@5d06d086
com.linkedbear.architecture.d_properties.dao.impl.DemoDaoImpl@55e8ed60
com.linkedbear.architecture.d_properties.dao.impl.DemoDaoImpl@daf5987
com.linkedbear.architecture.d_properties.dao.impl.DemoDaoImpl@7f6187f4
```

可以发现每次打印的内存地址都不相同，证明是创建了10个不同的 `DemoDaoImpl` ！但是，真的有必要吗。。。

### 5.1 【改良】引入缓存

如果对于这些没必要创建多个对象的组件，如果能有一种机制保证整个工程运行过程中只存在一个对象，那就可以大大减少资源消耗。于是可以在 `BeanFactory` 中加入一个缓存区：

```java
public class BeanFactory {
    // 缓存区，保存已经创建好的对象
    private static Map<String, Object> beanMap = new HashMap<>();
    
    // ......
```

之后在 `getBean` 方法中，为了控制线程并发，需要引入双检锁保证对象只有一个：

```java
public static Object getBean(String beanName) {
    // 双检锁保证beanMap中确实没有beanName对应的对象
    if (!beanMap.containsKey(beanName)) {
        synchronized (BeanFactory.class) {
            if (!beanMap.containsKey(beanName)) {
                // 过了双检锁，证明确实没有，可以执行反射创建
                try {
                    Class<?> beanClazz = Class.forName(properties.getProperty(beanName));
                    Object bean = beanClazz.newInstance();
                    // 反射创建后放入缓存再返回
                    beanMap.put(beanName, bean);
                } catch (ClassNotFoundException e) {
                    throw new RuntimeException("BeanFactory have not [" + beanName + "] bean!", e);
                } catch (IllegalAccessException | InstantiationException e) {
                    throw new RuntimeException("[" + beanName + "] instantiation error!", e);
                }
            }
        }
    }
    return beanMap.get(beanName);
}
```

改良完成，重新测试，观察这一次打印的结果：

```
com.linkedbear.architecture.e_cachedfactory.dao.impl.DemoDaoImpl@4a667700
com.linkedbear.architecture.e_cachedfactory.dao.impl.DemoDaoImpl@4a667700
com.linkedbear.architecture.e_cachedfactory.dao.impl.DemoDaoImpl@4a667700
......
```

果然只会有一个对象了，最终目的达到。

------

到这里，整个场景的演绎就算结束了，下面咱来总结一下这里面出现的几个关键点。

- 静态工厂可将多处依赖抽取分离
- 外部化配置文件+反射可解决配置的硬编码问题
- 缓存可控制对象实例数

接下来，是时候引出这一章的主题了。

## 6. IOC的思想引入【重点】

对比上面的两种代码写法：

```java
private DemoDao dao = new DemoDaoImpl();

private DemoDao dao = (DemoDao) BeanFactory.getBean("demoDao");
```

上面的是强依赖 / 紧耦合，在编译期就必须保证 `DemoDaoImpl` 存在；下面的是弱依赖 / 松散耦合，只有到运行期反射创建时才知道 `DemoDaoImpl` 是否存在。

再对比看，上面的写法是主动声明了 `DemoDao` 的实现类，只要编译通过，运行一定没错；而下面的写法没有指定实现类，而是由 `BeanFactory` 去帮咱查找一个 name 为 `demoDao` 的对象，倘若 `factory.properties` 中声明的全限定类名出现错误，则会出现强转失败的异常 `ClassCastException` 。

仔细体会下面这种对象获取的方式，本来咱开发者可以使用上面的方式，主动声明实现类，但如果选择下面的方式，那就不再是咱自己去声明，而是**将获取对象的方式交给了 `BeanFactory`** 。这种**将控制权交给别人**的思想，就可以称作：**控制反转（ Inverse of Control , IOC ）**。而 `BeanFactory` 根据指定的 `beanName` 去获取和创建对象的过程，就可以称作：**依赖查找（ Dependency Lookup , DL ）**。

## 小结与思考

【每一章的最后，我会留下一些小问题和小练习，帮助小伙伴回顾本章的内容，加深印象】

1. 需求变更引起的工程代码变动成本是巨大的，有什么办法可以减少变动成本呢？
2. 如何理解控制反转？

【终于了解什么是 IOC ，以及它的实现方式之一：**依赖查找**。下面咱就可以真正的快速入门 SpringFramework 了】

# 4. 入门-SpringFramework概述与IOC的依赖查找

了解了 IOC 的由来，接下来咱就可以真正的开始学习 SpringFramework 了。首先咱先对 SpringFramework 有一个大概的了解，毕竟学习一项技术，首先要知道它是什么、它都有什么、它能干什么等等。

## 1. SpringFramework概述【了解】

【以下内容可能比较啰里八嗦，想直接拿来面试的小伙伴请直接移步 1.4 节】

### 1.1 官方网站主页

引用官方网站主页的说明，Spring 官方对 SpringFramework 的描述是这样的：

[spring.io/projects/sp…](https://spring.io/projects/spring-framework)

> The Spring Framework provides a comprehensive programming and configuration model for modern Java-based enterprise applications - on any kind of deployment platform.
>
> A key element of Spring is infrastructural support at the application level: Spring focuses on the "plumbing" of enterprise applications so that teams can focus on application-level business logic, without unnecessary ties to specific deployment environments.
>
> Spring 框架为**任何类型的部署平台**上的**基于 Java** 的现代**企业应用程序**提供了全面的**编程和配置模型**。
>
> Spring 的一个关键元素是在**应用程序级别的基础架构支持**：Spring 专注于企业应用程序的 “**脚手架**” ，以便团队可以**专注于应用程序级别的业务逻辑**，而不必与特定的部署环境建立不必要的联系。

这段描述的内容只能用一个词概括：要素过多！对这里面的一些概念作一些解释，方便咱更好地理解这段话。

- 任何类型的部署平台：无论是操作系统，还是 Web 容器（ Tomcat 等）都是可以部署基于 SpringFramework 的应用
- 企业应用程序：包含 JavaSE 和 JavaEE 在内，它被称为一站式解决方案
- 编程和配置模型：基于框架编程，以及基于框架进行功能和组件的配置
- 基础架构支持：SpringFramework 不含任何业务功能，它只是一个底层的应用抽象支撑
- 脚手架：使用它可以更快速的构建应用

想必理解了这些关键概念的意思，也就更容易理解 SpringFramework 的强大了吧！

### 1.2 官方文档

上面看到的只是官方网站的 SpringFramework 工程首页的介绍概述，进入到 5.2 版本的官方文档中，这里面也有一段解释：

[docs.spring.io/spring/docs…](https://docs.spring.io/spring/docs/5.2.x/spring-framework-reference/overview.html#overview)

> Spring makes it easy to create Java enterprise applications. It provides everything you need to embrace the Java language in an enterprise environment, with support for Groovy and Kotlin as alternative languages on the JVM, and with the flexibility to create many kinds of architectures depending on an application’s needs.
>
> Spring 使创建企业级 Java 应用程序变得容易。它提供了在企业环境中使用Java语言所需的一切，并支持 Groovy 和 Kotlin 作为 JVM 上的替代语言，并且可以根据应用程序的需求灵活地创建多种体系结构。

这个描述算是更为概括和笼统吧，它同样解释了 SpringFramework 的强大和使用范围之广，另外它还提了一嘴 “运行在 JVM 上的第二语言”，这些东西咱可能很陌生，那就先不看它了。

下面小册整理一些网络上流传的比较多的 SpringFramework 概述。

### 1.3 网络流传概述

- SpringFramework 是一个分层的、JavaSE / JavaEE 的一站式轻量级开源框架，以 IOC 和 AOP 为内核，并提供表现层、持久层、业务层等领域的解决方案，同时还提供了整合第三方开源技术的能力。
- SpringFramework 是一个 JavaEE 编程领域的轻量级开源框架，它是为了解决企业级编程开发中的复杂性，实现敏捷开发的应用型框架。SpringFramework 是一个容器框架，它集成了各个类型的工具，通过核心的 IOC 容器实现了底层的组件实例化和生命周期管理。
- SpringFramework 是一个开源的容器框架，核心是 IOC 和 AOP ，它为了简化企业级开发而生。SpringFramework 有诸多优良特性（非侵入、容器管理、组件化、轻量级、一站式等）。

观察这些概述，对比官方文档中的描述，可以额外的提取出几个关键词：

- IOC & AOP：SpringFramework 的两大核心特定：**Inverse of Control 控制反转、Aspect Oriented Programming 面向切面编程**
- 轻量级：对比于重量级框架，它的规模更小（可能只有几个 jar 包）、消耗的资源更少
- 一站式：覆盖企业级开发中的所有领域
- 第三方整合：SpringFramework 可以很方便的整合进其他的第三方技术（如持久层框架 MyBatis / Hibernate ，表现层框架 Struts2 ，权限校验框架 Shiro 等）
- 容器：SpringFramework 的底层有一个管理对象和组件的容器，由它来支撑基于 SpringFramework 构建的应用的运行

好了，有了这些概述，最终咱需要提取出一个能尽可能表述完整且精简的概述。

### 1.4 【面试题】面试中如何概述SpringFramework

以下答案**仅供参考**，可根据个人理解和知识储备进行实际调整：

**SpringFramework 是一个开源的、松耦合的、分层的、可配置的一站式企业级 Java 开发框架，它的核心是 IOC 与 AOP ，它可以更容易的构建出企业级 Java 应用，并且它可以根据应用开发的组件需要，整合对应的技术。**

解释下这样概括的要点：

- 加入 “**松耦合**” 的概念是为了描述 IOC 和 AOP ，如果面试继续问 IOC 或耦合相关的内容，那这部分就可以拿去做回应
- 加入 “**可配置**” 是为了给 SpringBoot 垫底（可能还没到这一步，不过现在记住就好啦，后续会讲的）
- IOC 和 AOP 可提可不提，毕竟你只要学了它就肯定知道（人家 Spring 官方都懒得提它。。。）
- 没有提 “轻量级” ，是考虑到现在的大环境趋势早已经没有 EJB 的身影了（EJB是什么东西下面就会提到）
- 没有提 “容器” 的概念，是因为 SpringFramework 不仅仅是一个容器，如果只是限定死容器那相当于说窄了
- 注意对比 “企业级Java开发” 与 “JavaEE开发” 的区别：SpringFramework 不仅能构建在 Web 项目，对于普通的 JavaSE 项目、GUI 项目，也是可以用 SpringFramework 的

------

那既然说要学 SpringFramework ，为啥我就非得要学它啊？它凭什么值得我学呢？

## 2. 为什么使用SpringFramework【重点，面试题】

通过上面对 SpringFramework 的概述，想必也能总结出一些优点和强大之处：

【以下内容可用于面试题】

- **IOC**：组件之间的解耦（咱上一章已经体会到了）
- **AOP**：切面编程可以将应用业务做统一或特定的功能增强，能实现应用业务与增强逻辑的解耦
- **容器**与事件：管理应用中使用的组件Bean、托管Bean的生命周期、事件与监听器的驱动机制
- Web、事务控制、测试、与**其他技术的整合**

可能大多数的条目看上去还是不太容易能理解的，咱先看一眼，脑海里有个印象就可以了。随着深入的学习，这些内容会慢慢的被你理解。

------

要知道一点：学习一门技术，不要知道是什么就立马开始，一些背景还是要稍微了解一下的，了解背景可以为后面的学习作一些信息支撑。

## 3. SpringFramework的发展历史【了解】

聊到 SpringFramework 的发展历史，这里面的故事蛮有意思的，给小伙伴们讲讲那当年的故事。小伙伴大概知道有这么回事就行，没必要记住具体的内容，咱讲这部分也就图一乐。

### 3.1 EJB思想的提出

这个事得说回上个世纪的 1997 年，IBM 公司咱都知道，老大哥了是吧。人家那里头的大佬多啊，面对当时的 J2EE 开发，为了整一套标准的 Java 扩展开发，IBM 的大佬们费心研究，提出了一个技术思想：**EJB** ( Enterprise JavaBean ) ，并且还扬言说，做企业级开发就得按照我说的这么来！按照我这样做是标准的、规范的！

### 3.2 EJB的诞生与程序猿的痛苦

提出 EJB 来之后，这个思想被 Sun （那个时候 Java 还是 Sun 的）看到了，呦呵你这个东西好啊，那我是 Java 他爹啊，你这思想我能给你整合进来，壮大咱 Java 的规模和势力啊。于是在 1998 年，Java 中就有了 EJB 的标准规范，它跟当时 J2EE 的其它技术一起联合（包括 JMS 消息、JNDI 命名目录接口、JSP 服务端页面技术等等），称之为 J2EE 开发的核心技术。随后，IBM 召集的这群大佬就把 EJB 的实现给造出来了，而且在 2002 年 EJB 出了 2.0 版，那个时候基本上 EJB 已经可以横行 J2EE开发了，大家都拿 EJB 当做企业级开发的标准。

不过 EJB 虽然很牛，但学起来实在是太麻烦了，而且它本身是个重量级的技术，与应用业务的代码侵入度实在是有点高，所以搞得大家用 EJB 的时候都好痛苦。但话又说回来，人家 IBM 那么多大佬提出来、实现好的技术，你一句难学、不好用就行了？那是不是你本身太笨了才搞得你学不会呢？

![img](《从0开始深入学习Spring》/200107f1d6a345b284a9847814d5c97a~tplv-k3u1fbpfcp-zoom-1.image)

也由于这个原因吧，当时的 J2EE 开发者们都是一边嘟囔着难用难学，但又不好说出来，只能含泪使用。

### 3.3 SpringFramework的诞生

既然大家都用，难免会有一些铁头娃，人家就是觉得，**你不好用还赖得着我脑子笨？你不好用大家还都就变成猪头了？**于是，一个伟大的神仙级人物要登场了。(bgm......)

时间到了 2002 年，有一个人叫 **Rod Johnson** ，他写了一本书：**《Expert One-on-One J2EE design and development》** ，里面对当时现有的 J2EE 应用的架构和框架存在的臃肿、低效等问题提出了质疑，并且积极寻找和探索解决方案。大概的意思就是说，“我觉得 J2EE 开发挺好的，就是特喵的有些迷惑的设计实在是，徒增成本，方向错了”。

过了 2 年，2004 年 SpringFramework 1.0.0 横空出世，随后 **Rod Johnson** 又写了一本书，当时在 J2EE 开发界引起了巨大轰动，它就是著名的**《Expert one-on-one J2EE Development without EJB》**，这本书中直接告诉开发者完全可以不使用 EJB 开发 J2EE 应用，而是可以换用一种更轻量级、更简单的框架来代替，那就是 **SpringFramework** 。

这本书一出来，开发圈都是这样的：

![img](《从0开始深入学习Spring》/393b0760c88047119410ce83e31a90e7~tplv-k3u1fbpfcp-zoom-1.image)

你一个毛头小子还敢质疑 IBM 诸多大佬的设计精华？这么狂不怕被揍吗？但是！人的四大本质之一 ———— **真香怪**。后来开发界的程序猿们用了 SpringFramework 感觉确实比 EJB 好，而且 SpringFramework 提供的一些特性也比 EJB 好，于是大家就慢慢转投 SpringFramework 了。

### 3.4 SpringFramework的版本迭代

下面咱列出一个 SpringFramework 的重要版本更新时间及重大特性，现阶段小伙伴们可以只是看一眼，后面咱讲到具体的内容时都会提及到。

| SpringFramework版本 | 对应jdk版本 | 重要特性                                                     |
| ------------------- | ----------- | ------------------------------------------------------------ |
| SpringFramework 1.x | jdk 1.3     | 基于 xml 的配置                                              |
| SpringFramework 2.x | jdk 1.4     | 改良 xml 文件、初步支持注解式配置                            |
| SpringFramework 3.x | Java 5      | 注解式配置、JavaConfig 编程式配置、Environment 抽象          |
| SpringFramework 4.x | Java 6      | SpringBoot 1.x、核心容器增强、条件装配、WebMvc 基于 Servlet3.0 |
| SpringFramework 5.x | Java 8      | SpringBoot 2.x、响应式编程、SpringWebFlux、支持 Kotlin       |



## 4. SpringFramework包含的模块【熟悉，面试题】

大致了解一下 SpringFramework 的核心模块，以及包含的技术，混个脸熟。

【以下内容可用于面试题】

- beans、core、context、expression 【核心包】
- aop 【切面编程】
- jdbc 【整合 jdbc 】
- orm 【整合 ORM 框架】
- tx 【事务控制】
- web 【 Web 层技术】
- test 【整合测试】
- ......

------

好了，啰里八嗦了那么多，下面咱终于可以动手操作啦！冲冲冲！

## 5. 快速入门-IOC-DL【掌握】

下面咱用一个最最简单的实例，来体会 SpringFramework 中对于依赖查找的使用。

### 5.1 引入依赖

对于快速入门阶段来讲，咱只需要引入一个依赖即可：`spring-context` （此处引入的版本是 5.2.8 ）

```xml
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-context</artifactId>
    <version>5.2.8.RELEASE</version>
</dependency>
```

### 5.2 创建配置文件

像前面咱推演出来的规矩差不多，SpringFramework 实现 IOC 可以借助配置文件的方式来描述类和对象的定义信息。在工程的 `resources` 目录下，咱创建一个 `quickstart-byname.xml` 文件（为了使配置文件的存放更具条理，且容易维护，咱提前创建好一个文件夹）：

![img](《从0开始深入学习Spring》/16f6e60f6a3545dfa612f73ffea1c6a6~tplv-k3u1fbpfcp-zoom-1.image)

这里面的初始内容是预先规定好的，从 SpringFramework 的官方文档中可以找到 xml 配置文件的空架子：[docs.spring.io/spring/docs…](https://docs.spring.io/spring/docs/5.2.x/spring-framework-reference/core.html#beans-factory-instantiation)

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd">

</beans>
```

将这段内容粘贴到 `quickstart-byname.xml` 中即可。

### 5.3 [可选] 配置IDEA项目工程中的应用上下文

小伙伴们可能注意到了，粘贴了上面这段 xml 后，IDEA 会弹出一段提示：

![img](《从0开始深入学习Spring》/11788d98750a44ae842d1a8811424e3d~tplv-k3u1fbpfcp-zoom-1.image)

由此可见 IDEA 是多么的智能，它意识到你要在工程中添加 SpringFramework 的配置文件，它就想让你把这个配置文件配置到 IDEA 的项目工作环境下，那咱只需要按照提示，点击 `Configure application context` ，随后点击 `Create new application context...` ，会弹出一个对话框，让你创建应用上下文：

![img](《从0开始深入学习Spring》/02316f3b83f14bdb9ad7c30b6778548c~tplv-k3u1fbpfcp-zoom-1.image)

啥也不用管，直接点 OK ，就完事了。此番动作是让 IDEA 也知道，咱在使用 SpringFramework 开发应用，IDEA 会自动识别咱写的配置，可以帮我们省很多心。

### 5.4 声明一个普通的类

由于我的 `src/main/java` 中创建的包结构是按照咱小册的章节划分的，小伙伴们可以根据自己的习惯和喜好，划分包结构。下面我在咱这一小节的 `com.linkedbear.spring.basic_dl.a_quickstart_byname` 包下创建一个 bean 包，随后创建一个 `Person` 类：

![img](《从0开始深入学习Spring》/5a2f941385e14ff3a8da60d21ff0bf21~tplv-k3u1fbpfcp-zoom-1.image)

创建好就可以放那儿了，也不用在里面写这写那的。

### 5.5 在配置文件中加入Person声明

在 `quickstart-byname.xml` 中，使用 SpringFramework 的定义规则，将 `Person` 声明到配置文件中：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="person" class="com.linkedbear.spring.basic_dl.a_quickstart_byname.bean.Person"></bean>
</beans>
```

可以看到声明的规则很简单，跟之前咱写的 properties 形式几乎一个意思，也是 key 和 value ，只不过这里分别对应的是 id 和 class 罢了。

这么写完之后 IDEA 会报 xml 标签体为空，根据咱学过的 HTML 基础，应该知道，没有标签体的情况下是可以省略闭合标签的，咱这里就不省略了，后续还要往里面加东西。

### 5.6 创建启动类

有了配置文件，下一步可以来读这个配置文件了。在 `a_quickstart_byname` 包下创建一个 `QuickstartByNameApplication` 类，并声明 `main` 方法：

```java
public class QuickstartByNameApplication {
    public static void main(String[] args) {
    
    }
}
```

> （我个人的习惯，在写 `main` 方法时喜欢在方法上顺带抛 `Exception` ，这样大部分场景下可以不用关心 `try-catch` 操作，所以后续看到 `main` 方法中带了 `throws Exception` 的操作，不要方，个人编码习惯而已）

`main` 方法中要读这个配置文件，方法有很多种，咱快速入门中先来使用一种比较简单的方法：

```java
public static void main(String[] args) throws Exception {
    BeanFactory factory = new ClassPathXmlApplicationContext("basic_dl/quickstart-byname.xml");
    Person person = (Person) factory.getBean("person");
    System.out.println(person);
}
```

解释一下这段代码的意思。读取配置文件，需要一个载体来加载它，这里咱选用 `ClassPathXmlApplicationContext` 来加载。加载完成后咱直接使用 `BeanFactory` 接口来接收（多态思想）。下一步就可以从 `BeanFactory` 中获取 `person` 了，由于咱在配置文件中声明了 id ，故这里就可以直接把 id 传入，`BeanFactory` 就可以给我们返回 `Person` 对象。

运行 `main` 方法，可以成功打印出 `Person` 的全限定类名 + 内存地址，证明编写成功。

```
com.linkedbear.spring.basic_dl.a_quickstart_byname.bean.Person@6a4f787b
```

到这里，就可以轻松上手 SpringFramework 中 IOC 依赖查找的实现了。

## 小结与思考

1. 什么是 SpringFramework ？为什么要用 SpringFramework ？
2. 动手完成一个最基本的 IOC 依赖查找实例。

【上面的依赖查找只是 SpringFramework 最最基本的方式，下一章咱介绍更多关于依赖查找的使用方式，以及了解 IOC 的另一种实现：**依赖注入**】

# 5. 入门-IOC依赖查找&依赖注入

上一章中咱引入了一个最最简单的依赖查找实例，本章咱会继续展开更多的依赖查找实验，来体会 IOC 的依赖查找。后半段咱会介绍 IOC 的另外一个实现方式：依赖注入。

## 1. 依赖查找【掌握】

### 1.1 最简单的实验-byName

上一章已经做过最简单的实验了，不再重复。

### 1.2 根据类型查找-byType

> 本小节源码位置：`com.linkedbear.spring.basic_dl.b_bytype`

为了与上面的实验区分开，咱复制原有的 `quickstart-byname.xml` ，并拷贝出一份新的 `quickstart-bytype.xml` ，咱在这里面修改。

声明 bean 时，这次我不再声明 id 属性：

```xml
<bean class="com.linkedbear.spring.basic_dl.b_bytype.bean.Person"></bean>
```

启动类 `QuickstartByTypeApplication` 中，这次调用的方法不再是传 name 的 `getBean` 方法，而是直接传 `Class` 类型：

```java
public static void main(String[] args) throws Exception {
    BeanFactory factory = new ClassPathXmlApplicationContext("basic_dl/quickstart-bytype.xml");
    Person person = factory.getBean(Person.class);
    System.out.println(person);
}
```

有木有注意到，这次接收的 person 不用强转了！（那不是废话嘛 →_→ ，都把类型传进去了，人家 `BeanFactory` 给你找的时候肯定就是这个类型呀）

运行 `main` 方法，发现可以正常打印出 `Person` 的全限定名：

```
com.linkedbear.spring.basic_dl.b_bytype.bean.Person@6d4b1c02
```

### 1.3 接口与实现类

咱把之前介绍 IOC 思想的 Dao 拿过来：

![img](《从0开始深入学习Spring》/9ffa50d919b843a19dcc4997db1da4e2~tplv-k3u1fbpfcp-zoom-1.image)

之后在 `quickstart-bytype.xml` 中加入 `DemoDaoImpl` 的声明定义：

```xml
<bean class="com.linkedbear.spring.basic_dl.b_bytype.dao.impl.DemoDaoImpl"/>
```

之后在启动类 `QuickstartByTypeApplication` 中，借助 `BeanFactory` 取出 `DemoDao` ，并打印 `findAll` 方法的返回数据：

```java
public static void main(String[] args) throws Exception {
    BeanFactory factory = new ClassPathXmlApplicationContext("basic_dl/quickstart-bytype.xml");
    Person person = factory.getBean(Person.class);
    System.out.println(person);

    DemoDao demoDao = factory.getBean(DemoDao.class);
    System.out.println(demoDao.findAll());
}
```

运行 `main` 方法，控制台可以打印出 `[aaa, bbb, ccc]` ，证明 `DemoDaoImpl` 也成功注入，并且 `BeanFactory` 可以根据接口类型，找到对应的实现类。

## 2. 依赖注入【掌握】

由上面的实例可以发现一个问题：创建的 Bean 都是不带属性的！如果我要创建的 Bean 需要一些预设的属性，那该怎么办呢？那就涉及到 IOC 的另外一种实现了，就是**依赖注入**。还是延续 IOC 的思想，**如果你需要属性依赖，不要自己去找，交给 IOC 容器，让它帮你找**，并给你赋上值。

下面咱快速体验一个依赖注入的例子。

> 本小节源码位置：`com.linkedbear.spring.basic_di.a_quickstart_set`

### 2.1 最简单的实验-简单属性值注入

新建一个包 `basic_di` ，咱在这里面写有关依赖注入的实验。

#### 2.1.1 声明类+配置文件

声明两个类：`Person` 与 `Cat` ，形成“猫需要依赖人”的场景：

```java
public class Person {
    private String name;
    private Integer age;
    // getter and setter ......
}

public class Cat {
    private String name;
    private Person master;
    // getter and setter ......
}
```

之后，咱在 `resources` 目录下新建 `basic_di` 文件夹，并声明配置文件 `inject-set.xml` ：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="person" class="com.linkedbear.spring.basic_di.a_quickstart_set.bean.Person"></bean>

    <bean id="cat" class="com.linkedbear.spring.basic_di.a_quickstart_set.bean.Cat"></bean>
</beans>
```

到现在为止，这些操作还都是咱学过的内容吧，没有新的知识。

#### 2.1.2 编写启动类

回到包下，新增一个启动类 `QuickstartInjectBySetXmlApplication` ，并编写 `main` 方法初始化 `BeanFactory` ：

```java
public class QuickstartInjectBySetXmlApplication {
    public static void main(String[] args) throws Exception {
        BeanFactory beanFactory = new ClassPathXmlApplicationContext("basic_di/inject-set.xml");
        Person person = beanFactory.getBean(Person.class);
        System.out.println(person);
        
        Cat cat = beanFactory.getBean(Cat.class);
        System.out.println(cat);
    }
}
```

运行 `main` 方法，发现打印的 person 与 cat 的所有属性都是 null ：

```
Person{name='null', age=null}
Cat{name='null', master=null}
```

#### 2.1.3 给Person赋属性值

下面咱给 Person 的两个属性赋值。在 `<bean>` 标签中，可以声明如下一些标签：

![img](《从0开始深入学习Spring》/0b87bc08c234447ea7dab43d246ad0bf~tplv-k3u1fbpfcp-zoom-1.image)

这些标签咱不用全记住，学到哪个记哪个即可。现在咱要用的是第一个：**`property`** 。

在 person 的 `<bean>` 标签中声明 `property` 标签，这里面有两个属性：**name - 属性名，value - 属性值**。所以咱可以用如下方式来进行属性赋值：

```xml
<bean id="person" class="com.linkedbear.spring.basic_di.a_quickstart_set.bean.Person">
    <property name="name" value="test-person-byset"/>
    <property name="age" value="18"/>
</bean>
```

声明之后，保存，回到启动类，重新运行，发现 person 已经有值了：

```
Person{name='test-person-byset', age=18}
Cat{name='null', master=null}
```

### 2.2 关联Bean赋值

上面打印的结果明显 cat 还没有值，而且 master 的类型是 `Person` ，下面咱要给 cat 赋值。

对于 `property` 标签，除了可以声明 `value` 之外，还可以声明另外一个属性：**`ref`** ，它代表**要关联赋值的 Bean 的 id** 。 由此，对于 cat 中的 master 属性，可以有如下赋值方法：

```xml
<bean id="cat" class="com.linkedbear.spring.basic_di.a_quickstart_set.bean.Cat">
    <property name="name" value="test-cat"/>
    <!-- ref引用上面的person对象 -->
    <property name="master" ref="person"/>
</bean>
```

声明好后，重新运行启动类，发现 cat 也有属性了：

```
Person{name='test-person-byset', age=18}
Cat{name='test-cat', master=Person{name='test-person-byset', age=18}}
```

------

最后，咱对比一下这两种 IOC 的实现方式。

## 3. 【面试题】依赖查找与依赖注入的对比

以下答案仅供参考，可根据自己的理解调整回答内容：

- 作用目标不同
  - 依赖注入的作用目标通常是类成员
  - 依赖查找的作用目标可以是方法体内，也可以是方法体外
- 实现方式不同
  - 依赖注入通常借助一个上下文被动的接收
  - 依赖查找通常主动使用上下文搜索

## 小结与练习

1. IOC 的两种实现方式是什么？它们的区别和联系是什么？
2. 动手实现三层架构中的 service 层与 dao 层，实际体会依赖查找与依赖注入的使用。

【快速入门之后，下面咱就可以慢慢解锁新的姿势了，下一章咱来介绍更多关于依赖查找的方式，以及引出 SpringFramework 中的另一个核心概念：**`ApplicationContext`** 】

# 6. IOC基础-依赖查找高级&BeanFactory与ApplicationContext

上一章，咱了解了 IOC 的两种实现的基本用法，这一章咱来介绍更多关于依赖查找的使用方式。

> 本章源码均在：`com.linkedbear.spring.basic_dl`

## 1. 依赖查找的多种姿势【掌握】

### 1.1 ofType

试想，如果一个接口有多个实现，而咱又想一次性把这些都拿出来，那 `getBean` 方法显然就不够用了，需要使用额外的方式。

回到 `basic_dl` 包下，咱新创建一个 `oftype` 的包，来测试 **ofType** 的查找方式。

#### 1.1.1 声明Bean+配置文件

声明一个 `DemoDao` ，并声明 3 种对应的实现类，分别模拟操作 MySQL 、Oracle 、Postgres 数据库的实现类：

![img](《从0开始深入学习Spring》/d521e012f54941acb5daf7a54d756a00~tplv-k3u1fbpfcp-zoom-1.image)

对应的配置类，也把这几个 Bean 都注册上：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="demoMySQLDao" class="com.linkedbear.spring.basic_dl.c_oftype.dao.impl.DemoMySQLDao"/>
    <bean id="demoOracleDao" class="com.linkedbear.spring.basic_dl.c_oftype.dao.impl.DemoOracleDao"/>
    <bean id="demoPostgreDao" class="com.linkedbear.spring.basic_dl.c_oftype.dao.impl.DemoPostgresDao"/>
</beans>
```

#### 1.1.2 测试启动类

在启动类中，创建 `BeanFactory` 后，尝试一次性取出多个 Bean ，结果发现 `BeanFactory` 中并没有这样的方法：

![img](《从0开始深入学习Spring》/0a59f26ff7a948ccad9c7ce57965d3a7~tplv-k3u1fbpfcp-zoom-1.image)

此时咱的内心一定是：

![img](《从0开始深入学习Spring》/4bd697043b234c0a863a7119f17a51ab~tplv-k3u1fbpfcp-zoom-1.image)

没有这种实现吗？？？那我咋获取这些呢？

其实并不是人家没实现，只是咱用错了接口而已 (￣▽￣)／

这样，咱先改，改完了再解释为什么这么改。

#### 1.1.3 改用ApplicationContext

将 `BeanFactory` 接口换为 `ApplicationContext` ，再次尝试调用方法，发现了一个这样的方法：

![img](《从0开始深入学习Spring》/e52eadc4868f4085955d1d3cdef02b1f~tplv-k3u1fbpfcp-zoom-1.image)

它可以**传入一个类型，返回一个 Map** ，而 Map 中的 value 不难猜测就是**传入的参数类型对应的那些类 / 实现类**。

那咱就拿出来，foreach 一下呗：

```java
public class OfTypeApplication {
    
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new ClassPathXmlApplicationContext("basic_dl/quickstart-oftype.xml");
        Map<String, DemoDao> beans = ctx.getBeansOfType(DemoDao.class);
        beans.forEach((beanName, bean) -> {
            System.out.println(beanName + " : " + bean.toString());
        });
    }
}
```

运行 `main` 方法，控制台真的打印了上面声明的那3个类：

```
demoMySQLDao : com.linkedbear.spring.basic_dl.c_oftype.dao.impl.DemoMySQLDao@4883b407
demoOracleDao : com.linkedbear.spring.basic_dl.c_oftype.dao.impl.DemoOracleDao@7d9d1a19
demoPostgreDao : com.linkedbear.spring.basic_dl.c_oftype.dao.impl.DemoPostgresDao@39c0f4a
```

这样就实现了传入一个接口 / 抽象类，返回容器中所有的实现类 / 子类。

讲到这里，咱先停下来，解释下为什么换用 `ApplicationContext` 。

## 2. BeanFactory与ApplicationContext【掌握】

借助 IDEA ，发现 `ApplicationContext` 也是一个接口，而且通过接口继承关系发现它是 `BeanFactory` 的子接口。那咱想了解这两个接口，最好的办法还是先翻一翻官方文档，从官方文档中尝试获取最权威的解释。

### 2.1 官方文档的解释

在官方文档 [docs.spring.io/spring/docs…](https://docs.spring.io/spring/docs/5.2.x/spring-framework-reference/core.html#beans-introduction) 中，有一个段落解释了这两个接口的关系：

> The `org.springframework.beans` and `org.springframework.context` packages are the basis for Spring Framework’s IoC container. The [`BeanFactory`](https://docs.spring.io/spring-framework/docs/5.2.x/javadoc-api/org/springframework/beans/factory/BeanFactory.html) interface provides an advanced configuration mechanism capable of managing any type of object. [`ApplicationContext`](https://docs.spring.io/spring-framework/docs/5.2.x/javadoc-api/org/springframework/context/ApplicationContext.html) is a sub-interface of `BeanFactory`. It adds:
>
> - Easier integration with Spring’s AOP features
> - Message resource handling (for use in internationalization)
> - Event publication
> - Application-layer specific contexts such as the `WebApplicationContext` for use in web applications.
>
> `org.springframework.beans` 和 `org.springframework.context` 包是 SpringFramework 的 IOC 容器的基础。`BeanFactory` 接口提供了一种高级配置机制，能够管理任何类型的对象。`ApplicationContext` 是 `BeanFactory` 的子接口。它增加了：
>
> - 与 SpringFramework 的 AOP 功能轻松集成
> - 消息资源处理（用于国际化）
> - 事件发布
> - 应用层特定的上下文，例如 Web 应用程序中使用的 `WebApplicationContext`

这样说下来，给咱的主观感受是：**`ApplicationContext` 包含 `BeanFactory` 的所有功能，并且人家还扩展了好多特性**，其实就是这么回事。

而且，官方文档的下面还有一段，解释了我们为什么应该用 `ApplicationContext` 而不是 `BeanFactory` ：[docs.spring.io/spring/docs…](https://docs.spring.io/spring/docs/5.2.x/spring-framework-reference/core.html#context-introduction-ctx-vs-beanfactory)

> You should use an `ApplicationContext` unless you have a good reason for not doing so, with `GenericApplicationContext` and its subclass `AnnotationConfigApplicationContext` as the common implementations for custom bootstrapping. These are the primary entry points to Spring’s core container for all common purposes: loading of configuration files, triggering a classpath scan, programmatically registering bean definitions and annotated classes, and (as of 5.0) registering functional bean definitions.
>
> 你应该使用 `ApplicationContext` ，除非能有充分的理由解释不需要的原因。一般情况下，我们推荐将 `GenericApplicationContext` 及其子类 `AnnotationConfigApplicationContext` 作为自定义引导的常见实现。这些实现类是用于所有常见目的的 SpringFramework 核心容器的主要入口点：加载配置文件，触发类路径扫描，编程式注册 Bean 定义和带注解的类，以及（从5.0版本开始）注册功能性 Bean 的定义。

这段话的下面还给了一张表，对比了 `BeanFactory` 与 `ApplicationContext` 的不同指标：

| Feature                                                      | `BeanFactory` | `ApplicationContext` |
| ------------------------------------------------------------ | ------------- | -------------------- |
| Bean instantiation/wiring —— Bean的实例化和属性注入          | Yes           | Yes                  |
| Integrated lifecycle management —— 生命周期管理              | No            | Yes                  |
| Automatic `BeanPostProcessor` registration —— Bean后置处理器的支持 | No            | Yes                  |
| Automatic `BeanFactoryPostProcessor` registration —— BeanFactory后置处理器的支持 | No            | Yes                  |
| Convenient `MessageSource` access (for internalization) —— 消息转换服务（国际化） | No            | Yes                  |
| Built-in `ApplicationEvent` publication mechanism —— 事件发布机制（事件驱动） | No            | Yes                  |



由此可以发现，`ApplicationContext` 真的比 `BeanFactory` 强大太多了，所以咱还是选择使用 `ApplicationContext` 吧！

### 2.2 【面试题】BeanFactory与ApplicationContext的对比

既然都聊到这个份上了，那咱就顺便来一道面试题吧，看看这个问题如何在面试中回答会比较合适。

以下答案仅供参考，可根据自己的理解调整回答内容：

`BeanFactory` 接口提供了一个**抽象的配置和对象的管理机制**，`ApplicationContext` 是 `BeanFactory` 的子接口，它简化了与 AOP 的整合、消息机制、事件机制，以及对 Web 环境的扩展（ `WebApplicationContext` 等），`BeanFactory` 是没有这些扩展的。

`ApplicationContext` 主要扩展了以下功能：

- AOP 的支持（ `AnnotationAwareAspectJAutoProxyCreator` 作用于 Bean 的初始化之后 ）
- 配置元信息（ `BeanDefinition` 、`Environment` 、注解等 ）
- 资源管理（ `Resource` 抽象 ）
- 事件驱动机制（ `ApplicationEvent` 、`ApplicationListener` ）
- 消息与国际化（ `LocaleResolver` ）
- `Environment` 抽象（ SpringFramework 3.1 以后）

> 目前可以只记住前面的部分，括号内的内容可以先略过，等到学完整遍的 SpringFramework ，再回过头看时自然会有那种“会心一笑”的感觉的ヽ(￣▽￣)ﾉ 。

------

好了，初步了解了 `BeanFactory` 与 `ApplicationContext` 的区别，也知道 `ApplicationContext` 更加强大，下面咱就继续研究依赖查找的花板子吧。

## 3. 继续研究依赖查找

### 3.1 withAnnotation【熟悉】

IOC 容器除了可以根据一个父类 / 接口来找实现类，还可以根据类上标注的注解来查找对应的 Bean 。下面咱来测试包含注解的 Bean 如何被查找。

#### 3.1.1 声明Bean+注解+配置文件

新建一个包 `d_withanno` ，并在里面声明一个注解：`@Color` 。

```java
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.TYPE)
public @interface Color {

}
```

之后，创建几个类，以及运行 `main` 方法的启动类：

![img](《从0开始深入学习Spring》/89e8d70873874dd783527e82554a4589~tplv-k3u1fbpfcp-zoom-1.image)

其中，`Black` 与 `Red` 的类上标注 `@Color` 注解，`Dog` 不标注（废话，一只狗上什么色儿~~~）

对应的，配置文件中声明好这几个类。

#### 3.1.2 测试启动类

`ApplicationContext` 中有一个方法叫 `getBeansWithAnnotation` ，它可以传入一个注解的 class ，返回所有被这个注解标注的 bean 。于是咱的测试启动类可以这样写：

```java
public class WithAnnoApplication {
    
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new ClassPathXmlApplicationContext("basic_dl/quickstart-withanno.xml");
        Map<String, Object> beans = ctx.getBeansWithAnnotation(Color.class);
        beans.forEach((beanName, bean) -> {
            System.out.println(beanName + " : " + bean.toString());
        });
    }
}
```

运行 `main` 方法，可以发现控制台只打印了 `Black` 和 `Red` ，证明成功取出。

```
black : com.linkedbear.spring.basic_dl.d_withanno.bean.Black@553f17c
red : com.linkedbear.spring.basic_dl.d_withanno.bean.Red@6c3708b3
```

### 3.2 获取IOC容器中的所有Bean【熟悉】

如果真的会有这么一个需求，要取出当前 IOC 容器中的所有 bean ，这个时候一个一个取是不现实的，因为你根本不知道都有谁，不知道到底有哪些你还没见过的小盆友们。。。所以这个时候就要用到 `ApplicationContext` 的另一个方法了：`getBeanDefinitionNames` 。

看这个方法名，感觉像是获取 bean 的定义名称，这跟 name 有什么关系吗？这里先告诉你，它获取的就是那些 Bean 的 **id** ，至于这些关于定义的信息，后续也会讲到的，小伙伴们先学习这些比较基础的东西即可。

接下来咱就试一下这个 `getBeanDefinitionNames` 方法的效果，编写一个新的启动类，这次咱就不再造 bean 了，咱直接拿上面刚测试过的吧：

```java
public class BeannamesApplication {
    
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new ClassPathXmlApplicationContext("basic_dl/quickstart-withanno.xml");
        String[] beanNames = ctx.getBeanDefinitionNames();
        // 利用jdk8的Stream快速编写打印方法
        Stream.of(beanNames).forEach(System.out::println);
    }
}
```

运行 `main` 方法，发现控制台上真的打印了咱自己创建的几个 bean ：

```
black
red
dog
```

那既然 Bean 的 id 都出来了，那取出来还不是轻而易举？这个咱都很熟悉了，就不再演示了。

## 4. 依赖查找的高级使用——延迟查找【熟悉】

对于一些特殊的场景，需要依赖容器中的某些特定的 Bean ，但当它们不存在时也能使用默认 / 缺省策略来处理逻辑。这个时候，使用上面已经学过的方式倒是可以实现，但编码可能会不很优雅。

### 4.1 使用现有方案实现Bean缺失时的缺省加载

咱把设计做的简单一些，准备两个 bean ：`Cat` 和 `Dog` ，但是在 xml 中咱只注册 `Cat` ，这样 IOC 容器中就只有 `Cat` ，没有 `Dog` 。

之后，咱来编写启动类。由于 Dog 没有在 IOC 容器中，所以调用 `getBean` 方法时会报 `NoSuchBeanDefinitionException` ，为了保证能在没有找到 Bean 的时候启用缺省策略，咱可以在 catch 块中手动创建，实现代码如下：

```java
public class ImmediatlyLookupApplication {
    
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new ClassPathXmlApplicationContext("basic_dl/quickstart-lazylookup.xml");
        Cat cat = ctx.getBean(Cat.class);
        System.out.println(cat);
        
        Dog dog;
        try {
            dog = ctx.getBean(Dog.class);
        } catch (NoSuchBeanDefinitionException e) {
            // 找不到Dog时手动创建
        	dog = new Dog();
        }
        System.out.println(dog);
    }

}
```

可以发现这种编码方式相当不优雅，而且很别扭（性能也低）。如果真的后续每一个 bean 都这样操作，那编码量岂不是巨大？这肯定不行，一定有改良方案。

### 4.2 改良-获取之前先检查

既然作为一个容器，能获取自然就能有检查，`ApplicationContext` 中有一个方法就可以专门用来检查容器中是否有指定的 Bean ：`containsBean`

```java
    Dog dog = ctx.containsBean("dog") ? (Dog) ctx.getBean("dog") : new Dog();
```

但注意，这个 `containsBean` 方法只能传 bean 的 id ，不能查类型，所以虽然可以改良前面的方案，但还是有问题：如果 Bean 的名不叫 dog ，叫 wangwang ，那这个方法岂不是废了？所以这个方案还是不够好，需要改良。

### 4.3 改良-延迟查找

如果能有一种机制，我想获取一个 Bean 的时候，你可以**先不给我报错，先给我一个包装让我拿着，回头我自己用的时候再拆开决定里面有还是没有**，这样是不是就省去了 IOC 容器报错的麻烦事了呢？在 SpringFramework 4.3 中引入了一个新的 API ：**`ObjectProvider`** ，它可以实现延迟查找。

于是，咱可以改良上面的代码如下：（为了保留上面的案例示范，下面新起一个类）

```java
public class LazyLookupApplication {
    
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new ClassPathXmlApplicationContext("basic_dl/quickstart-lazylookup.xml");
        Cat cat = ctx.getBean(Cat.class);
        System.out.println(cat);
        // 下面的代码会报Bean没有定义 NoSuchBeanDefinitionException
        // Dog dog = ctx.getBean(Dog.class);
    
        // 这一行代码不会报错
        ObjectProvider<Dog> dogProvider = ctx.getBeanProvider(Dog.class);
    }
}
```

可以发现，`ApplicationContext` 中有一个方法叫 `getBeanProvider` ，它就是返回上面说的那个**“包装”**。如果直接 `getBean` ，那如果容器中没有对应的 Bean ，就会报 `NoSuchBeanDefinitionException`；如果使用这种方式，运行 `main` 方法后发现并没有报错，只有调用 `dogProvider` 的 `getObject` ，真正要取包装里面的 Bean 时，才会报异常。所以总结下来，`ObjectProvider` 相当于**延后了 Bean 的获取时机，也延后了异常可能出现的时机**。

但是，上面的问题还没有被解决呀，调用 `getObject` 方法还是会报异常，那下面咱就继续研究 `ObjectProvider` 的其他一些方法。

### 4.4 延迟查找-方案实现

`ObjectProvider` 中还有一个方法：`getIfAvailable` ，它可以在**找不到 Bean 时返回 null 而不抛出异常**。使用这个方法，就可以避免上面的问题了。改良之后的代码如下：

```java
    Dog dog = dogProvider.getIfAvailable();
    if (dog == null) {
        dog = new Dog();
    }
```

### 4.5 ObjectProvider在jdk8的升级

随着 SpringFramework 5.0 基于 jdk8 的发布，函数式编程也被大量用于 SpringFramework 中。`ObjectProvider` 中新加了几个方法，可以使编码更佳优雅。

看着上面 4.4 节的那几行代码，有木有联想到 `Map` 中的 `getOrDefault` ？由此，`ObjectProvider` 在 SpringFramework 5.0 后扩展了一个带 `Supplier` 参数的 `getIfAvailable` ，它可以在找不到 Bean 时直接用 **`Supplier`** 接口的方法返回默认实现，由此上面的代码还可以进一步简化为：

```java
    Dog dog = dogProvider.getIfAvailable(() -> new Dog());
```

或者更简单的，使用方法引用：

```java
    Dog dog = dogProvider.getIfAvailable(Dog::new);
```

当然，一般情况下，取出的 Bean 都会马上或者间歇的用到，`ObjectProvider` 还提供了一个 `ifAvailable` 方法，可以在 Bean 存在时执行 `Consumer` 接口的方法：

```java
    dogProvider.ifAvailable(dog -> System.out.println(dog)); // 或者使用方法引用
```

以上就是关于延迟查找的内容，这种方案可以使用，但在日常开发中可能使用的不是很多，小伙伴们实际动手操作一遍，有一个印象即可。后续如果升级到更高的位置，这部分或许会在封装组件和底层时用到。

## 小结与练习

1. 如何对比 `BeanFactory` 与 `ApplicationContext` ？`ApplicationContext` 都在 `BeanFactory` 的基础上扩展了哪些特性？
2. 动手练习一下前面几章已经学过的所有 `ApplicationContext` 中的依赖查找方式，加深印象。

【对于依赖查找这部分，其实难度还不算很大，小伙伴只需要多加练习，掌握起来也是非常简单的。下一章咱先不深入研究依赖注入，来聊一个区别于 xml 的驱动方式：**注解驱动**】

# 7. IOC基础-注解驱动IOC与组件扫描

自打 SpringFramework 推出 3.0 后，最低的版本支持来到了 Java 5 ，我们也知道，Java 5 的最大新特性之一就是引入了**注解**。SpringFramework 3.0 开始也引入了大量注解，代替 xml 的方式进行声明式开发。这一章，咱来了解 SpringFramework 中的注解驱动开发，同时体会几个案例。

## 1. 注解驱动IOC容器【掌握】

在 xml 驱动的 IOC 容器中，咱使用的是 `ClassPathXmlApplicationContext` ，它对应的是类路径下的 xml 驱动。对于注解配置的驱动，那自然可以试着猜一下，应该是 Annotation 开头的，ApplicationContext 结尾。那就是下面咱介绍的 `AnnotationConfigApplicationContext` 。

咱新建一个 `annotation` 包，用来讲解关于注解驱动 IOC 的部分。

> 本章源码均在 `com.linkedbear.spring.annotation`

### 1.1 注解驱动IOC的依赖查找

#### 1.1.1 配置类的编写与Bean的注册

对比于 xml 文件作为驱动，注解驱动需要的是**配置类**。一个配置类就可以类似的理解为一个 xml 。配置类没有特殊的限制，只需要在类上标注一个 `@Configuration` 注解即可。

```java
@Configuration
public class QuickstartConfiguration {

}
```

在 xml 中，咱声明 Bean 是通过 `<bean>` 标签。

```xml
<bean id="person" class="com.linkedbear.spring.basic_dl.a_quickstart_byname.bean.Person"/>
```

在配置类中，要想替换掉 `<bean>` 标签，自然也能想到，它是使用 `@Bean` 注解。

```java
@Bean
public Person person() {
    return new Person();
}
```

这种使用方式，可以解释为：**向 IOC 容器注册一个类型为 Person ，id 为 person 的 Bean** 。**方法的返回值代表注册的类型，方法名代表 Bean 的 id** 。当然，也可以直接在 `@Bean` 注解上显式的声明 Bean 的 id ，只不过在注解驱动的范畴里，它不叫 id 而是叫 **name** ：

```java
@Bean(name = "aaa") // 4.3.3之后可以直接写value
public Person person() {
    return new Person();
}
```

这样就算把配置类编写好了。

#### 1.1.2 启动类初始化注解IOC容器

像上面所说的，咱使用 `AnnotationConfigApplicationContext` 来驱动注解 IOC 容器，在构造方法中把配置类传入：

```java
public class AnnotationConfigApplication {
    
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new AnnotationConfigApplicationContext(QuickstartConfiguration.class);
        Person person = ctx.getBean(Person.class);
        System.out.println(person);
    }
}
```

运行，可以发现 `Person` 被打印，证明编写成功。

### 1.2 注解驱动IOC的依赖注入

编码方式的依赖注入可以说是相当简单了，直接在创建对象后先别着急返回，把里面的值都 set 进去，再返回即可：

```java
@Bean
public Person person() {
    Person person = new Person();
    person.setName("person");
    person.setAge(123);
    return person;
}
```

就相当于：

```xml
<bean id="person" class="com.linkedbear.spring.basic_di.a_quickstart_set.bean.Person">
    <property name="name" value="test-person-byset"/>
    <property name="age" value="18"/>
</bean>
```

------

```java
@Bean
public Cat cat() {
    Cat cat = new Cat();
    cat.setName("test-cat-anno");
    // 直接拿上面的person()方法作为返回值即可，相当于ref
    cat.setMaster(person());
    return cat;
}
```

就相当于：

```xml
<bean id="cat" class="com.linkedbear.spring.basic_di.a_quickstart_set.bean.Cat">
    <property name="name" value="test-cat"/>
    <property name="master" ref="person"/>
</bean>
```

其余部分与上面一模一样，不再展开。

### 1.3 注解IOC容器的其他用法

翻看 `AnnotationConfigApplicationContext` 的构造方法，可以发现它还有一个方法，是传入一组 `basePackage` ，翻译过来是 “根包” 的意思，它又是什么意思呢？这就涉及到下面的概念了：**组件注册与扫描**。

## 2. 组件注册与组件扫描【掌握】

上面声明的方式，如果需要注册的组件特别多，那编写这些 `@Bean` 无疑是超多工作量，于是 SpringFramework 中给咱整了几个注解出来，可以帮咱快速注册需要的组件，这些注解被成为**模式注解 ( stereotype annotation )**。

### 2.1 一切组件注册的根源：@Component

在类上标注 `@Component` 注解，即代表该类会被注册到 IOC 容器中作为一个 Bean 。

```java
@Component
public class Person {
    
}
```

相当于 xml 中的：

```xml
<bean class="com.linkedbear.spring.basic_dl.a_quickstart_byname.bean.Person"/>
```

如果想指定 Bean 的名称，可以直接在 `@Component` 中声明 **value** 属性即可：

```java
@Component("aaa")
public class Person { }
```

如果不指定 Bean 的名称，它的默认规则是 **“类名的首字母小写”**（例如 `Person` 的默认名称是 `person` ，`DepartmentServiceImpl` 的默认名称是 `departmentServiceImpl` ）。

### 2.2 组件扫描

只声明了组件，咱在写配置类时如果还是只写 `@Configuration` 注解，随后启动 IOC 容器，那它是感知不到有 `@Component` 存在的，一定会报 `NoSuchBeanDefinitionException` 。

为了解决这个问题，咱需要引入一个新的注解：`@ComponentScan` 。

#### 2.2.1 @ComponentScan

在配置类上额外标注一个 `@ComponentScan` ，并指定要扫描的路径，它就可以**扫描指定路径包及子包下的所有 `@Component` 组件**：

```java
@Configuration
@ComponentScan("com.linkedbear.spring.annotation.c_scan.bean")
public class ComponentScanConfiguration {
    
}
```

如果不指定扫描路径，则**默认扫描本类所在包及子包下的所有 `@Component` 组件**。

注意一点，如果 SpringFramework 的版本比较老，可能会看到这样的写法：

```java
@ComponentScan(basePackages = "com.linkedbear.spring.annotation.c_scan.bean")
```

这两个属性实质上是一样的，写哪个都可以。

另外注意 `basePackages` 是复数，它可以声明多个扫描包。

声明上 `@ComponentScan` 之后，重新启动配置类，可以发现 `Person` 已经成功被注册。

#### 2.2.2 不使用@ComponentScan的组件扫描

其实，如果不写 `@ComponentScan` ，也是可以做到组件扫描的。在 `AnnotationConfigApplicationContext` 的构造方法中有一个类型为 String 可变参数的构造方法：

```java
ApplicationContext ctx = new AnnotationConfigApplicationContext("com.linkedbear.spring.annotation.c_scan.bean");
```

这样声明好要扫描的包，也是可以直接扫描到那些标注了 `@Component` 的 Bean 的。

#### 2.2.3 xml中启用组件扫描

组件扫描可不是注解驱动 IOC 的专利，对于 xml 驱动的 IOC 同样可以启用组件扫描，它只需要在 xml 中声明一个标签即可：

```xml
<context:component-scan base-package="com.linkedbear.spring.annotation.c_scan.bean"/>
<!-- 注意标签是package，不是packages，代表一个标签只能声明一个根包 -->
```

之后使用 `ClassPathXmlApplicationContext` 驱动，也是可以获取到 `Person` 的。

### 2.3 组件注册的其他注解

SpringFramework 为了迎合咱在进行 Web 开发时的三层架构，它额外提供了三个注解：`@Controller` 、`@Service` 、`@Repository` ，分别代表表现层、业务层、持久层。这三个注解的作用与 `@Component` 完全一致，其实它们的底层也就是 `@Component` ：

```java
@Target({ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Component
public @interface Controller { ... }
```

有了这几个注解，那么在进行符合三层架构的开发时，对于那些 ServiceImpl ，就可以直接标注 `@Service` 注解，而不用一个一个的写 `<bean>` 标签或者 `@Bean` 注解了。

> 多提一嘴，其实 `@Repository` 是 SpringFramework 2.0 就已经有了的，只是到了 SpringFramework 3.0 才开始全面支持注解驱动开发。

### 2.4 @Configuration也是@Component

如果上面指定的扫描包中，去掉后面的 bean ，让它扫描整个根包，咱修改一下启动类：

```java
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new AnnotationConfigApplicationContext(ComponentScanConfiguration.class);
        //或者直接扫描com.linkedbear.spring.annotation.c_scan包
        String[] beanNames = ctx.getBeanDefinitionNames();
        Stream.of(beanNames).forEach(System.out::println);
    }
```

运行 `main` 方法，会发现配置类 `ComponentScanConfiguration` 也被注册到 IOC 容器了：（上面的一大堆东西咱不关心，只看最后 3 行）

```
org.springframework.context.annotation.internalConfigurationAnnotationProcessor
org.springframework.context.annotation.internalAutowiredAnnotationProcessor
org.springframework.context.annotation.internalCommonAnnotationProcessor
org.springframework.context.event.internalEventListenerProcessor
org.springframework.context.event.internalEventListenerFactory
componentScanConfiguration
cat
person
```

可能会有小伙伴疑惑了，配置类不应该像配置文件那样，它只是做一个配置而已吗？咱看一眼 `@Configuration` 注解：

```java
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Component
public @interface Configuration { ... }
```

好吧，它也标注了 `@Component` 注解，证明确实它也会被视为 bean ，注册到 IOC 容器。

## 3. 注解驱动与xml驱动互通【掌握】

如果一个应用中，既有注解配置，又有 xml 配置，这个时候就需要由一方引入另一方了。两种方式咱都介绍一下。

### 3.1 xml引入注解

在 xml 中要引入注解配置，需要开启注解配置，同时注册对应的配置类：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd 
        http://www.springframework.org/schema/context 
        https://www.springframework.org/schema/context/spring-context.xsd">

    <!-- 开启注解配置 -->
    <context:annotation-config />
    <bean class="com.linkedbear.spring.annotation.d_importxml.config.AnnotationConfigConfiguration"/>
</beans>
```

### 3.2 注解引入xml

在注解配置中引入 xml ，需要在配置类上标注 `@ImportResource` 注解，并声明配置文件的路径：

```java
@Configuration
@ImportResource("classpath:annotation/beans.xml")
public class ImportXmlAnnotationConfiguration {
    
}
```

具体的组件注册，可自由发挥，小册不再展开演示。

## 小结与练习

1. 注解驱动的 IOC 容器与 xml 驱动的 IOC 容器有什么不同？
2. 动手练习上面提到的几个演示案例，并尝试混用两种 IOC 容器的实现，加深对 IOC 容器的认识。

【了解了注解驱动 IOC 之后，下面咱要对依赖注入进行比较深入的研究了，这部分内容比较多，咱拆成 3 章讲解】

# 8. IOC基础-依赖注入-属性注入&SpEL表达式

由于依赖注入的内容比较多，咱把依赖注入拆分成 3 章来学习。

依赖注入的部分，咱会分述 xml 方式与注解方式两种情况来学习，力求让小伙伴都完全掌握。

## 1. setter属性注入【掌握】

论依赖注入哪个最简单，那当属 “ setter 注入” 。下面咱来介绍最简单的 Bean 的 setter 注入。

> 本小节源码位置：`com.linkedbear.spring.basic_di.a_quickstart_set`

### 1.1 xml方式的setter注入

在最开始的入门阶段，其实咱就已经学过基于 xml 的 setter 注入了，简单回顾一下吧：

```xml
<bean id="person" class="com.linkedbear.spring.basic_di.a_quickstart_set.bean.Person">
    <property name="name" value="test-person-byset"/>
    <property name="age" value="18"/>
</bean>
```

### 1.2 注解方式的setter注入

注解形式的 setter 注入，咱之前学过的是在 bean 的创建时，编程式设置属性：

```java
@Bean
public Person person() {
    Person person = new Person();
    person.setName("test-person-anno-byset");
    person.setAge(18);
    return person;
}
```

## 2. 构造器注入【掌握】

有一些 bean 的属性依赖，需要在调用构造器（构造方法）时就设置好；或者另一种情况，有一些 bean 本身没有无参构造器，这个时候就必须使用**构造器注入**了。

> 本小节源码位置：`com.linkedbear.spring.basic_di.b_constructor`

### 2.1 修改Bean

为了演示构造器注入，需要给 `Person` 添加一个全参数构造方法：

```java
public Person(String name, Integer age) {
    this.name = name;
    this.age = age;
}
```

加上这个构造方法后，默认的无参构造方法就没了，这样原来的 `<bean>` 标签创建时就会失效，提示没有默认的构造方法：

```
Caused by: java.lang.NoSuchMethodException: com.linkedbear.spring.basic_di.b_constructor.bean.Person.<init>()
```

为此，咱需要学习新的 bean 构造和属性注入方法。

### 2.2 xml方式的构造器注入

在 `<bean>` 标签的内部，可以声明一个子标签：`constructor-arg` ，顾名思义，它是指构造器参数，由它可以指定构造器中的属性，来进行属性注入。`constructor-arg` 标签的编写规则如下：

```xml
<bean id="person" class="com.linkedbear.spring.basic_di.b_constructor.bean.Person">
    <constructor-arg index="0" value="test-person-byconstructor"/>
    <constructor-arg index="1" value="18"/>
</bean>
```

一个标签中有两部分，分别指定构造器的参数索引和参数值。这个地方真的能体现出 IDEA 的强大，如果没有在 `<bean>` 标签中声明 `constructor-arg` ，它会直接报红并提示帮你生成：

![img](《从0开始深入学习Spring》/b92592e4241f480688f7ac7ab07da281~tplv-k3u1fbpfcp-zoom-1.image)

由此，可以对这些属性进行注入。

### 2.3 注解式构造器属性注入

注解驱动的 bean 注册中，也是直接使用编程式赋值即可：

```java
@Bean
public Person person() {
    return new Person("test-person-anno-byconstructor", 18);
}
```

## 3. 注解式属性注入【掌握】

看到这里，是不是突然有点迷？哎，上面不是都介绍了注解式的 setter 和构造器的注入了吗？为什么又突然开了一节介绍呢？

回想一下，注册 bean 的方式不仅有 `@Bean` 的方式，还有组件扫描呢！那些声明式注册好的组件，它们的属性怎么处理呢？所以这一节咱就专门拿出来介绍这部分，如果这部分出现了一些新的内容，咱也同样在 xml 的方式下演示。

> 本小节源码位置：`com.linkedbear.spring.basic_di.c_value_spel`

### 3.1 @Component下的属性注入

咱这次不拿动物举例子了（才疏学浅啦 ~ 搞不了那么多动物的啦），换点颜色玩玩（给你们点颜色康康）。先介绍最简单的属性注入方式：**`@Value`** 。

新建一个 `Black` 类，并声明 `name` 和 `order` ，不过这次咱不设置 setter 方法了：

```java
public class Black {
    private String name;
    private Integer order;
    
    @Override
    public String toString() {
        return "Black{" + "name='" + name + '\'' + ", order=" + order + '}';
    }
}
```

实现注解式属性注入，可以直接在要注入的字段上标注 **`@Value`** 注解：

```java
    @Value("black-value-anno")
    private String name;
    
    @Value("0")
    private Integer order;
```

随后，咱使用组件扫描的形式，将这个 `Black` 类扫描到 IOC 容器，并取出打印：

```java
public class InjectValueAnnoApplication {
    
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new AnnotationConfigApplicationContext("com.linkedbear.spring.basic_di.c_value_spel.bean");
        Black black = ctx.getBean(Black.class);
        System.out.println("simple value : " + black);
    }
}
```

运行 `main` 方法，发现 `Black` 的属性已经注入进去了：

```
simple value : Black{name='black-value-anno', order=0}
```

### 3.2 外部配置文件引入-@PropertySource

不是讲属性注入吗？怎么又扯到外部配置文件了？回想一下咱一开始学 IOC 思想的时候，咱不是搞了一个 properties 文件嘛，如果咱需要在 SpringFramework 中使用的话，应该怎么办呢？还是像之前那样用 Properties 类去 IO 读取？SpringFramework 自然能想到这个需求，于是就又扩展出了一个注解，用于导入外部的配置文件：`@PropertySource` 。

#### 3.2.1 创建Bean+配置文件

新建一个 `Red` 类，结构与 `Black` 完全一致。

之后在工程的 resources 目录下新建一个 `red.properties` ，用于存放 `Red` 的属性的配置：

```properties
red.name=red-value-byproperties
red.order=1
```

#### 3.2.2 引入配置文件

使用时，只需要将 **`@PropertySource`** 注解标注在配置类上，并声明 properties 文件的位置，即可导入外部的配置文件：

```java
@Configuration
// 顺便加上包扫描
@ComponentScan("com.linkedbear.spring.basic_di.c_value_spel.bean")
@PropertySource("classpath:basic_di/value/red.properties")
public class InjectValueConfiguration {
    
}
```

#### 3.2.3 Red类的属性注入

对于 properties 类型的属性，`@Value` 需要配合**占位符**来表示注入的属性，我先写，写完你一下子就明白了：

```java
    @Value("${red.name}")
    private String name;
    
    @Value("${red.order}")
    private Integer order;
```

是不是突然熟悉！这不跟 jsp 里的 el 表达式一个样吗？哎没错，还真就这样！

#### 3.2.4 测试启动类

修改启动类，将包扫描启动改为配置类启动，随后将 `Red` 取出：

```java
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new AnnotationConfigApplicationContext(InjectValueConfiguration.class);
        Red red = ctx.getBean(Red.class);
        System.out.println("properties value : " + red);
    }
```

运行 `main` 方法，控制台打印 `Red` 的信息，证明配置文件的属性已经成功注入：

```
properties value : Red{name='red-value-byproperties', order=1}
```

#### 3.2.5 xml中使用占位符

对于 xml 中，占位符的使用方式与 `@Value` 是一模一样的：

```xml
<bean class="com.linkedbear.spring.basic_di.c_value_spel.bean.Red">
    <property name="name" value="${red.name}"/>
    <property name="order" value="${red.order}"/>
</bean>
```

#### 3.2.6 占位符的取值范围【理解】

作为一个 **properties 文件**，它加载到 SpringFramework 的 IOC 容器后，**会转换成 Map 的形式来保存**这些配置，而 SpringFramework 中本身在初始化时就有一些配置项，这些配置项也都放在这个 Map 中。**占位符的取值就是从这些配置项中取**。

> 多提一嘴，实际上这些配置属性和值存放的真实位置是一个叫 **`Environment`** 的抽象中，在后面的 IOC 进阶和高级部分，小册会拿出专门开篇幅讲解 `Environment` 的设计，以及 properties 文件的加载。

### 3.3 SpEL表达式【了解会用】

不是在讲属性注入吗？怎么突然提到 SpEL 了？试想一下，如果咱要在属性注入时，使用一些特殊的数值（如一个 Bean 需要依赖另一个 Bean 的某个属性，或者需要动态处理一个特定的属性值），这种情况 **${}** 的占位符方式就办不了了（占位符只能取配置项），需要一种更强大的表达方式来满足这种需求，这种表达方式就是 SpEL 表达式。

#### 3.3.1 快速了解SpEL

SpEL 全称 Spring Expression Language ，它从 SpringFramework 3.0 开始被支持，它本身可以算 SpringFramework 的组成部分，但又可以被独立使用。它可以支持调用属性值、属性参数以及方法调用、数组存储、逻辑计算等功能。

> 如果有接触过 Struts2 / FreeMarker 的小伙伴应该知道 OGNL ，它也是一种表达式语言，只不过 OGNL 是一个单独的开源项目，而 SpEL 是由 Spring 推出的表达式语言，而且 SpEL 默认本身内嵌在 SpringFramework 中。

#### 3.3.2 SpEL属性注入

下面咱使用 SpEL进行最简单的属性注入。SpEL 的语法统一用 **`#{}`** 表示，花括号内部编写表达式语言。

创建一个 `Blue` ，也是像上面一样声明 name 和 order ，并提供 getter 、setter 方法（为了方便后续操作）和 `toString()` 方法，最后用 `@Component` 标注。

使用 `@Value` 配合 SpEL 完成字面量的属性注入，需要额外在花括号内部加单引号：

```java
@Component
public class Blue {
    
    @Value("#{'blue-value-byspel'}")
    private String name;
    
    @Value("#{2}")
    private Integer order;
```

修改启动类，从 IOC 容器中取 `Blue` 并打印，可以发现字面量被成功注入：

```
Blue{name='blue-value-byspel', order=2}
```

#### 3.3.3 Bean属性引用

如果 SpEL 的功能仅仅是这样，那真的太弱鸡了，SpEL 可以取 IOC 容器中其它 Bean 的属性，下面咱来演示。

上面的注入中咱已经注册了 `Blue` ，下面咱再创建一个 `Green` ，以同样的方式对字段和方法进行声明，同时标注 `@Component` 注解。

在 name 属性上，咱希望直接拿 `Blue` 的 name 贴过来；order 属性希望它比 blue 的 order 大 1，则可以这样编写：

```java
@Component
public class Green {
    
    @Value("#{'copy of ' + blue.name}")
    private String name;
    
    @Value("#{blue.order + 1}")
    private Integer order;
```

修改启动类，测试运行，发现 `Blue` 的属性已经成功被取出了：

```
use spel bean property : Green{name='copy of blue-value-byspel', order=3}
```

xml 的使用方式也很简单：

```xml
<bean class="com.linkedbear.spring.basic_di.c_value_spel.bean.Green">
    <property name="name" value="#{'copy of ' + blue.name}"/>
    <property name="order" value="#{blue.order + 1}"/>
</bean>
```

#### 3.3.4 方法调用

SpEL 表达式不仅可以引用对象的属性，还可以直接引用类常量，以及调用对象的方法等，下面咱演示方法调用和常量引入。

新建一个 `White` ，以同样的方式初始化属性、`toString()` 、注解。

咱设想一个简单的需求，让 name 取 blue 属性的前 3 个字符，order 取 `Integer` 的最大值，则使用 SpEL 可以这样写：

```java
@Component
public class White {
    
    @Value("#{blue.name.substring(0, 3)}")
    private String name;
    
    @Value("#{T(java.lang.Integer).MAX_VALUE}")
    private Integer order;
```

注意，直接引用类的属性，需要在类的全限定名外面使用 **T()** 包围。

修改启动类，测试运行，发现 `White` 的属性已经是处理之后的值了：

```
use spel methods : White{name='blu', order=2147483647}
```

xml 的方式，同样都是使用 value 属性：

```xml
<bean class="com.linkedbear.spring.basic_di.c_value_spel.bean.White">
    <property name="name" value="#{blue.name.substring(0, 3)}"/>
    <property name="order" value="#{T(java.lang.Integer).MAX_VALUE}"/>
</bean>
```

小伙伴不要把过多的精力放到 SpEL 表达式上，简单学会一些基础的使用即可，更多的 SpEL 表达式使用方式，可以参照官方文档，这上面写的非常全：[docs.spring.io/spring/docs…](https://docs.spring.io/spring/docs/5.2.x/spring-framework-reference/core.html#expressions) 。

## 小结与练习

1. 动手练习上面讲解的几个演示案例，熟练掌握这几种基础的属性注入方式。

【最简单的学完了，下面咱来学习如何注入复杂类型的数据，以及 Bean 的依赖如何使用注解处理】

# 9. IOC基础-依赖注入-自动注入&复杂类型注入

上一章咱对最简单基础的属性注入有了比较全面的了解和学习，这一章咱要考虑另外一个问题了：一个 Bean 要依赖另一个 Bean 怎么办？在 xml 中可以声明 ref 属性，用注解怎么办？如果 Bean 里要注入复杂类型（数组、集合、Map 等）又需要怎么办呢？

## 1. 自动注入【掌握】

xml 中的 `ref` 属性可以在一个 Bean 中注入另一个 Bean ，注解同样也可以这样做，它可以使用的注解有很多种，咱一一来学习。

> 本小节源码位置均在 `com.linkedbear.spring.basic_di`

### 1.1 @Autowired

在 Bean 中直接在 **属性 / setter 方法** 上标注 `@Autowired` 注解，IOC 容器会**按照属性对应的类型，从容器中找对应类型的 Bean 赋值到对应的属性**上，实现自动注入。

咱来编写一个案例，以下部分均放在 `d_complexfield` 包下。

#### 1.1.1 创建Bean

预先创建好几个 Bean ，用来过会做演示用。

`Person` ：

```java
@Component
public class Person {
    private String name = "administrator";
    // setter
```

`Dog` ：

```java
@Component
public class Dog {
    
    @Value("dogdog")
    private String name;
    
    private Person person;
    // toString() ......
```

#### 1.1.2 给Dog注入Person的三种方式

对于 `@Autowired` 的使用，只需要在属性上标注即可：

```java
@Component
public class Dog {
    // ......
    @Autowired
    private Person person;
```

也可以使用构造器注入方式：

```java
@Component
public class Dog {
    // ......
    private Person person;
    
    @Autowired
    public Dog(Person person) {
        this.person = person;
    }
```

亦可以使用 setter 方法注入：

```java
@Component
public class Dog {
    // ......
    private Person person;
    
    @Autowired
    public void setPerson(Person person) {
        this.person = person;
    }
```

> 至于这三种方式的区别，下面会有专门的面试题整理，咱先往下学。

#### 1.1.3 测试启动类

编写启动类，把上面的 `Person` 和 `Dog` 都扫描进 IOC 容器，之后取出 `Dog` 并打印：

```java
public class InjectComplexFieldAnnoApplication {
    
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new AnnotationConfigApplicationContext("com.linkedbear.spring.basic_di.d_complexfield.bean");
        Dog dog = ctx.getBean(Dog.class);
        System.out.println(dog);
    }
}
```

运行，打印 `Dog` ，发现 `Dog` 里已经依赖了 `Person` ：

```
Dog{name='dogdog', person=Person{name='administrator'}}
```

#### 1.1.4 注入的Bean不存在

将 `Person` 上面的 `@Component` 暂时的注释掉，此时 IOC 容器中应该没有 `Person` 了吧，再次运行启动类，可以发现

```
Caused by: org.springframework.beans.factory.NoSuchBeanDefinitionException: No qualifying bean of type 'com.linkedbear.spring.basic_di.d_autowired.bean.Person' available: expected at least 1 bean which qualifies as autowire candidate. Dependency annotations: {}
```

简单概括这个异常，就是说**本来想找一个类型为 `Person` 的 Bean ，但一个也没找到**！那必然没找到啊，`@Component` 注解被注释掉了，自然就不会注册了。如果出现这种情况下又不想让程序抛异常，就需要在 `@Autowired` 注解上加一个属性：**`required = false`** 。

```java
    @Autowired(required = false)
    private Person person;
```

再次运行启动类，可以发现控制台打印 `person=null` ，但没有抛出异常：

```
Dog{name='dogdog', person=null}
```

### 1.2 @Autowired在配置类的使用

`@Autowired` 不仅可以用在普通 Bean 的属性上，在配置类中，注册 `@Bean` 时也可以标注：

```java
@Configuration
@ComponentScan("com.linkedbear.spring.basic_di.d_complexfield.bean")
public class InjectComplexFieldConfiguration {

    @Bean
    @Autowired // 高版本可不标注
    public Cat cat(Person person) {
        Cat cat = new Cat();
        cat.setName("mimi");
        cat.setPerson(person);
        return cat;
    }
}
```

由于配置类的上下文中没有 `Person` 的注册了（使用了 `@Component` 模式注解），自然也就没有 `person()` 方法给咱调，那就可以使用 `@Autowired` 注解来进行自动注入了。（其实不用标，SpringFramework 也知道自己得注入了）

将扫描包换为配置类驱动，可以发现 cat 也能打印出来了：

```java
public static void main(String[] args) throws Exception {
    ApplicationContext ctx = new AnnotationConfigApplicationContext(InjectComplexFieldConfiguration.class);

    Cat cat = ctx.getBean(Cat.class);
    System.out.println(cat);
}
```

### 1.3 多个相同类型Bean的自动注入

刚才咱已经使用 `@Component` 模式注解，在 `Person` 类上标注过了，此时 IOC 容器就应该有一个 `Person` 类型的 Bean 了。下面咱在配置类中再注册一个 ：

```java
    @Bean
    public Person master() {
        Person master = new Person();
        master.setName("master");
        return master;
    }
```

这样 IOC 容器就应该有两个 `Person` 对象了吧！接下来咱改一个地方，给 `Person` 的 `@Component` 加一个名称：

```java
@Component("administrator")
```

此时，两个 person 一个叫 master ，一个叫 administrator 。

下面咱直接运行测试启动类，可以发现控制台会报这样一个错误：

```
Caused by: org.springframework.beans.factory.NoUniqueBeanDefinitionException: No qualifying bean of type 'com.linkedbear.spring.basic_di.d_complexfield.bean.Person' available: expected single matching bean but found 2: administrator,master
```

IOC 容器发现有两个类型相同的 `Person` ，它也不知道注入哪一个了，索性直接 “我选择死亡” ，就挂了。

出现这个问题不能就这样不管啊，得先办法啊。SpringFramework 针对这种情况专门提供了两个注解，可以使用两种方式解决该问题。

#### 1.3.1 @Qualifier：指定注入Bean的名称

`@Qualifier` 注解的使用目标是要注入的 Bean ，它配合 `@Autowired` 使用，可以显式的指定要注入哪一个 Bean ：

```java
    @Autowired
    @Qualifier("administrator")
    private Person person;
```

重新运行测试类，可以发现 `Dog` 中注入的 `Person` 是 administrator 。

#### 1.3.2 @Primary：默认Bean

`@Primary` 注解的使用目标是被注入的 Bean ，在一个应用中，一个类型的 Bean 注册只能有一个，它配合 `@Bean` 使用，可以指定默认注入的 Bean ：

```java
    @Bean
    @Primary
    public Person master() {
        Person master = new Person();
        master.setName("master");
        return master;
    }
```

重新运行测试类，发现 `Cat` 中注入的 `Person` 是 master ，`Dog` 中注入的还是 administrator ，可见 `@Qualifier` 不受 `@Primary` 的干扰。

同样的，在 xml 中可以指定 `<bean>` 标签中的 `primary` 属性为 true ，跟上面标注 `@Primary` 注解是一样的。

#### 1.3.3 另外的办法

其实，如果不用上面的注解，也是可以解决问题的，只需要改一下变量名即可：

```java
    @Autowired
    private Person administrator;
```

重新运行测试类，发现可以注入了，而且没有报 `expected single matching bean but found 2` 的异常。

#### 1.3.4 【面试题】@Autowired注入的原理逻辑

由此可以总结出 `@Autowired` 的注入逻辑：（以下答案仅供参考，可根据自己的理解调整回答内容）

**先拿属性对应的类型，去 IOC 容器中找 Bean ，如果找到了一个，直接返回；如果找到多个类型一样的 Bean ， 把属性名拿过去，跟这些 Bean 的 id 逐个对比，如果有一个相同的，直接返回；如果没有任何相同的 id 与要注入的属性名相同，则会抛出 `NoUniqueBeanDefinitionException` 异常。**

### 1.4 多个相同类型Bean的全部注入

上面都是注入一个 Bean 的方式，通过两种不同的办法来保证注入的唯一性。但如果需要一下子把所有指定类型的 Bean 都注入进去应该怎么办呢？其实答案也挺简单的，**注入一个用单个对象接收，注入一组对象就用集合来接收**：

```java
@Component
public class Dog {
    // ......
    
    @Autowired
    private List<Person> persons;
```

如上就可以实现一次性把所有的 `Person` 都注入进来，重新运行启动类，可以发现 persons 中有两个对象：

```
Dog{name='dogdog', person=Person{name='administrator'}, persons=[Person{name='administrator'}, Person{name='master'}]}
```

以上就是关于 `@Autowired` 的使用，下面咱再介绍两个用于自动注入的规范。

### 1.5 JSR250-@Resource

介绍 JSR250 规范之前，先简单了解下 JSR 。

> JSR 全程 **Java Specification Requests** ，它定义了很多 Java 语言开发的规范，有专门的一个组织叫 JCP ( Java Community Process ) 来参与定制。
>
> 有关 JSR250 规范的说明文档可参考官方文档：[jcp.org/en/jsr/deta…](https://jcp.org/en/jsr/detail?id=250)

回到正题，`@Resource` 也是用来属性注入的注解，它与 `@Autowired` 的不同之处在于：**`@Autowired` 是按照类型注入，`@Resource` 是直接按照属性名 / Bean的名称注入**。

是不是突然有点狂喜，这个 **`@Resource` 注解相当于标注 `@Autowired` 和 `@Qualifier`** 了！实际开发中，`@Resource` 注解也是用的很多的，可以根据情况来进行选择。

为了不与上面的代码起冲突，咱另创建一个 `Bird` ，也注入 `Person` ，不过这次咱直接用 `@Resource` 注解指定要注入的 Person ：

```java
@Component
public class Bird {
    
    @Resource(name = "master")
    private Person person;
```

之后在启动类中取出 `Bird` 并打印，可以发现确实正常注入了 name 为 "master" 的 `Person` 。

```
Bird{person=Person{name='master'}}
```

### 1.6 JSR330-@Inject

JSR330 也提出了跟 `@Autowired` 一样的策略，它也是**按照类型注入**。不过想要用 JSR330 的规范，需要额外导入一个依赖：

```xml
<!-- jsr330 -->
<dependency>
    <groupId>javax.inject</groupId>
    <artifactId>javax.inject</artifactId>
    <version>1</version>
</dependency>
```

剩下的使用方式就跟 SpringFramework 原生的 `@Autowired` + `@Qualifier` 一样了：

```java
@Component
public class Cat {
    
    @Inject // 等同于@Autowired
    @Named("admin") // 等同于@Qualifier
    private Person master;
```

#### 1.6.1 @Autowired与@Inject对比

可能会有小伙伴问了，那这个 `@Inject` 都跟 SpringFramework 原生的 `@Autowired` 一个作用，那我还用它干嘛？来看一眼包名：

```
import org.springframework.beans.factory.annotation.Autowired;

import javax.inject.Inject;
```

是不是突然明白了点什么？如果万一项目中没有 SpringFramework 了，那么 `@Autowired` 注解将失效，但 `@Inject` 属于 **JSR 规范，不会因为一个框架失效而失去它的意义**，只要导入其它支持 JSR330 的 IOC 框架，它依然能起作用。

> 当然，话又说回来，当下的 JavaEE 开发，谁又能离得了 Spring 呢？（ヽ(￣▽￣)ﾉ）

------

最后，整理一下上面以及上一章出现的几个大的问题，总结成两道面试题。（面试题答案仅供参考，可根据自己的理解调整回答内容）

### 1.7 【面试题】依赖注入的注入方式

| 注入方式   | 被注入成员是否可变 | 是否依赖IOC框架的API                                         | 使用场景                           |
| ---------- | ------------------ | ------------------------------------------------------------ | ---------------------------------- |
| 构造器注入 | 不可变             | 否（xml、编程式注入不依赖）                                  | 不可变的固定注入                   |
| 参数注入   | 不可变             | 否（高版本中注解配置类中的 `@Bean` 方法参数注入可不标注注解） | 注解配置类中 `@Bean` 方法注册 bean |
| 属性注入   | 不可变             | 是（只能通过标注注解来侵入式注入）                           | 通常用于不可变的固定注入           |
| setter注入 | 可变               | 否（xml、编程式注入不依赖）                                  | 可选属性的注入                     |



### 1.8 【面试题】自动注入的注解对比

| 注解       | 注入方式     | 是否支持@Primary | 来源                       | Bean不存在时处理                   |
| ---------- | ------------ | ---------------- | -------------------------- | ---------------------------------- |
| @Autowired | 根据类型注入 | 是               | SpringFramework原生注解    | 可指定required=false来避免注入失败 |
| @Resource  | 根据名称注入 | 是               | JSR250规范                 | 容器中不存在指定Bean会抛出异常     |
| @Inject    | 根据类型注入 | 是               | JSR330规范 ( 需要导jar包 ) | 容器中不存在指定Bean会抛出异常     |



`@Qualifier` ：如果被标注的成员/方法在根据类型注入时发现有多个相同类型的 Bean ，则会根据该注解声明的 name 寻找特定的 bean

`@Primary` ：如果有多个相同类型的 Bean 同时注册到 IOC 容器中，使用 “根据类型注入” 的注解时会注入标注 `@Primary` 注解的 bean

------

说完了 Bean 的注入，下面咱来看看复杂类型如何注入。

## 2. 复杂类型注入

这部分咱介绍的复杂类型注入包括如下几种：

- 数组
- List / Set
- Map
- Properties

其实看起来也不算复杂嘛。。。基本都是集合类型。。。那咱一个一个介绍。

> 本小节源码位置：`com.linkedbear.spring.basic_di.g_complexfield`

### 2.1 创建复杂对象

咱这次构造一个复杂的 Person ，里面的属性涵盖了上面涉及到的所有类型：

```java
public class Person {

    private String[] names;
    private List<String> tels;
    private Set<Cat> cats;
    private Map<String, Object> events;
    private Properties props;
    // setter
```

下面咱先来使用 xml 的方式注入属性。

### 2.2 xml复杂注入【掌握】

xml 注入复杂类型相对比较简单，咱先在 xml 中注册一个 `Person` （不要扫描 `Person` 所在的包）：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean class="com.linkedbear.spring.basic_di.g_complexfield.bean.Person"></bean>
</beans>
```

接下来，咱把其中的属性都一一赋值。

#### 2.2.1 数组注入

`<bean>` 标签中，要想给属性赋值，统统都是用 `<property>` 标签，对于简单注入和 Bean 的注入，可以通过 **value** 和 **ref** 完成，但复杂类型就必须在标签体内写子标签了。

`<property>` 标签中有好多子标签：

![img](《从0开始深入学习Spring》/d3dc9a25cb1c43e9bb78e5610dd1228e~tplv-k3u1fbpfcp-zoom-1.image)

必然的，注入数组是用 `<array>` 标签咯，于是数组的注入可以这么写：

```xml
<property name="names">
    <array>
        <value>张三</value>
        <value>三三来迟</value>
    </array>
</property>
```

#### 2.2.2 List注入

array 与 list 的形式基本是一模一样的（本身 List 的底层就可以是数组），于是 List 的注入也很简单：

```xml
<property name="tels">
    <list>
        <value>13888</value>
        <value>15999</value>
    </list>
</property>
```

#### 2.2.3 Set注入

有木有小伙伴注意到，在写了 `<array>` 或者 `<list>` 标签后，里面的标签还是上面那一堆，说明集合是可以继续嵌套集合的吧！

在上面的 `Person` 模型中，Set 集合的泛型是 `Cat` ，也就说明咱要在这个集合中注入一组 Bean 。对于这些 Bean ，可以直接声明创建，也可以直接引用现有的 Bean 进行注入，如下所示：

```xml
<!-- 已经提前声明好的Cat -->
<bean id="mimi" class="com.linkedbear.spring.basic_di.g_complexfield.bean.Cat"/>
---

<property name="cats">
    <set>
        <bean class="com.linkedbear.spring.basic_di.g_complexfield.bean.Cat"/>
        <ref bean="mimi"/>
    </set>
</property>
```

#### 2.2.4 Map注入

**Map** 的底层是键值对，迭代的时候都是用 **Entry** 来取 key 和 value ，那在这里面也是这样设计的：（ key 和 value 都可以是 Bean 的引用）

```xml
<property name="events">
    <map>
        <entry key="8:00" value="起床"/>
        <!-- 撸猫 -->
        <entry key="9:00" value-ref="mimi"/>
        <!-- 买猫 -->
        <entry key="14:00">
            <bean class="com.linkedbear.spring.basic_di.g_complexfield.bean.Cat"/>
        </entry>
        <entry key="18:00" value="睡觉"/>
    </map>
</property>
```

#### 2.2.5 Properties注入

Properties 类型与 Map 其实是一模一样的，注入的方式也基本一样，只不过有一点：Properties 的 key 和 value 只能是 String 类型。

```xml
<property name="props">
    <props>
        <prop key="sex">男</prop>
        <prop key="age">18</prop>
    </props>
</property>
```

#### 2.2.6 测试启动类

编写启动类，加载 xml 文件，并取出 `Person` 打印，可以发现属性都被注入成功了：

```
Person{
  names=[张三, 三三来迟],
  tels=[13888, 15999],
  cats=[Cat{name='cat'}, Cat{name='cat'}],
  events={8:00=起床, 9:00=Cat{name='cat'}, 14:00=Cat{name='cat'}, 18:00=睡觉},
  props={age=18, sex=男}
}
```

### 2.3 注解复杂注入【会用】

为了能演示 Bean 的引用，咱给 `Cat` 加上 `@Component` 注解，并带上名称：

```java
@Component("miaomiao")
public class Cat {
    private String name = "cat";
```

下面咱进行注解注入。其实对于注解的注入，说白了还是借助 SpEL 表达式，上一章咱也说了，它的功能很强大，这一节咱继续体会一下。

这部分咱直接全部列出吧，使用 SpEL 表达式实现注解注入的方式：（江郎才尽了已经开始不知道注入什么东西好了 ~ ~ ~ 以下内容开始胡言乱语。。。）

```java
@Component
public class Person2 {
    
    @Value("#{new String[] {'张三', '张仨'}}")
    private String[] names;
    
    @Value("#{{'333333', '3333', '33'}}")
    private List<String> tels;
    
    // 引用现有的Bean，以及创建新的Bean
    @Value("#{{@miaomiao, new com.linkedbear.spring.basic_di.g_complexfield.bean.Cat()}}")
    private Set<Cat> cats;
    
    @Value("#{{'喵喵': @miaomiao.name, '猫猫': new com.linkedbear.spring.basic_di.g_complexfield.bean.Cat().name}}")
    private Map<String, Object> events;
    
    @Value("#{{'123': '牵着手', '456': '抬起头', '789': '我们私奔到月球'}}")
    private Properties props;
```

相应的，也都可以正常打印：

```
Person{
  names=[张三, 张仨],
  tels=[333333, 3333, 33],
  cats=[Cat{name='cat'}, Cat{name='cat'}],
  events={喵喵=miaomiao, 猫猫=cat},
  props={123=牵着手, 456=抬起头, 789=我们私奔到月球}
}
```

> 学是这么学，不过估计没什么人真的会在实际开发中这么肆无忌惮的用 SpEL 注入这种属性吧。。。
>
> 当然，别忘了，还有一种方式能做到复杂类型的注入：编程式。。。直接在配置类中声明 `@Bean` 注册也是可以的，这种方式最灵活。

到这里，复杂类型的注入也就介绍的差不多了。

## 小结与练习

1. 依赖注入的方式有哪几种？分别有什么特点？有什么区别？
2. `@Autowired` 、`@Resource` 、`@Inject` 之间的对比区别是什么？
3. 动手实现组件间的注入，以及复杂类型的注入。

【到这里，依赖注入的大部分内容也就都学完了，最后一部分咱学习两个不是太常用但含量蛮高的方式，作为依赖注入的收尾了】

# 10. IOC进阶-依赖注入-回调注入&延迟注入

对，这一章的难度算是进阶的，倒不是说难不难，只是这部分涉及的内容可能平时开发中用的相对少，做一个了解+会用即可。

## 1. 回调注入【熟悉】

说起这个回调，其实对于大多数情况来讲，已经不需要实现接口了，直接 `@Autowired` 就可以搞定。但这话不是绝对的，这些回调机制还是有用的，咱还是来学一学。

> 本小节源码位置：`com.linkedbear.spring.basic_di.h_aware`

### 1.1 回调的根源：Aware

回调注入的核心是一个叫 **`Aware`** 的接口，它来自 SpringFramework 3.1 ：

```java
public interface Aware {

}
```

它是一个空接口，底下有一系列子接口，借助 IDEA 的继承关系，可以发现还蛮多的：

![img](《从0开始深入学习Spring》/985ddf54f86a42c8a9484310afdaa719~tplv-k3u1fbpfcp-zoom-1.image)

这里面，可能比较常用到的有这么几个，咱单独列出来讲解一下。

### 1.2 比较常用的几个回调接口

| 接口名                         | 用途                                                         |
| ------------------------------ | ------------------------------------------------------------ |
| BeanFactoryAware               | 回调注入 BeanFactory                                         |
| ApplicationContextAware        | 回调注入 ApplicationContext（与上面不同，后续 IOC 高级讲解） |
| EnvironmentAware               | 回调注入 Environment（后续IOC高级讲解）                      |
| ApplicationEventPublisherAware | 回调注入事件发布器                                           |
| ResourceLoaderAware            | 回调注入资源加载器（xml驱动可用）                            |
| BeanClassLoaderAware           | 回调注入加载当前 Bean 的 ClassLoader                         |
| BeanNameAware                  | 回调注入当前 Bean 的名称                                     |



这里面大部分接口，其实在当下的 SpringFramework 5 版本中，借助 `@Autowired` 注解就可以实现注入了，根本不需要这些接口，只有最后面两个，是因 Bean 而异的，还是需要 **Aware** 接口来帮忙注入。下面咱来演示两个接口的作用，剩余的接口小伙伴们可以自行尝试编写体会一下即可。

### 1.3 ApplicationContextAware的使用

#### 1.3.1 创建Bean

新创建一个 `AwaredTestBean` ，用来实现这些 `Aware` 接口。咱先让它实现 `ApplicationContextAware` 接口：

```java
public class AwaredTestBean implements ApplicationContextAware {
    
    private ApplicationContext ctx;
    
    @Override
    public void setApplicationContext(ApplicationContext ctx) throws BeansException {
        this.ctx = ctx;
    }
}
```

这样就相当于，当这个 `AwaredTestBean` 被初始化好的时候，就会把 `ApplicationContext` 传给它，之后它就可以干自己想干的事了。那咱为了测试效果，咱就打印一下 IOC 容器内部的所有 bean 的名称吧：

```java
public class AwaredTestBean implements ApplicationContextAware {
    
    private ApplicationContext ctx;
    
    public void printBeanNames() {
        Stream.of(ctx.getBeanDefinitionNames()).forEach(System.out::println);
    }
    
    @Override
    public void setApplicationContext(ApplicationContext ctx) throws BeansException {
        this.ctx = ctx;
    }
}
```

#### 1.3.2 创建配置类

之后，编写一个配置类，创建这个 `AwaredTestBean` （没有选择直接用包扫描，是为了演示下面的 `BeanNameAware` 接口）：

```java
@Configuration
public class AwareConfiguration {
    
    @Bean
    public AwaredTestBean bbb() {
        return new AwaredTestBean();
    }
}
```

#### 1.3.3 编写启动类

最后，编写测试启动类，并从容器中取出 `AwaredTestBean` ，调用它的 `printBeanNames` 方法：

```java
public class AwareApplication {
    
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new AnnotationConfigApplicationContext(AwareConfiguration.class);
        AwaredTestBean bbb = ctx.getBean(AwaredTestBean.class);
        bbb.printBeanNames();
    }
}
```

运行 `main` 方法，发现容器中的 bean 名称一一被打印，说明 `ApplicationContext` 已经成功注入到 `AwaredTestBean` 中了。

### 1.4 BeanNameAware的使用

如果当前的 bean 需要依赖它本身的 name ，使用 `@Autowired` 就不好使了，这个时候就得使用 `BeanNameAware` 接口来辅助注入当前 bean 的 name 了。

#### 1.4.1 修改bean

给 `AwaredTestBean` 再实现 `BeanNameAware` 接口，并增加 `getName` 方法：

```java
public class AwaredTestBean implements ApplicationContextAware, BeanNameAware {
    
    private String beanName;
    private ApplicationContext ctx;
    
    public String getName() {
        return beanName;
    }
    
    public void printBeanNames() {
        Stream.of(ctx.getBeanDefinitionNames()).forEach(System.out::println);
    }
    
    @Override
    public void setApplicationContext(ApplicationContext ctx) throws BeansException {
        this.ctx = ctx;
    }
    
    @Override
    public void setBeanName(String name) {
        this.beanName = name;
    }
}
```

修改启动类，添加 `getName` 方法的调用并打印：

```java
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new AnnotationConfigApplicationContext(AwareConfiguration.class);
        AwaredTestBean bbb = ctx.getBean(AwaredTestBean.class);
        bbb.printBeanNames();
        System.out.println("-----------");
        System.out.println(bbb.getName());
    }
```

运行 `main` 方法，发现 bbb 已经成功打印出来了，证明 bean 的 name 已经成功注入到 bean 中了。

#### 1.4.2 NamedBean

其实，`BeanNameAware` 还有一个可选的搭配接口：**`NamedBean`** ，它专门提供了一个 `getBeanName` 方法，用于获取 bean 的 name 。

所以说，如果给上面的 `AwaredTestBean` 再实现 `NamedBean` 接口，那就不需要自己定义 `getName` 或者 `getBeanName` 方法，直接实现 `NamedBean` 定义好的 `getBeanName` 方法即可。它的使用方式非常简单，小册就不再演示了。

以上就是对回调注入的简单介绍了，其它的接口小伙伴们可以自行测试。

> 多提一嘴，`@Autowired` 注入 SpringFramework 内置组件并不是在所有场景都适用的，后续 IOC 高级中会解释这个问题。

## 2. 延迟注入【熟悉】

提到延迟注入，是不是就想起来之前学习依赖查找时的延迟查找了呢？还真就这么回事，下面咱再看看 `ObjectProvider` 如何应用于延迟注入。

> 本小节源码位置：`com.linkedbear.spring.basic_di.i_lazyinject`

### 2.1 setter的延迟注入

之前咱在写 setter 注入时，直接在 setter 中标注 `@Autowired` ，并注入对应的 bean 即可。如果使用延迟注入，则注入的就应该换成 `ObjectProvider` ：

```java
@Component
public class Dog {
    
    private Person person;
    
    @Autowired
    public void setPerson(ObjectProvider<Person> person) {
        // 有Bean才取出，注入
        this.person = person.getIfAvailable();
    }
```

如此设计，可以防止 Bean 不存在时出现异常。

### 2.2 构造器的延迟注入

构造器的延迟注入与 setter 方式不要太像：

```java
@Component
public class Dog {
    
    private Person person;
    
    @Autowired
    public Dog(ObjectProvider<Person> person) {
        // 如果没有Bean，则采用缺省策略创建
        this.person = person.getIfAvailable(Person::new);
    }
```

效果跟 setter 是一样的，只不过 setter 的注入时机是创建对象**后**，而构造器的注入时机是创建对象**时**。

### 2.3 属性字段的延迟注入

属性直接注入是不能直接注入 Bean 的，只能注入 `ObjectProvider` ，通常也不会这么干，因为这样注入了之后，每次要用这个 Bean 的时候都得判断一次：

```java
    @Autowired
    private ObjectProvider<Person> person;
    
    @Override
    public String toString() {
        // 每用一次都要getIfAvailable一次
        return "Dog{" + "person=" + person.getIfAvailable(Person::new) + '}';
    }
```

到这里，延迟注入的内容也就介绍的差不多了，关于 `ObjectProvider` 的使用咱在第 6 章也介绍过一些，这里咱就不多重复了。

### 2.4 【面试题】依赖注入的注入方式-扩展

以下答案仅供参考，可根据自己的理解调整回答内容：

| 注入方式   | 被注入成员是否可变 | 是否依赖IOC框架的API               | 注入时机   | 使用场景                 | 支持延迟注入 |
| ---------- | ------------------ | ---------------------------------- | ---------- | ------------------------ | ------------ |
| 构造器注入 | 不可变             | 否（xml、编程式注入不依赖）        | 对象创建时 | 不可变的固定注入         | 是           |
| 参数注入   | 不可变             | 是（只能通过标注注解来侵入式注入） | 对象创建后 | 通常用于不可变的固定注入 | 否           |
| setter注入 | 可变               | 否（xml、编程式注入不依赖）        | 对象创建后 | 可选属性的注入           | 是           |



------

最后，咱对依赖注入作一个面试题级别的总结，帮助小伙伴好好理解依赖注入的思想。

## 3. 【面试题】依赖注入4连问

### 3.1 依赖注入的目的和优点？

首先，依赖注入作为 IOC 的实现方式之一，目的就是**解耦**，我们不再需要直接去 new 那些依赖的类对象（直接依赖会导致对象的创建机制、初始化过程难以统一控制）；而且，如果组件存在多级依赖，依赖注入可以将这些依赖的关系简化，开发者只需要定义好谁依赖谁即可。

除此之外，依赖注入的另一个特点是依赖对象的**可配置**：通过 xml 或者注解声明，可以指定和调整组件注入的对象，借助 Java 的多态特性，可以不需要大批量的修改就完成依赖注入的对象替换（面向接口编程与依赖注入配合近乎完美）。

### 3.2 谁把什么注入给谁了？

由于组件与组件之间的依赖只剩下成员属性 + 依赖注入的注解，而注入的注解又被 SpringFramework 支持，所以这个问题也好回答：**IOC 容器把需要依赖的对象注入给待注入的组件**。

### 3.3 依赖注入具体是如何注入的？

关于 `@Autowired` 注解的注入逻辑，在第 9 章 1.3.4 节有提过；`@Resource` 和 `@Inject` 的注入方式也都在第 9 章的 1.8 节罗列出来了，小伙伴们可以根据表格内容整理，灵活回答即可。

至于里面的注入逻辑，小册不打算在这里详细展开，会放到后续 IOC 原理篇，解析 Bean 的生命周期时详细解释依赖注入的原理。

### 3.4 使用setter注入还是构造器注入？

这个问题，最好的保险回答是引用官方文档，而官方文档在不同的版本推荐的注入方式也不同，具体可参照如下回答：

- SpringFramework **4.0.2** 及之前是推荐 setter 注入，理由是**一个 Bean 有多个依赖时，构造器的参数列表会很长**；而且如果 **Bean 中依赖的属性不都是必需的话，注入会变得更麻烦**；
- **4.0.3** 及以后官方推荐构造器注入，理由是**构造器注入的依赖是不可变的、完全初始化好的，且可以保证不为 null** ；
- 当然 **4.0.3** 及以后的官方文档中也说了，如果**真的出现构造器参数列表过长的情况，可能是这个 Bean 承担的责任太多，应该考虑组件的责任拆解**。

![img](《从0开始深入学习Spring》/189e28f36ac94ad0b3948502df59e365~tplv-k3u1fbpfcp-zoom-1.image)

## 小结与练习

1. 什么是回调注入？回调注入都可以注入什么？
2. 依赖注入如何实现延迟注入？

【到这里，有关依赖注入的部分就算是讲解完毕了。下面的几章，咱会把目标聚焦在 Bean 上，研究 SpringFramework 中对 Bean 的设计和支持】

# 11. IOC基础-Bean常见的几种类型与Bean的作用域

前面的几章，咱对 Bean 的依赖注入有了一个比较全方面的学习，那么对于 IOC 的依赖查找与依赖注入，基本到这里就学完了。接下来的几章，咱会关注 Bean 本身的一些特性，体会 SpringFramework 对于 Bean 的设计。

## 1. Bean的类型【掌握】

在 SpringFramework 中，对于 Bean 的类型，一般有两种设计：**普通 Bean 、工厂 Bean** 。以下分述这两种类型。

> 本小节源码位置：`com.linkedbear.spring.bean.a_type`

### 1.1 普通Bean

其实，在前面好多章，咱创建的 Bean 全都是普通 Bean 。。。比方说这样：

```java
@Component
public class Child {

}
```

或者这样：

```java
@Bean
public Child child() {
    return new Child();
}
```

亦或者这样：

```xml
<bean class="com.linkedbear.spring.bean.a_type.bean.Child"/>
```

### 1.2 FactoryBean

SpringFramework 考虑到一些特殊的设计：Bean 的创建需要指定一些策略，或者依赖特殊的场景来分别创建，也或者一个对象的创建过程太复杂，使用 xml 或者注解声明也比较复杂。这种情况下，如果还是使用普通的创建 Bean 方式，以咱现有的认知就搞不定了。于是，SpringFramework 在一开始就帮我们想了办法，可以借助 **`FactoryBean`** 来使用工厂方法创建对象。

#### 1.2.1 FactoryBean是什么

`FactoryBean` 本身是一个接口，它本身就是一个创建对象的工厂。如果 Bean 实现了 `FactoryBean` 接口，则它本身将不再是一个普通的 Bean ，不会在实际的业务逻辑中起作用，而是由创建的对象来起作用。

`FactoryBean` 接口有三个方法：

```java
public interface FactoryBean<T> {
    // 返回创建的对象
    @Nullable
    T getObject() throws Exception;

    // 返回创建的对象的类型（即泛型类型）
    @Nullable
    Class<?> getObjectType();

    // 创建的对象是单实例Bean还是原型Bean，默认单实例
    default boolean isSingleton() {
        return true;
    }
}
```

#### 1.2.2 FactoryBean的使用

咱构造一个场景：小孩子要买玩具，由一个玩具生产工厂来给这个小孩子造玩具。

##### 1.2.2.1 创建小孩子+玩具

小孩子的类在上面已经创建好了，咱给这里面加一个属性，代表现在想要玩的玩具：

```java
public class Child {
    // 当前的小孩子想玩球
    private String wantToy = "ball";
    
    public String getWantToy() {
        return wantToy;
    }
```

接下来咱创建几个玩具，包括一个抽象类和两个实现类：

```java
public abstract class Toy {
    
    private String name;
    
    public Toy(String name) {
        this.name = name;
    }
public class Ball extends Toy { // 球
    
    public Ball(String name) {
        super(name);
    }
}
public class Car extends Toy { // 玩具汽车
    
    public Car(String name) {
        super(name);
    }
}
```

这样准备工作就算完成了。

##### 1.2.2.2 创建玩具工厂

创建一个 `ToyFactoryBean` ，让它实现 `FactoryBean` 接口：

```java
public class ToyFactoryBean implements FactoryBean<Toy> {
    
    @Override
    public Toy getObject() throws Exception {
        return null;
    }
    
    @Override
    public Class<Toy> getObjectType() {
        return Toy.class;
    }
}
```

咱希望能让它根据小孩子想要玩的玩具来决定生产哪种玩具，那咱就得在这里面注入 `Child` 。由于咱这里面使用的不是注解式自动注入，那咱就用 setter 注入吧：

```java
public class ToyFactoryBean implements FactoryBean<Toy> {
    
    private Child child;
    
    @Override
    public Toy getObject() throws Exception {
        return null;
    }
    
    @Override
    public Class<Toy> getObjectType() {
        return Toy.class;
    }
    
    public void setChild(Child child) {
        this.child = child;
    }
}
```

剩下的就是编写创建逻辑了，咱根据 `Child` 中的 `wantToy` 属性，来决定创建哪个玩具：

```java
    @Override
    public Toy getObject() throws Exception {
        switch (child.getWantToy()) {
            case "ball":
                return new Ball("ball");
            case "car":
                return new Car("car");
            default:
                // SpringFramework2.0开始允许返回null
                // 之前的1.x版本是不允许的
                return null;
        }
    }
```

##### 1.2.2.3 注册工厂类

无论是使用 xml 还是注解的方式，注册这两个 Bean 都是很简单的：

```xml
    <bean id="child" class="com.linkedbear.spring.bean.a_type.bean.Child"/>

    <bean id="toyFactory" class="com.linkedbear.spring.bean.a_type.bean.ToyFactoryBean">
        <property name="child" ref="child"/>
    </bean>
    @Bean
    public Child child() {
        return new Child();
    }
    
    @Bean
    public ToyFactoryBean toyFactory() {
        ToyFactoryBean toyFactory = new ToyFactoryBean();
        toyFactory.setChild(child());
        return toyFactory;
    }
```

##### 1.2.2.4 测试运行

咱用注解驱动的方式，来尝试从 IOC 容器中获取 `Toy` ，看看它是否能创建成功：

```java
public class BeanTypeAnnoApplication {
    
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new AnnotationConfigApplicationContext(BeanTypeConfiguration.class);
        Toy toy = ctx.getBean(Toy.class);
        System.out.println(toy);
    }
}
```

运行 `main` 方法，发现打印的 `Toy` 跟我们预想的一致：

```
Toy{name='ball'}
```

#### 1.2.3 FactoryBean与Bean同时存在

修改配置文件 / 配置类，向 IOC 容器预先的创建一个 `Ball` ，这样 `FactoryBean` 再创建一个，IOC 容器里就会同时存在两个 `Toy` 了：

```java
    @Bean
    public Toy ball() {
        return new Ball("ball");
    }
    
    @Bean
    public ToyFactoryBean toyFactory() {
        ToyFactoryBean toyFactory = new ToyFactoryBean();
        toyFactory.setChild(child());
        return toyFactory;
    }
```

再次运行 `main` 方法，发现控制台抛出了 `NoUniqueBeanDefinitionException` 异常，提示有两个 `Toy` 了，说明 **`FactoryBean` 创建的 Bean 是直接放在 IOC 容器中**了。

咱打印一下 IOC 容器中现有的 `Toy` ：

```java
        Map<String, Toy> toys = ctx.getBeansOfType(Toy.class);
        toys.forEach((name, toy) -> {
            System.out.println("toy name : " + name + ", " + toy.toString());
        });
```

可以发现确实有两个 Bean ：

```
toy name : ball, Toy{name='ball'}
toy name : toyFactory, Toy{name='ball'}
```

#### 1.2.4 FactoryBean创建Bean的时机

咱已经学过了，`ApplicationContext` 初始化 Bean 的时机默认是容器加载时就已经创建，那 `FactoryBean` 创建 Bean 的时机又是什么呢？咱下面来探究这个问题。

##### 1.2.4.1 FactoryBean的加载时机

给 `Toy` 的构造方法中添加一个控制台打印：

```java
    public Toy(String name) {
        System.out.println("生产了一个" + name);
        this.name = name;
    }
```

同时，给 `ToyFactoryBean` 也添加默认构造方法，加一句控制台打印：

```java
public class ToyFactoryBean implements FactoryBean<Toy> {
    
    public ToyFactoryBean() {
        System.out.println("ToyFactoryBean 初始化了。。。");
    }
```

接下来，咱修改 `main` 方法，只初始化 IOC 容器：

```java
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new AnnotationConfigApplicationContext(BeanTypeConfiguration.class);
    }
```

运行，观察控制台的输出：

```
ToyFactoryBean 初始化了。。。
```

只有 `ToyFactoryBean` 被初始化，说明 **`FactoryBean` 本身的加载是伴随 IOC 容器的初始化时机一起的**。

##### 1.2.4.2 创建Bean的时机

与此同时，发现控制台并没有打印生产玩具，说明 `FactoryBean` 中要创建的 Bean 还没有被加载，也就得出：**`FactoryBean` 生产 Bean 的机制是延迟生产**。

修改 `main` 方法，添加 `getBean` 的调用：

```java
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new AnnotationConfigApplicationContext(BeanTypeConfiguration.class);
        Toy toy = ctx.getBean(Toy.class);
    }
```

再次运行 `main` 方法，发现这次生产出了玩具：

```
ToyFactoryBean 初始化了。。。
生产了一个ball
```

#### 1.2.5 FactoryBean创建Bean的实例数

咱上面看到了，`FactoryBean` 接口中有一个默认的方法 `isSingleton` ，默认是 true ，代表默认是单实例的。

修改 `main` 方法，连续取出两次 `Toy` ，并对比内存地址：

```java
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new AnnotationConfigApplicationContext(BeanTypeConfiguration.class);
        Toy toy1 = ctx.getBean(Toy.class);
        Toy toy2 = ctx.getBean(Toy.class);
        System.out.println(toy1 == toy2);
    }
```

运行，发现控制台打印 true ，说明 **`FactoryBean` 默认生成的 Bean 确实是单实例的**。

#### 1.2.6 取出FactoryBean本体

咱刚才一直都是拿 `Toy` 本体去取，取到的都是 `FactoryBean` 生产的 Bean 。一般情况下咱也用不到 `FactoryBean` 本体，但如果真的需要取，使用的方法也很简单：要么直接传 `FactoryBean` 的 class （很容易理解），也可以传 ID 。不过，如果真的靠传 ID 的话，传配置文件 / 配置类声明的 ID 就不好使了，因为那样只会取出生产出来的 Bean ：

```java
System.out.println(ctx.getBean("toyFactory"));
// 输出：Toy{name='ball'}
```

取 `FactoryBean` 的方式，需要在 Bean 的 id 前面加 **“&”** 符号：

```java
System.out.println(ctx.getBean("&toyFactory"));
// 输出：com.linkedbear.spring.bean.a_type.bean.ToyFactoryBean@4df828d7
```

到这里，`FactoryBean` 的使用方法和注意的细节基本都就讲解完毕了。

最后，解答一个可能已经翻腾在小伙伴脑海中的问题：**BeanFactory 与 FactoryBean 的区别是什么？**

#### 1.2.7 【面试题】BeanFactory与FactoryBean的区别

以下答案仅供参考，可根据自己的理解调整回答内容：

`BeanFactory` ：SpringFramework 中实现 IOC 的最底层容器（此处的回答可以从两种角度出发：从类的继承结构上看，它是最顶级的接口，也就是最顶层的容器实现；从类的组合结构上看，它则是最深层次的容器，`ApplicationContext` 在最底层组合了 `BeanFactory` ）

`FactoryBean` ：创建对象的工厂 Bean ，可以使用它来直接创建一些初始化流程比较复杂的对象

------

## 2. Bean的作用域【掌握】

提到作用域，咱先回顾一下这个概念，彻底理解这个概念，对学习 SpringFramework 中 Bean 的作用域很有帮助。

> 本小节源码位置：`com.linkedbear.spring.bean.b_scope`

### 2.1 作用域的概念

回想一下在学习 Java 基础的时候，咱学过一些基础的概念：**成员变量、方法变量、局部变量**。我下边列一段代码，小伙伴们来复习一下每一个变量的作用范围：

```java
public class ScopeReviewDemo {
    // 类级别成员
    private static String classVariable = "";
    
    // 对象级别成员
    private String objectVariable = "";
    
    public static void main(String[] args) throws Exception {
        // 方法级别成员
        String methodVariable = "";
        for (int i = 0; i < args.length; i++) {
            // 循环体局部成员
            String partVariable = args[i];
            
            // 此处能访问哪些变量？
        }
        
        // 此处能访问哪些变量？
    }
    
    public void test() {
        // 此处能访问哪些变量？
    }
    
    public static void staticTest() {
        // 此处能访问哪些变量？
    }
}
```

想必基础扎实的小伙伴很容易就能回答这个问题了吧。上面的四个问题，访问的成员作用域级别依次升高，这也就说明了**不同的作用域，可访问的位置是不一样的**。

那再思考一个问题：为什么会出现多种不同的作用域呢？肯定是它可以被使用的范围不同了。那为什么不都统一成一样的作用范围呢？说白了，**资源是有限的，如果一个资源允许同时被多个地方访问（如全局常量），那就可以把作用域提的很高；反之，如果一个资源伴随着一个时效性强的、带强状态的动作，那这个作用域就应该局限于这一个动作，不能被这个动作之外的干扰。**这段话理解起来可能有点困难，接下来咱配合着 SpringFramework 的作用域来学习，会更容易理解一些。

### 2.2 SpringFramework中内置的作用域

SpringFramework 中内置了 6 种作用域（5.x 版本）：

| 作用域类型  | 概述                                         |
| ----------- | -------------------------------------------- |
| singleton   | 一个 IOC 容器中只有一个【默认值】            |
| prototype   | 每次获取创建一个                             |
| request     | 一次请求创建一个（仅Web应用可用）            |
| session     | 一个会话创建一个（仅Web应用可用）            |
| application | 一个 Web 应用创建一个（仅Web应用可用）       |
| websocket   | 一个 WebSocket 会话创建一个（仅Web应用可用） |



讲真还是比较好理解的吧，下面咱先介绍原生的两种作用域：**singleton** 和 **prototype** 。

### 2.3 singleton：单实例Bean

SpringFramework 官方文档中有一张图，解释了单实例 Bean 的概念：

![img](《从0开始深入学习Spring》/f1a1548eb64b49c797bc0155c43512bc~tplv-k3u1fbpfcp-zoom-1.image)

左边的几个定义的 Bean 同时引用了右边的同一个 `accountDao` ，对于这个 `accountDao` 就是单实例 Bean 。

SpringFramework 中默认所有的 Bean 都是单实例的，即：**一个 IOC 容器中只有一个**。下面咱演示一下单实例 Bean 的效果：

#### 2.3.1 创建Bean+配置类

咱使用注解驱动式演示，先创建 `Child` 和 `Toy` ，本案例演示中 `Toy` 不再是抽象类，直接定义为普通类即可。

```java
public class Child {
    
    private Toy toy;
    
    public void setToy(Toy toy) {
        this.toy = toy;
    }
// Toy 中标注@Component注解
@Component
public class Toy {
    
}
```

接下来创建配置类，同时注册两个 `Child` ，代表现在有两个小孩：

```java
@Configuration
@ComponentScan("com.linkedbear.spring.bean.b_scope.bean")
public class BeanScopeConfiguration {
    
    @Bean
    public Child child1(Toy toy) {
        Child child = new Child();
        child.setToy(toy);
        return child;
    }
    
    @Bean
    public Child child2(Toy toy) {
        Child child = new Child();
        child.setToy(toy);
        return child;
    }
    
}
```

#### 2.3.2 测试运行

编写启动类，驱动 IOC 容器，并获取其中的 `Child` ，打印里面的 `Toy` ：

```java
public class BeanScopeAnnoApplication {
    
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new AnnotationConfigApplicationContext(BeanScopeConfiguration.class);
        ctx.getBeansOfType(Child.class).forEach((name, child) -> {
            System.out.println(name + " : " + child);
        });
    }
    
}
```

运行 `main` 方法，控制台中打印了两个 `Child` 持有同一个 `Toy` ：

```
child1 : Child{toy=com.linkedbear.spring.bean.b_scope.bean.Toy@971d0d8}
child2 : Child{toy=com.linkedbear.spring.bean.b_scope.bean.Toy@971d0d8}
```

说明**默认情况下，Bean 的作用域是单实例的**。

### 2.4 prototype：原型Bean

Spring 官方的定义是：**每次对原型 Bean 提出请求时，都会创建一个新的 Bean 实例。**这里面提到的 ”提出请求“ ，包括任何依赖查找、依赖注入的动作，都算做一次 ”提出请求“ 。由此咱也可以总结一点：如果连续 `getBean()` 两次，那就应该创建两个不同的 Bean 实例；向两个不同的 Bean 中注入两次，也应该注入两个不同的 Bean 实例。SpringFramework 的官方文档中也给出了一张解释原型 Bean 的图：

![img](《从0开始深入学习Spring》/c497ccbeac5e49eba21839c8c2f08a1a~tplv-k3u1fbpfcp-zoom-1.image)

图中的 3 个 `accountDao` 是 3 个不同的对象，由此可以体现出原型 Bean 的意思。

> 其实对于**原型**这个概念，在设计模式中也是有对应的：**原型模式**。原型模式实质上是使用对象深克隆，乍看上去跟 SpringFramework 的原型 Bean 没什么区别，但咱仔细想，每一次生成的原型 Bean 本质上都还是一样的，只是可能带一些特殊的状态等等，这个可能理解起来比较抽象，可以跟下面的 request 域结合着理解。

下面咱也实际测试一下效果，体会原型 Bean 的使用。

#### 2.4.1 修改Bean

给 `Toy` 的类上标注一个额外的注解：`@Scope` ，并声明为原型类型：

```java
@Component
@Scope("prototype")
public class Toy {
    
}
```

注意，这个 **prototype** 不是随便写的常量，而是在 `ConfigurableBeanFactory` 中定义好的常量：

```java
public interface ConfigurableBeanFactory extends HierarchicalBeanFactory, SingletonBeanRegistry {

	String SCOPE_SINGLETON = "singleton";

	String SCOPE_PROTOTYPE = "prototype";
```

如果真的担心打错，建议引用该常量 ￣へ￣ 。。。

#### 2.4.2 测试运行

其他的代码都不需要改变，直接运行 `main` 方法，发现控制台打印的两个 Toy 确实不同：

```
child1 : Child{toy=com.linkedbear.spring.bean.b_scope.bean.Toy@18a70f16}
child2 : Child{toy=com.linkedbear.spring.bean.b_scope.bean.Toy@62e136d3}
```

#### 2.4.3 原型Bean的创建时机

仔细思考一下，单实例 Bean 的创建咱已经知道，是在 `ApplicationContext` 被初始化时就已经创建好了，那这些原型 Bean 又是什么时候被创建的呢？其实也不难想出，它都是什么时候需要，什么时候创建。咱可以给 `Toy` 加一个无参构造方法，打印构造方法被打印了：

```java
@Component
@Scope("prototype")
public class Toy {
    public Toy() {
        System.out.println("Toy constructor run ...");
    }
}
```

修改启动类，只让它扫描 bean 包，不加载配置类，这样就相当于只有一个 Toy 类被扫描进去了，Child 不会注册到 IOC 容器中。

```java
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new AnnotationConfigApplicationContext("com.linkedbear.spring.bean.b_scope.bean");
    }
```

重新运行 `main` 方法，发现控制台什么也没打印，因为没有 `Toy` 的使用需求嘛，它当然不会被创建。

### 2.5 Web应用的作用域们

上面表中还涉及到几个关于 Web 应用的作用域，它们都是在 Web 应用中才会有的，这个咱放到后面介绍 SpringWebMvc 时再介绍，这里只是简单介绍一下。

- request ：请求Bean，每次客户端向 Web 应用服务器发起一次请求，Web 服务器接收到请求后，由 SpringFramework 生成一个 Bean ，直到请求结束
- session ：会话Bean，每个客户端在与 Web 应用服务器发起会话后，SpringFramework 会为之生成一个 Bean ，直到会话过期
- application ：应用Bean，每个 Web 应用在启动时，SpringFramework 会生成一个 Bean ，直到应用停止（有的也叫 global-session ）
- websocket ：WebSocket Bean ，每个客户端在与 Web 应用服务器建立 WebSocket 长连接时，SpringFramework 会为之生成一个 Bean ，直到断开连接

上面 3 种可能小伙伴们还熟悉，最后一种 WebSocket 可能有些小伙伴还不了解，不了解没关系，这玩意用的也少，等回头小伙伴学习了 WebSocket 之后自己试一下就可以了，小册这里也不多展开了。

## 小结与练习

1. `BeanFactory` 与 `FactoryBean` 的区别？
2. `FactoryBean` 创建 Bean 的规则是什么？创建 Bean 的时机是什么？
3. 单实例 Bean 与原型 Bean 的区别都有什么？
4. 练习本节提到的案例，熟练掌握该部分内容。

【了解了 Bean 的类型和作用域，下面咱要学习 Bean 的创建方式了，SpringFramework 中对于 Bean 的创建方式有很多种，下一章咱来学习这部分】

# 12. IOC基础-Bean的实例化方式

SpringFramework 中实例化 Bean 的方法有好多种，这里面还涉及到一个非常经典的设计模式：**工厂模式**。下面咱逐个介绍创建 Bean 的方式。

【为防止概念混淆，小册中提到的所有**实例化指调用构造方法，创建新的对象**，**初始化指创建好新的对象后的属性赋值、组件注入等后续动作**】

> 本小节源码位置：`com.linkedbear.spring.bean.c_instantiate`

## 1. 普通Bean实例化

其实咱前面创建的所有 `<bean>` 标签、`@Bean` 注解的方式，都是普通 Bean 的对象，它们默认是单实例的，在 IOC 容器初始化时就已经被初始化了。咱已经足够熟悉了，不多赘述。

## 2. 借助FactoryBean创建Bean【掌握】

上一章中，咱详细学习了 `FactoryBean` 的使用，并了解了 `FactoryBean` 的一些特性，简单复习一下吧：

### 2.1 普通Bean+FactoryBean

```java
public class Ball {
    
}
public class BallFactoryBean implements FactoryBean<Ball> {
    
    @Override
    public Ball getObject() {
        return new Ball();
    }
    
    @Override
    public Class<Ball> getObjectType() {
        return Ball.class;
    }
}
```

### 2.2 注册Bean

```java
@Bean
public BallFactoryBean ballFactoryBean() {
    return new BallFactoryBean();
}
<bean class="com.linkedbear.spring.bean.c_instantiate.bean.BallFactoryBean"/>
```

注册 Bean 时，只需要注入 `FactoryBean` ，IOC 容器会自动识别，并默认在第一次获取时创建对应的 Bean 并缓存（针对默认的单实例 `FactoryBean` ）。

## 3. 借助静态工厂创建Bean【掌握】

还记得咱最开始学习 IOC 思想的时候，封装的那个静态工厂吗？

```java
public class BeanFactory {
    
    public static DemoService getDemoService() {
        return new DemoServiceImpl();
    }
}
```

它也可以在 SpringFramework 中发挥作用，咱学习一下它的使用方式。

### 3.1 创建Bean+静态工厂

咱创建一个 `Car` ，为了能看见它被创建，咱加一个构造方法：

```java
public class Car {
    
    public Car() {
        System.out.println("Car constructor run ...");
    }
}
```

之后，仿照上面的设计，咱直接写一个 `CarStaticFactory` 类，加上静态方法，返回 `Car` 即可：

```java
public class CarStaticFactory {
    
    public static Car getCar() {
        return new Car();
    }
}
```

### 3.2 配置xml

静态工厂的使用通常运用于 xml 方式比较多（主要是注解驱动没有直接能让它起作用的注解，编程式配置又可以直接调用，显得没那么大必要，下面会演示），咱下面创建一个 `bean-instantiate.xml` 文件，在这里面编写关于静态工厂的使用方法：

```xml
<bean id="car1" class="com.linkedbear.spring.bean.c_instantiate.bean.Car"/>

<bean id="car2" class="com.linkedbear.spring.bean.c_instantiate.bean.CarStaticFactory" factory-method="getCar"/>
```

可以看出来，上面的注册方式是普通的 Bean 注册方式，下面的方式会直接引用静态工厂，并声明要创建对象的工厂方法 `factory-method` 即可。SpringFramework 会依照这个 xml 的方式，解析出规则并调用静态工厂的方法来创建实际的 Bean 对象。

### 3.3 测试运行

编写启动类，读取 xml 配置文件，并直接取出所有的 `Car` 对象：

```java
public class BeanInstantiateXmlApplication {
    
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new ClassPathXmlApplicationContext("bean/bean-instantiate.xml");
        ctx.getBeansOfType(Car.class).forEach((beanName, car) -> {
            System.out.println(beanName + " : " + car);
        });
    }
}
```

运行 `main` 方法，发现控制台上打印了两次 `Car` 的构造方法运行，并且创建了两个 `Car` 对象：

```
Car constructor run ...
Car constructor run ...
car1 : com.linkedbear.spring.bean.c_instantiate.bean.Car@3c0ecd4b
car2 : com.linkedbear.spring.bean.c_instantiate.bean.Car@14bf9759
```

### 3.4 静态工厂本身在工厂吗

既然 car2 也注册到 IOC 容器中了，那静态工厂本身是不是也在 IOC 容器中了呢？咱从 IOC 容器中取一下试试：

```java
    public static void main(String[] args) throws Exception {
        ApplicationContext ctx = new ClassPathXmlApplicationContext("bean/bean-instantiate.xml");
        ctx.getBeansOfType(Car.class).forEach((beanName, car) -> {
            System.out.println(beanName + " : " + car);
        });
        // 尝试取一下试试
        System.out.println(ctx.getBean(CarInstanceFactory.class));
    }
```

运行，发现程序抛出了 `NoSuchBeanDefinitionException` 异常：

```
Exception in thread "main" org.springframework.beans.factory.NoSuchBeanDefinitionException: No qualifying bean of type 'com.linkedbear.spring.bean.c_instantiate.bean.CarStaticFactory' available
```

由此可以得出一个结论：**静态工厂本身不会被注册到 IOC 容器中**。

### 3.5 编程式使用静态工厂

由于 SpringFramework 中并没有提供关于静态工厂相关的注解，所以只能使用注解配置类+编程式使用静态工厂了，而这个使用方式相当的简单：

```java
    @Bean
    public Car car2() {
        return CarStaticFactory.getCar();
    }
```

是不是突然感觉智商被侮辱了？对的，就这么简单，所以才说对于注解驱动的 IOC 这部分没啥可讲的。

## 4. 借助实例工厂创建Bean【掌握】

跟静态工厂类似，SpringFramework 也支持咱用实例工厂来创建 Bean ，下面咱也来体会一下。

### 4.1 创建实例工厂

创建一个 `CarInstanceFactory` 代表实例工厂，它跟静态工厂唯一的区别是方法不再是 **static** 方法了：

```java
public class CarInstanceFactory {
    
    public Car getCar() {
        return new Car();
    }
}
```

### 4.2 配置xml

对于实例工厂，要想调用对象的方法，那自然得先把对象实例化才行了，所以咱就需要先在 xml 中注册实例工厂，随后才能创建真正的目标 Bean ：

```xml
    <bean id="carInstanceFactory" class="com.linkedbear.spring.bean.c_instantiate.bean.CarInstanceFactory"/>
    <bean id="car3" factory-bean="carInstanceFactory" factory-method="getCar"/>
```

可以发现，`<bean>` 标签可以不传入 class 属性，用 `factory-bean` 和 `factory-method` 属性也可以完成 Bean 的创建。

### 4.3 测试运行

去掉 `BeanInstantiateXmlApplication` 的 `main` 方法里面的静态工厂取出，之后运行，可以发现控制台这次打印了三次 `Car` 的构造方法打印：

```
Car constructor run ...
Car constructor run ...
Car constructor run ...
car1 : com.linkedbear.spring.bean.c_instantiate.bean.Car@3c0ecd4b
car2 : com.linkedbear.spring.bean.c_instantiate.bean.Car@14bf9759
car3 : com.linkedbear.spring.bean.c_instantiate.bean.Car@5f341870
```

这个时候再问那个问题：这次实例工厂在 IOC 容器中吗？那肯定不用思考就知道答案是存在了（都 `<bean>` 注册进去了。。。）

### 4.4 编程式使用实例工厂

跟上面的配置类中使用静态工厂一样，实例工厂的使用也是很蹂躏智商了：

```java
    @Bean
    public Car car3(CarInstanceFactory carInstanceFactory) {
        return carInstanceFactory.getCar();
    }
```

也是简单的一批吧，那咱就不多解释了。

以上就是 SpringFramework 中的 Bean 实例化的方式，内容不算多，小伙伴们需多加练习。

## 小结与练习

1. 能熟练驾驭 Bean 的几种实例化方式，并能总结出它们的区别。

【Bean 创建出来之后，下一步还要对它进行初始化，这部分属于 Bean 的生命周期中，下一章咱来学习 Bean 的生命周期相关知识】

# 13. IOC基础-Bean的生命周期-初始化与销毁

Bean 创建出来之后，也就到了咱正常理解的生命周期中的初始化阶段了，整个 Bean 的生命周期也是非常重要的，小伙伴需要好好理解这部分知识。

## 1. 生命周期的意义【掌握】

这个概念可能对于有些小伙伴来讲，理解起来会比较抽象。咱用一张图来解释：

### 1.1 生命周期的阶段

![img](《从0开始深入学习Spring》/4376c21f525e4c11b4fc07148e65e8e0~tplv-k3u1fbpfcp-zoom-1.image)

一个对象从被创建，到被垃圾回收，可以宏观的划分为 5 个阶段：

- **创建 / 实例化阶段**：此时会调用类的构造方法，产生一个新的对象
- **初始化阶段**：此时对象已经创建好，但还没有被正式使用，可能这里面需要做一些额外的操作（如预初始化数据库的连接池）
- **运行使用期**：此时对象已经完全初始化好，程序正常运行，对象被使用
- **销毁阶段**：此时对象准备被销毁，已不再使用，需要预先的把自身占用的资源等处理好（如关闭、释放数据库连接）
- **回收阶段**：此时对象已经完全没有被引用了，被垃圾回收器回收

由此可见，把控好生命周期的步骤，可以在恰当的时机处理一些恰当的逻辑。

### 1.2 SpringFramework能干预的生命周期阶段

仔细观察上面的 5 个阶段，思考一个问题：作为一个框架，它能干预的是哪几个阶段呢？

很明显，只有对象的回收动作不行吧。

那再思考一个问题：我们使用 SpringFramework 来获取 Bean 的前提下，又能干预哪几个阶段呢？

这次 Bean 的创建应该是咱也干预不了了，只剩下**初始化和销毁两个阶段**可以干预了吧。

再思考，SpringFramework 如何能让我们干预 Bean 的初始化和销毁呢？

回想一下 **Servlet** ，`Servlet` 里面有两个方法，分别叫 `init` 和 `destroy` ，咱之前在使用 Servlet 开发时，有自己调过这两个方法吗？肯定没有吧。但是这两个方法有真实的被调用过吗？肯定有吧，不然咋设计出来的呢？这两个方法都是**被 Web 容器（ Tomcat 等）调用的吧，用来初始化和销毁 Servlet 的**。这种方法的设计思想其实就是 “**回调机制**” ，它**都不是自己设计的，而是由父类 / 接口定义好的，由第三者（框架、容器等）来调用**。回调机制跟前面咱学的那些 `Aware` 接口的回调注入，在核心思想上其实是一样的。

理解了生命周期的阶段，以及回调的机制，下面咱就可以来学习 SpringFramework 中提供的初始化和销毁的回调开口了。

> 生命周期的触发，更适合叫回调，因为生命周期方法是咱定义的，但方法被调用，是框架内部帮我们调的，那也就可以称之为 “回调” 了。

## 2. init-method&destroy-method【掌握】

咱先体会一种最容易理解的生命周期阶段：**初始化和销毁方法**。这种控制时机是在 Bean 的初始化和销毁阶段起作用，下面咱来演示这种方式。

> 本小节源码位置：`com.linkedbear.spring.lifecycle.a_initmethod`

### 2.1 创建Bean

为了方便演示 xml 与注解的方式，咱创建两个类分别演示，这样咱搞一个 `Cat` 和一个 `Dog` 。

```java
public class Cat {
    
    private String name;
    
    public void setName(String name) {
        this.name = name;
    }
    
    public void init() {
        System.out.println(name + "被初始化了。。。");
    }
    public void destroy() {
        System.out.println(name + "被销毁了。。。");
    }
}
public class Dog {
    
    private String name;
    
    public void setName(String name) {
        this.name = name;
    }
    
    public void init() {
        System.out.println(name + "被初始化了。。。");
    }
    public void destroy() {
        System.out.println(name + "被销毁了。。。");
    }
}
```

都是再简单不过的模型了吧。

### 2.2 创建配置文件/配置类

#### 2.2.1 xml配置

xml 方式，咱使用 `<bean>` 标签来注册 `Cat` ：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean class="com.linkedbear.spring.lifecycle.a_initmethod.bean.Cat">
        <property name="name" value="mimi"/>
    </bean>
</beans>
```

在 `<bean>` 标签中，有两个属性，就是上面的 `init-method` 和 `destroy-method` ，意义想必也不用多解释了吧：

```xml
    <bean class="com.linkedbear.spring.lifecycle.a_initmethod.bean.Cat"
          init-method="init" destroy-method="destroy">
        <property name="name" value="mimi"/>
    </bean>
```

#### 2.2.2 注解配置

类似于 xml ，`@Bean` 注解中也有类似的属性，只不过 Java 中的属性名不能带短横线，所以就改用驼峰命名咯：

```java
    @Bean(initMethod = "init", destroyMethod = "destroy")
    public Dog dog() {
        Dog dog = new Dog();
        dog.setName("wangwang");
        return dog;
    }
```

#### 2.2.3 初始化销毁方法的要求特征

注意一点，这些配置的初始化和销毁方法必须具有以下特征：（原因一并解释）

- 方法访问权限无限制要求（ SpringFramework 底层会反射调用的）
- 方法**无参数**（如果真的设置了参数，SpringFramework 也不知道传什么进去）
- 方法**无返回值**（返回给 SpringFramework 也没有意义）
- 可以抛出异常（异常不由自己处理，交予 SpringFramework 可以打断 Bean 的初始化 / 销毁步骤）

### 2.3 测试效果

分别初始化 xml 和注解驱动的容器，不过需要注意的是，这次咱接收的类型不再用 `ApplicationContext` ，而是用实现类本身，目的是为了调用 `close` 方法对容器进行关闭，以触发 Bean 的销毁动作。至于为什么实现类会有 `close` 方法，`ApplicationContext` 本身没有，这个咱后面放到 IOC进阶部分讲解。

初始化基于 xml 的容器就很简单了，咱在初始化和关闭的后面都加一句控制台打印：

```java
public class InitMethodXmlApplication {
    
    public static void main(String[] args) throws Exception {
        System.out.println("准备初始化IOC容器。。。");
        ClassPathXmlApplicationContext ctx = new ClassPathXmlApplicationContext("lifecycle/bean-initmethod.xml");
        System.out.println("IOC容器初始化完成。。。");
        
        System.out.println();
        
        System.out.println("准备销毁IOC容器。。。");
        ctx.close();
        System.out.println("IOC容器销毁完成。。。");
    }
}
```

运行 main 方法，控制台会打印如下内容：

```
准备初始化IOC容器。。。
mimi被初始化了。。。
IOC容器初始化完成。。。

准备销毁IOC容器。。。
mimi被销毁了。。。
IOC容器销毁完成。。。
```

由此可以得出结论：**在 IOC 容器初始化之前，默认情况下 Bean 已经创建好了，而且完成了初始化动作；容器调用销毁动作时，先销毁所有 Bean ，最后 IOC 容器全部销毁完成。**

注解驱动效果与 xml 完全一致，小伙伴们可自行测试。

### 2.4 Bean的初始化流程顺序探究

上面的编码中，只能看出来 Bean 在 IOC 容器初始化阶段就创建并初始化好，那每个 Bean 的初始化动作又是如何呢？咱修改一下 Cat ，分别在构造方法和 `setName` 方法中加入控制台打印，这样在触发这些方法时，会在控制台上得以体现：

```java
public class Cat {
    
    private String name;
    
    public Cat() {
        System.out.println("Cat 构造方法执行了。。。");
    }
    
    public void setName(String name) {
        System.out.println("setName方法执行了。。。");
        this.name = name;
    }
```

重新运行启动类的 `main` 方法，控制台会打印如下内容：（省略销毁部分）

```
准备初始化IOC容器。。。
Cat 构造方法执行了。。。
setName方法执行了。。。
mimi被初始化了。。。
IOC容器初始化完成。。。
```

由此可以得出结论：**Bean 的生命周期中，是先对属性赋值，后执行 `init-method` 标记的方法**。

## 3. JSR250规范【掌握】

上面的方法，都是咱手动声明注册的 Bean ，对于那些使用模式注解的 Bean ，这种方式就不好使了，因为**没有可以让你声明 `init-method` 和 `destroy-method` 的地方了，`@Component` 注解上也只有一个 `value` 属性而已**。这个时候咱就需要学习一种新的方式，这种方式专门配合注解式注册 Bean 以完成全注解驱动开发，那就是如标题所说的 **JSR250 规范**。

对，又是它，没写错（ ￣▽￣ ）JSR250 规范中除了有 `@Resource` 这样的自动注入注解，还有负责生命周期的注解，包括 **`@PostConstruct`** 、**`@PreDestroy`** 两个注解，分别对应 `init-method` 和 `destroy-method` 。

下面咱来演示这两个注解的使用，由于是注解驱动，故咱这里只演示注解驱动的方式。

> 本小节源码位置：`com.linkedbear.spring.lifecycle.b_jsr250`

### 3.1 创建Bean

这次咱模拟另一种场景：钢笔与墨水，刚买来的动作代表实例化，加墨水的动作代表初始化，倒掉所有墨水的动作代表销毁，于是这个 `Pen` 可以这样设计：

```java
@Component
public class Pen {
    
    private Integer ink;
    
    public void addInk() {
        this.ink = 100;
    }
    
    public void outwellInk() {
        this.ink = 0;
    }
    
    @Override
    public String toString() {
        return "Pen{" + "ink=" + ink + '}';
    }
}
```

对于 JSR250 规范的这两个注解的使用，直接标注在 Bean 的方法上即可：（顺便加上控制台打印以便观察）

```java
    @PostConstruct
    public void addInk() {
        System.out.println("钢笔中已加满墨水。。。");
        this.ink = 100;
    }
    
    @PreDestroy
    public void outwellInk() {
        System.out.println("钢笔中的墨水都放干净了。。。");
        this.ink = 0;
    }
```

> 被 `@PostConstruct` 和 `@PreDestroy` 注解标注的方法，与 `init-method` / `destroy-method` 方法的声明要求是一样的，访问修饰符也可以是 private 。

### 3.2 测试效果

编写启动类，直接扫描这个 Pen 类：

```java
public class JSR250AnnoApplication {
    
    public static void main(String[] args) throws Exception {
        System.out.println("准备初始化IOC容器。。。");
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                "com.linkedbear.spring.lifecycle.b_jsr250.bean");
        System.out.println("IOC容器初始化完成。。。");
        System.out.println();
        System.out.println("准备销毁IOC容器。。。");
        ctx.close();
        System.out.println("IOC容器销毁完成。。。");
    }
}
```

运行 `main` 方法，控制台中打印如下内容：

```
准备初始化IOC容器。。。
钢笔中已加满墨水。。。
IOC容器初始化完成。。。

准备销毁IOC容器。。。
钢笔中的墨水都放干净了。。。
IOC容器销毁完成。。。
```

可见这两个注解也完成了像 `init-method` 和 `destroy-method` 一样的效果。

### 3.3 JSR250规范与init-method共存

如果不使用 `@Component` 注解来注册 Bean 而转用 `<bean>` / `@Bean` 的方式，那 `@PostConstruct` 与 `@PreDestroy` 注解是可以与 `init-method` / `destroy-method` 共存的，下面咱来演示.

扩展 `Pen` 中的方法：（为了不与之前的代码有影响，复制粘贴一个 `Pen2` ）

```java
    public void open() {
        System.out.println("init-method - 打开钢笔。。。");
    }
    
    public void close() {
        System.out.println("destroy-method - 合上钢笔。。。");
    }
    
    @PostConstruct
    public void addInk() {
        System.out.println("@PostConstruct - 钢笔中已加满墨水。。。");
        this.ink = 100;
    }
    
    @PreDestroy
    public void outwellInk() {
        System.out.println("@PreDestroy - 钢笔中的墨水都放干净了。。。");
        this.ink = 0;
    }
```

之后使用注解式注册这个 `Pen2` ：

```java
@Configuration
public class JSR250Configuration {

    @Bean(initMethod = "open", destroyMethod = "close")
    public Pen2 pen() {
        return new Pen2();
    }
}
```

之后修改启动类，驱动这个配置类，观察控制台的打印：

```
准备初始化IOC容器。。。
@PostConstruct - 钢笔中已加满墨水。。。
init-method - 打开钢笔。。。
IOC容器初始化完成。。。

准备销毁IOC容器。。。
@PreDestroy - 钢笔中的墨水都放干净了。。。
destroy-method - 合上钢笔。。。
IOC容器销毁完成。。。
```

虽然打印的逻辑有点怪怪的，但透过逻辑看执行顺序，可以得出结论：**JSR250 规范的执行优先级高于 init / destroy**。

## 4. InitializingBean&DisposableBean【掌握】

这两个家伙实际上是两个接口，而且是 SpringFramework 内部预先定义好的两个关于生命周期的接口。他们的触发时机与上面的 `init-method` / `destroy-method` 以及 JSR250 规范的两个注解一样，都是在 Bean 的初始化和销毁阶段要回调的。下面咱演示这两个接口的使用。

> 本小节源码位置：`com.linkedbear.spring.lifecycle.c_initializingbean`

### 4.1 创建Bean

咱依然使用 `Pen` 作为演示对象，这次咱让 `Pen` 实现这两个接口：

```java
@Component
public class Pen implements InitializingBean, DisposableBean {
    
    private Integer ink;
    
    @Override
    public void afterPropertiesSet() throws Exception {
        System.out.println("钢笔中已加满墨水。。。");
        this.ink = 100;
    }
    
    @Override
    public void destroy() throws Exception {
        System.out.println("钢笔中的墨水都放干净了。。。");
        this.ink = 0;
    }
    
    @Override
    public String toString() {
        return "Pen{" + "ink=" + ink + '}';
    }
}
```

### 4.2 测试效果

直接使用注解驱动 IOC 容器扫描这个 Pen ，其余编写内容与上面一致：

```java
public class InitializingDisposableAnnoApplication {
    
    public static void main(String[] args) throws Exception {
        System.out.println("准备初始化IOC容器。。。");
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                "com.linkedbear.spring.lifecycle.c_initializingbean.bean");
        System.out.println("IOC容器初始化完成。。。");
        System.out.println();
        System.out.println("准备销毁IOC容器。。。");
        ctx.close();
        System.out.println("IOC容器销毁完成。。。");
    }
}
```

运行 `main` 方法，控制台同样打印了触发生命周期的内容：

```
准备初始化IOC容器。。。
钢笔中已加满墨水。。。
IOC容器初始化完成。。。

准备销毁IOC容器。。。
钢笔中的墨水都放干净了。。。
IOC容器销毁完成。。。
```

### 4.3 三种生命周期并存

与上面一样，咱测试一下，当一个 Bean 同时使用这三种生命周期共同控制时，执行顺序是怎样的。

再复制出一个 `Pen` 来，命名为 `Pen3` ，并同时实现三种生命周期的控制：（三种方式的顺序按照讲解的顺序从上到下排列）

```java
    public void open() {
        System.out.println("init-method - 打开钢笔。。。");
    }
    
    public void close() {
        System.out.println("destroy-method - 合上钢笔。。。");
    }
    
    @PostConstruct
    public void addInk() {
        System.out.println("@PostConstruct - 钢笔中已加满墨水。。。");
        this.ink = 100;
    }
    
    @PreDestroy
    public void outwellInk() {
        System.out.println("@PreDestroy - 钢笔中的墨水都放干净了。。。");
        this.ink = 0;
    }
    
    @Override
    public void afterPropertiesSet() throws Exception {
        System.out.println("InitializingBean - 准备写字。。。");
    }
    
    @Override
    public void destroy() throws Exception {
        System.out.println("DisposableBean - 写完字了。。。");
    }
```

之后使用注解驱动方式注册这个 `Pen3` ：

```java
    @Bean(initMethod = "open", destroyMethod = "close")
    public Pen3 pen() {
        return new Pen3();
    }
```

之后让注解 IOC 容器驱动这个配置类，运行 `main` 方法，观察控制台的打印：

```
准备初始化IOC容器。。。
@PostConstruct - 钢笔中已加满墨水。。。
InitializingBean - 准备写字。。。
init-method - 打开钢笔。。。
IOC容器初始化完成。。。

准备销毁IOC容器。。。
@PreDestroy - 钢笔中的墨水都放干净了。。。
DisposableBean - 写完字了。。。
destroy-method - 合上钢笔。。。
IOC容器销毁完成。。。
```

这个顺序又有点怪怪的，咱不要关注那些，总结执行顺序才是最关键的：**`@PostConstruct` → `InitializingBean` → `init-method`** 。

以上就是单实例 Bean 在 SpringFramework 中常见的 3 种生命周期，下面咱介绍原型 Bean 的生命周期执行。

## 5. 原型Bean的生命周期【掌握】

对于原型 Bean 的生命周期，使用的方式跟上面是完全一致的，只是它的触发时机就不像单实例 Bean 那样了。

单实例 Bean 的生命周期是陪着 IOC 容器一起的，容器初始化，单实例 Bean 也跟着初始化（当然不绝对，后面会介绍延迟 Bean ）；容器销毁，单实例 Bean 也跟着销毁。原型 Bean 由于每次都是取的时候才产生一个，所以它的生命周期与 IOC 容器无关。

> 本小节源码位置：`com.linkedbear.spring.lifecycle.d_prototype`

### 5.1 创建Bean+配置类

将上面的 `Pen3` 改名为 `Pen` ，移到一个新的包中，之后创建配置类，注册这个 `Pen` ，并标注原型 Bean ：

```java
@Configuration
public class PrototypeLifecycleConfiguration {
    
    @Bean(initMethod = "open", destroyMethod = "close")
    @Scope(ConfigurableBeanFactroy.SCOPE_PROTOTYPE)
    public Pen pen() {
        return new Pen();
    }
}
```

下面咱开始逐步测试。

### 5.2 IOC容器初始化时原型Bean不初始化

编写启动类，只初始化 IOC 容器：

```java
public class PrototypeLifecycleApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                PrototypeLifecycleConfiguration.class);
        System.out.println("IOC容器初始化完成。。。");
    }
}
```

运行 `main` 方法，控制台只打印了 `IOC容器初始化完成。。。` 这一句话，证明**原型 Bean 的创建不随 IOC 的初始化而创建**。

### 5.3 原型Bean的初始化动作与单实例Bean一致

在 `main` 方法中添加如下几行代码，来获取一次 Pen 实例：

```java
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                PrototypeLifecycleConfiguration.class);
        System.out.println("准备获取一个Pen。。。");
        Pen pen = ctx.getBean(Pen.class);
        System.out.println("已经取到了Pen。。。");
    }
```

运行，控制台打印 `Pen` 的初始化动作：

```
准备获取一个Pen。。。
@PostConstruct - 钢笔中已加满墨水。。。
InitializingBean - 准备写字。。。
init-method - 打开钢笔。。。
已经取到了Pen。。。
```

三种初始化的动作都执行了，证明**原型Bean的初始化动作与单实例Bean完全一致**。

### 5.4 原型Bean的销毁不包括destroy-method

在 `main` 方法中再添加几行代码，将这个 Pen 销毁掉：

```java
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                PrototypeLifecycleConfiguration.class);
        System.out.println("准备获取一个Pen。。。");
        Pen pen = ctx.getBean(Pen.class);
        System.out.println("已经取到了Pen。。。");
        System.out.println("用完Pen了，准备销毁。。。");
        ctx.getBeanFactroy().destroyBean(pen);
        System.out.println("Pen销毁完成。。。");
    }
```

再次运行 `main` 方法，发现控制台中只打印了 `@PreDestroy` 注解和 `DisposableBean` 接口的执行，没有触发 `destroy-method` 的执行：

```
用完Pen了，准备销毁。。。
@PreDestroy - 钢笔中的墨水都放干净了。。。
DisposableBean - 写完字了。。。
Pen销毁完成。。。
```

得出结论：**原型 Bean 在销毁时不处理 `destroy-method` 标注的方法**。

最后，咱列举一个三种生命周期控制的对比，方便小伙伴们理解。

## 6. 【面试题】SpringFramework中控制Bean生命周期的三种方式

以下的对比维度不是最终最全的，不过在现在的阶段已经是足够了：

|            | init-method & destroy-method              | @PostConstruct & @PreDestroy    | InitializingBean & DisposableBean |
| ---------- | ----------------------------------------- | ------------------------------- | --------------------------------- |
| 执行顺序   | 最后                                      | 最先                            | 中间                              |
| 组件耦合度 | 无侵入（只在 `<bean>` 和 `@Bean` 中使用） | 与 JSR 规范耦合                 | 与 SpringFramework 耦合           |
| 容器支持   | xml 、注解原生支持                        | 注解原生支持，xml需开启注解驱动 | xml 、注解原生支持                |
| 单实例Bean | √                                         | √                               | √                                 |
| 原型Bean   | 只支持 init-method                        | √                               | √                                 |

到这里，Bean 的基本生命周期就讲解完毕了（恩，仅仅是基本的），更复杂的生命周期知识咱放到后面的 IOC 高级中讲解。

## 小结与练习

1. Bean 的生命周期有几种控制方式？方式之间都有什么区别？
2. 单实例 Bean 与原型 Bean 的生命周期有什么不同？
3. 动手实现 Bean 的生命周期方式，并按照合理的逻辑改造上面的钢笔模型。

【到这里，IOC 的基础部分就都讲解完毕了，小伙伴们一定要把这部分基础打牢！一定要打牢！！！下面的难度会逐渐升高，当然也是小白逐渐蜕变成大佬的过程啦，小伙伴们继续跟随小册往下学习吧！】

# 14. IOC进阶-IOC容器的详细对比-BeanFactory

进入到进阶的部分，难度就不像前面那么低了，因为咱要慢慢进入 SpringFramework 更深层次的部分，来更透彻的了解 SpringFramework ，从而更好地驾驭它。

前面在第 6 章咱就说过，SpringFramework 中的容器最核心的是 `BeanFactory` 与 `ApplicationContext` ，但它们还有好多的子接口、抽象类和具体实现类，接下来的两章咱就把这些重要的子接口、实现类都研究个明明白白。

## 1. BeanFactory和它的子接口们

借助 IDEA ，可以将 `BeanFactory` 接口的所有子接口都取出来，形成一张图：

![img](《从0开始深入学习Spring》/c3fb460e3a9343d5b47a101d9bc5a9df~tplv-k3u1fbpfcp-zoom-1.image)

可以发现，这里面除了一些 `BeanFactory` 接口的扩展，还有 `ApplicationContext` ，那关于 `ApplicationContext` 的部分咱放到下一章，这部分只解释 `BeanFactory` 相关的重要接口。

### 1.1 BeanFactory【掌握】

`BeanFactory` 作为 SpringFramework 中最顶级的容器接口，它的作用一定是最简单、最核心的。下面咱先来看一看文档注释 ( javadoc ) 中的描述。

**【SpringFramework 的 javadoc 质量非常的高，建议小伙伴在该阶段进阶或者高阶深入时一定要结合 javadoc 来学习】**

文档注释的内容很多，咱拆分成几个部分来看，并详细解析。

#### 1.1.1 BeanFactory是根容器

> The root interface for accessing a Spring bean container. This is the basic client view of a bean container; further interfaces such as `ListableBeanFactory` and `org.springframework.beans.factory.config.ConfigurableBeanFactory` are available for specific purposes.
>
> 用于访问 SpringFramework bean 容器的根接口。这是 bean 容器的基本客户端视图。诸如 `ListableBeanFactory` 和 `org.springframework.beans.factory.config.ConfigurableBeanFactory` 之类的扩展接口可用于特定的用途。

这一段的解释是最开始，解释 `BeanFactory` 是 SpringFramework 中管理 Bean 的容器，它是最最基本的根接口，下面的扩展都是为了实现某些额外的特性（层次性、可搜索性、可配置性等）。

#### 1.1.2 BeanFactory中定义的作用域概念

> This interface is implemented by objects that hold a number of bean definitions, each uniquely identified by a String name. Depending on the bean definition, the factory will return either an independent instance of a contained object (the Prototype design pattern), or a single shared instance (a superior alternative to the Singleton design pattern, in which the instance is a singleton in the scope of the factory). Which type of instance will be returned depends on the bean factory configuration: the API is the same. Since Spring 2.0, further scopes are available depending on the concrete application context (e.g. "request" and "session" scopes in a web environment).
>
> `BeanFactory` 接口由包含多个 bean 定义的对象实现，每个 bean 的定义信息均由 “name” 进行唯一标识。根据 bean 的定义，SpringFramework 中的工厂会返回所包含对象的独立实例 ( prototype ，原型模式 ) ，或者返回单个共享实例 ( singleton ，单例模式的替代方案，其中实例是工厂作用域中的单例 ) 。返回 bean 的实例类型取决于 bean 工厂的配置：API是相同的。从 SpringFramework 2.0 开始，根据具体的应用程序上下文 ( 例如 Web 环境中的 request 和 session 作用域 ) ，可以使用更多作用域。

这段文档是解释了 `BeanFactory` 中设计的作用域概念，默认情况下，`BeanFactory` 中的 Bean 只有**单实例 Bean（`singleton`）** 和**原型 Bean（`prototype`）** ，自打 SpringFramework2.0 开始，出现了 Web 系列的作用域 `“request”` 和 `“session”` ，后续的又出现了 `“global session”` 和 `“websocket”` 作用域。

这里面有一句话不是很好理解：

> Which type of instance will be returned depends on the bean factory configuration: the API is the same.
>
> 返回 bean 的实例类型取决于 bean 工厂的配置：API是相同的。

前面的部分还可以，咱知道 Bean 的作用域类型取决于定义的 scope ，但后面的 `the API is the same.` 是什么鬼呢？回想一下配置 Bean 的作用域是怎么来的：

```java
@Component
@Scope("prototype")
public class Cat { }
```

无论是声明单实例 Bean ，还是原型 Bean ，都是用 `@Scope` 注解标注；在配置类中用 `@Bean` 注册组件，如果要显式声明作用域，也是用 `@Scope` 注解。由此就可以解释这句话了：**产生单实例 Bean 和原型 Bean 所用的 API 是相同的，都是用 `@Scope` 注解来声明，然后由 `BeanFactory` 来创建**。

#### 1.1.3 BeanFactory集成了环境配置

> The point of this approach is that the BeanFactory is a central registry of application components, and centralizes configuration of application components (no more do individual objects need to read properties files, for example). See chapters 4 and 11 of "Expert One-on-One J2EE Design and Development" for a discussion of the benefits of this approach.
>
> 这种方法的重点是 `BeanFactory` 是应用程序组件的注册中心，并且它集成了应用程序组件的配置（例如不再需要单个对象读取属性文件）。有关此方法的好处的讨论，请参见《Expert One-on-One J2EE Design and Development》的第4章和第11章。

这部分解释了 `BeanFactory` 它本身是所有 Bean 的注册中心，所有的 Bean 最终都在 `BeanFactory` 中创建和保存。另外 `BeanFactory` 中还集成了配置信息，这部分咱在第 8 章依赖注入中有接触到，咱通过加载外部的 properties 文件，借助 SpringFramework 的方式将配置文件的属性值设置到 Bean 对象中。

不过，这里面有关集成配置的概念，其实说的有点老了，自 SpringFramework 3.1 之后出现了一个新的概念叫 **`Environment`** ，到后面咱会展开讲解，它才是真正做环境和配置的保存地。

#### 1.1.4 BeanFactory推荐使用DI而不是DL

> Note that it is generally better to rely on Dependency Injection ("push" configuration) to configure application objects through setters or constructors, rather than use any form of "pull" configuration like a BeanFactory lookup. Spring's Dependency Injection functionality is implemented using this BeanFactory interface and its subinterfaces.
>
> 请注意，通常最好使用依赖注入（“推”的配置），通过setter方法或构造器注入的方式，配置应用程序对象，而不是使用任何形式的“拉”的配置（例如借助 `BeanFactory` 进行依赖查找）。 SpringFramework 的 Dependency Injection 功能是使用 `BeanFactory` 接口及其子接口实现的。

这部分的内容其实跟 `BeanFactory` 的关系不是特别大，它阐述的是 SpringFramework 官方在 IOC 的两种实现上的权衡：**推荐使用 DI ，尽可能不要使用 DL** 。

另外它这里面的一个概念特别好：**DI 的思想是“推”**，它主张把组件需要的依赖“推”到组件的成员上；**DL 的思想是”拉“**，组件需要哪些依赖需要组件自己去 IOC 容器中“拉取”。这样在解释 DL 和 DI 的概念和对比时就有了新的说法（奇怪的知识增加了~~~）。

#### 1.1.5 BeanFactory支持多种类型的配置源

> Normally a BeanFactory will load bean definitions stored in a configuration source (such as an XML document), and use the org.springframework.beans package to configure the beans. However, an implementation could simply return Java objects it creates as necessary directly in Java code. There are no constraints on how the definitions could be stored: LDAP, RDBMS, XML, properties file, etc. Implementations are encouraged to support references amongst beans (Dependency Injection).
>
> 通常情况下，`BeanFactory` 会加载存储在配置源（例如 XML 文档）中 bean 的定义，并使用 `org.springframework.beans` 包中的 API 来配置 bean 。然而，`BeanFactory` 的实现可以根据需要直接在 Java 代码中返回它创建的 Java 对象。bean 定义的存储方式没有任何限制，它可以是 LDAP （轻型文件目录访问协议），RDBMS（关系型数据库系统），XML，properties 文件等。鼓励实现以支持 Bean 之间的引用（依赖注入）。

这一段告诉我们，SpringFramework 可以支持的配置源类型有很多种，当然咱最常用的还是 xml 和注解驱动啦 ~ 这些配置源中存储的信息是一些 Bean 的定义，这个概念很复杂，咱放到后面的 `BeanDefinition` 中介绍。

#### 1.1.6 BeanFactory可实现层次性

> In contrast to the methods in ListableBeanFactory, all of the operations in this interface will also check parent factories if this is a HierarchicalBeanFactory. If a bean is not found in this factory instance, the immediate parent factory will be asked. Beans in this factory instance are supposed to override beans of the same name in any parent factory.
>
> 与 `ListableBeanFactory` 中的方法相比，`BeanFactory` 中的所有操作还将检查父工厂（如果这是 `HierarchicalBeanFactory` ）。如果在 `BeanFactory` 实例中没有找到指定的 bean ，则会向父工厂中搜索查找。`BeanFactory` 实例中的 Bean 应该覆盖任何父工厂中的同名 Bean 。

这部分想告诉我们的是，`BeanFactory` 本身可以支持**父子结构**，这个父子结构的概念和实现由 `HierarchicalBeanFactory` 实现，在 `BeanFactory` 中它也只是提了一下。这部分咱放到下面的 `HierarchicalBeanFactory` 中解释。

#### 1.1.7 BeanFactory中设有完整的生命周期控制机制

> Bean factory implementations should support the standard bean lifecycle interfaces as far as possible. The full set of initialization methods and their standard order is:
>
> 1. BeanNameAware's `setBeanName`
> 2. BeanClassLoaderAware's `setBeanClassLoader`
> 3. ......
>
> On shutdown of a bean factory, the following lifecycle methods apply: ......
>
> `BeanFactory` 接口实现了尽可能支持标准 Bean 的生命周期接口。全套初始化方法及其标准顺序为：......
>
> 在关闭 `BeanFactory` 时，以下生命周期方法适用：......

由这一段咱能很清楚的了解到，Bean 的生命周期是在 `BeanFactory` 中就有设计的，而且官方文档也提供了全套的初始化和销毁流程，这个咱在这里不展开，后面会有专门介绍完整的 Bean 的生命周期的章节来讲解此部分内容（讲真想完整理解好也挺难的，先做好心理预备）。

#### 1.1.8 小结

到这里，小伙伴是不是对 `BeanFactory` 有了一个更深刻的认识了呢？总结下来 `BeanFactory` 提供了如下基础的特性：

- 基础的容器
- 定义了作用域的概念
- 集成环境配置
- 支持多种类型的配置源
- 层次性的设计
- 完整的生命周期控制机制

这些内容有一部分咱前面已经学习过了，剩下的一些部分咱后面的 IOC 高级部分都会讲到。

### 1.2 HierarchicalBeanFactory【熟悉】

从类名上能很容易的理解，它是体现了**层次性**的 `BeanFactory` 。有了这个特性，`BeanFactory` 就有了**父子结构**。它的文档注释蛮简单的，咱看一眼：

> Sub-interface implemented by bean factories that can be part of a hierarchy.
>
> The corresponding setParentBeanFactory method for bean factories that allow setting the parent in a configurable fashion can be found in the ConfigurableBeanFactory interface.
>
> 由 `BeanFactory` 实现的子接口，它可以理解为是层次结构的一部分。
>
> 可以在 `ConfigurableBeanFactory` 接口中找到用于 `BeanFactory` 的相应 `setParentBeanFactory` 方法，该方法允许以可配置的方式设置父对象。

果然文档注释也解释的很清晰了，对应的接口方法定义中，就有这么一个方法：**`getParentBeanFactory()`** ，它就可以获取到父 `BeanFactory` 对象；接口中还有一个方法是 `containsLocalBean(String name)` ，它是检查当前本地的容器中是否有指定名称的 Bean ，而不会往上找父 `BeanFactory` 。

> ```
> getBean` 方法会从当前 `BeanFactory` 开始查找是否存在指定的 Bean ，如果当前找不到就依次向上找父 `BeanFactory` ，直到找到为止返回，或者都找不到最终抛出 `NoSuchBeanDefinitionException
> ```

注意这里的说法：如果当前找不到就往上找，那如果找到了就不往上找了。思考一个问题：如果当前 `BeanFactory` 中有指定的 Bean 了，父 `BeanFactory` 中可能有吗？

答案是有，因为**即便存在父子关系，但他们本质上是不同的容器，所以有可能找到多个相同的 Bean** 。换句话说，**`@Scope` 中声明的 Singleton 只是在一个容器中是单实例的，但有了层次性结构后，对于整体的多个容器来看，就不是单实例的了**。

至于怎么设置父 `BeanFactory` ，文档注释中也说了，要用 `ConfigurableBeanFactory` 的 `setParentBeanFactory` 方法，那至于 `ConfigurableBeanFactory` 是什么东西，咱下面自然会解释。

### 1.3 ListableBeanFactory【熟悉】

类名理解为**“可列举”**的 `BeanFactory` ，它的文档也把这个特性解释的很清楚，咱一段一段来读。

#### 1.3.1 ListableBeanFactory可以列举出容器中的所有Bean

> Extension of the BeanFactory interface to be implemented by bean factories that can enumerate all their bean instances, rather than attempting bean lookup by name one by one as requested by clients. BeanFactory implementations that preload all their bean definitions (such as XML-based factories) may implement this interface.
>
> 它是 `BeanFactory` 接口的扩展实现，它可以列举出所有 bean 实例，而不是按客户端调用的要求，按照名称一一进行 bean 的依赖查找。具有 “预加载其所有 bean 定义信息” 的 `BeanFactory` 实现（例如基于XML的 `BeanFactory` ）可以实现此接口。

这段话比较好理解了，它的扩展功能是能让咱在拿到 `BeanFactory` 时可以直接**把容器中的所有 Bean 都拿出来**（也就相当于提供了**可迭代**的特性），而不是一个一个的拿 name 去取（一个一个的取会很麻烦，而且很大程度上取不全）。后面提到了一个概念，叫“预加载所有 bean 的定义信息”，这个也是涉及到 `BeanDefinition` 的东西了，咱到后面讲解 `BeanDefinition` 时再详细介绍。

#### 1.3.2 ListableBeanFactory只列举当前容器中的Bean

> If this is a HierarchicalBeanFactory, the return values will not take any BeanFactory hierarchy into account, but will relate only to the beans defined in the current factory. Use the BeanFactoryUtils helper class to consider beans in ancestor factories too.
>
> 如果当前 `BeanFactory` 同时也是 `HierarchicalBeanFactory` ，则返回值会忽略 `BeanFactory` 的层次结构，仅仅与当前 `BeanFactory` 中定义的 bean 有关。除此之外，也可以使用 `BeanFactoryUtils` 来考虑父 `BeanFactory` 中的 bean 。

通过这部分可以了解到另外一个特性：**`ListableBeanFactory` 只会列举当前容器的 Bean** ，因为咱上面也看了，`BeanFactory` 可以具有层次性，那这样再列举所有 Bean 的时候，就需要斟酌到底是获取包括父容器在内的所有 Bean ，还是只获取当前容器中的 Bean ，SpringFramework 在斟酌之后选择了**只获取当前容器中的 Bean** ，而如果真的想获取所有 Bean ，可以借助 `BeanFactoryUtils` 工具类来实现（工具类中有不少以 `"IncludingAncestors"` 结尾的方法，代表可以一起取父容器）。

#### 1.3.3 ListableBeanFactory会有选择性的列举

> The methods in this interface will just respect bean definitions of this factory. They will ignore any singleton beans that have been registered by other means like org.springframework.beans.factory.config.ConfigurableBeanFactory's registerSingleton method, with the exception of getBeanNamesOfType and getBeansOfType which will check such manually registered singletons too. Of course, BeanFactory's getBean does allow transparent access to such special beans as well. However, in typical scenarios, all beans will be defined by external bean definitions anyway, so most applications don't need to worry about this differentiation.
>
> `ListableBeanFactory` 中的方法将仅遵循当前工厂的 bean 定义，它们将忽略通过其他方式（例如 `ConfigurableBeanFactory` 的 `registerSingleton` 方法）注册的任何单实例 bean （但 `getBeanNamesOfType` 和 `getBeansOfType` 除外），它们也会检查这种手动注册的单实例 Bean 。当然，`BeanFactory` 的 `getBean` 确实也允许透明访问此类特殊 bean 。在一般情况下，无论如何所有的 bean 都来自由外部的 bean 定义信息，因此大多数应用程序不必担心这种区别。

这一段注释的意思似乎有点让人摸不着头脑：作为一个“可迭代”的 `BeanFactory` ，按理来讲应该最起码得把当前容器中的所有 Bean 都列出来，结果你又告诉我**有些 Bean 会被忽略掉不给列**，那你想怎样嘛！ヽ(`Д´)ﾉ 别着急，下面小册会给你解释的，不过在解释之前，咱先演示一下这段注释的代码体现。

##### 1.3.3.1 创建Bean+配置文件

创建两个最最简单的类：

```java
public class Cat { }
public class Dog { }
```

之后编写 xml 配置文件，只注册 Cat 进去：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean class="com.linkedbear.spring.container.a_beanfactory.bean.Cat"/>
</beans>
```

##### 1.3.3.2 驱动原始的BeanFactory加载配置文件

这次咱驱动的时候，选用 `BeanFactory` 的最终实现来构造 IOC 容器（虽然现在看来有点超纲，但是没关系，下面会讲到哈）：

```java
public class ListableBeanFactoryApplication {
    
    public static void main(String[] args) throws Exception {
        ClassPathResource resource = new ClassPathResource("container/listable-container.xml");
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        XmlBeanDefinitionReader beanDefinitionReader = new XmlBeanDefinitionReader(beanFactory);
        beanDefinitionReader.loadBeanDefinitions(resource);
        // 直接打印容器中的所有Bean
        System.out.println("加载xml文件后容器中的Bean：");
        Stream.of(beanFactory.getBeanDefinitionNames()).forEach(System.out::println);
    }
}
```

使用这种方式，也可以加载 xml 配置文件，完成 IOC 容器的构建。此时如果直接打印 IOC 容器中的 Bean ，可以发现确实只有一个 cat ：

```
加载xml文件后容器中的Bean：
com.linkedbear.spring.container.a_beanfactory.bean.Cat#0
```

##### 1.3.3.3 测试手动注册Bean

虽然现在看来这个操作小伙伴还不熟悉，但是没关系，先跟着小册敲一遍，了解一下还有这种操作就 OK 了：

```java
public class ListableBeanFactoryApplication {
    
    public static void main(String[] args) throws Exception {
        ClassPathResource resource = new ClassPathResource("container/listable-container.xml");
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        XmlBeanDefinitionReader beanDefinitionReader = new XmlBeanDefinitionReader(beanFactory);
        beanDefinitionReader.loadBeanDefinitions(resource);
        // 直接打印容器中的所有Bean
        System.out.println("加载xml文件后容器中的Bean：");
        Stream.of(beanFactory.getBeanDefinitionNames()).forEach(System.out::println);
        System.out.println();
        
        // 手动注册一个单实例Bean
        beanFactory.registerSingleton("doggg", new Dog());
        // 再打印容器中的所有Bean
        System.out.println("手动注册单实例Bean后容器中的所有Bean：");
        Stream.of(beanFactory.getBeanDefinitionNames()).forEach(System.out::println);
    }
}
```

再次运行 `main` 方法，可以发现控制台还是只打印了一个 cat ：

```
加载xml文件后容器中的Bean：
com.linkedbear.spring.container.a_beanfactory.bean.Cat#0

手动注册单实例Bean后容器中的所有Bean：
com.linkedbear.spring.container.a_beanfactory.bean.Cat#0
```

是不是突然一脸楞逼，也或者突然明白上面文档注释中说的那句话了？`ListableBeanFactory` 在获取容器内所有 Bean 时真的不会把这些手动注册的拿出来，也就是文档注释中说的 **“忽略通过其他方式”** ！可是容器里真的有 `Dog` 了吗？

##### 1.3.3.4 容器中真的注册了Dog

在上面的启动类 `main` 方法最后再追加这么几行代码：

```java
    System.out.println("容器中真的有注册Dog：" + beanFactory.getBean("doggg"));
    // 通过getBeanNamesOfType查找Dog
    System.out.println("容器中的所有Dog：" + Arrays.toString(beanFactory.getBeanNamesForType(Dog.class)));
```

重新运行，控制台打印了 `Dog` 的地址和名称：

```
容器中真的有注册Dog：com.linkedbear.spring.container.a_beanfactory.bean.Dog@50cbc42f
容器中的所有Dog：[doggg]
```

说明文档注释中说的 `getBeanNamesOfType` 和 `getBeansOfType` 两个方法是例外的，它们可以取到手动注册的 Bean 。

##### 1.3.3.5 【源码】ListableBeanFactory设计选择性列举的目的

现象看到了，可它为什么要这么设计呢？这里只是先简单提一下，后面在讲解 `BeanDefinition` 章节部分时会回来填这个坑的。

借助 IDEA ，查看 `ConfigurableBeanFactory` 的 `registerSingleton` 方法调用，可以发现在一个叫 `AbstractApplicationContext` 的 `prepareBeanFactory` 方法中有一些使用：（源码节选）

```java
    // Register default environment beans.
    if (!beanFactory.containsLocalBean(ENVIRONMENT_BEAN_NAME)) {
        beanFactory.registerSingleton(ENVIRONMENT_BEAN_NAME, getEnvironment());
    }
    if (!beanFactory.containsLocalBean(SYSTEM_PROPERTIES_BEAN_NAME)) {
        beanFactory.registerSingleton(SYSTEM_PROPERTIES_BEAN_NAME, getEnvironment().getSystemProperties());
    }
    if (!beanFactory.containsLocalBean(SYSTEM_ENVIRONMENT_BEAN_NAME)) {
        beanFactory.registerSingleton(SYSTEM_ENVIRONMENT_BEAN_NAME, getEnvironment().getSystemEnvironment());
    }
```

可以发现它在这里直接注册了几个组件，而这些组件都是**属于 SpringFramework 内部使用的**，这样做的目的是 **SpringFramework 不希望咱开发者直接操控他们，于是就使用了这种方式来隐藏它们**。

这个设计如果不是很好理解的话，我举另外一个例子：在 Windows 系统中，系统不希望咱用户去随意改动系统内部使用的一些文件，会在文件资源管理器中设置一个选项：**隐藏受保护的操作系统文件**（在控制面板 → 文件资源管理器选项中）。

![img](《从0开始深入学习Spring》/b3a847772a8048098e49275da443c76b~tplv-k3u1fbpfcp-zoom-1.image)

默认情况下这个选项是勾选的（意思就是这些文件我都藏起来了，我自己管理就行，不用你操心），当然你可以取消勾选它，这样文件资源管理器中也能显示那些操作系统的文件，但你要是真的动了它们，指不定你的机器就出什么问题了。

这样大概可以理解 `ListableBeanFactory` 这样设计的目的了吧，那这一段注释也就差不多理解完了。

#### 1.3.4 ListableBeanFactory的大部分方法不适合频繁调用

> NOTE: With the exception of getBeanDefinitionCount and containsBeanDefinition, the methods in this interface are not designed for frequent invocation. Implementations may be slow.
>
> 注意：除了 `getBeanDefinitionCount` 和 `containsBeanDefinition` 之外，此接口中的方法不适用于频繁调用，方法的实现可能执行速度会很慢。

最后文档注释中给了一句提醒，说这个接口里的大部分方法都不适合频繁调用，这个咱也能理解，毕竟谁会动不动去翻 IOC 容器的东西呢？顶多是读完一遍就自己缓存起来吧！而且一般情况下也不会有业务需求会深入到 IOC 容器的底部吧，所以这个提醒算是挺贴心的，而且咱开发者也都这么做了。

### 1.4 AutowireCapableBeanFactory【了解】

类名中有一个熟悉的概念：自动注入，它的意思就应该是：**支持自动注入的 `BeanFactory`** 。那是不是就意味着，这个扩展的 `BeanFactory` 就可以支持 DI 了呢？咱还是先从文档注释入手。

#### 1.4.1 AutowireCapableBeanFactory可以支持外部Bean的自动装配

> Extension of the BeanFactory interface to be implemented by bean factories that are capable of autowiring, provided that they want to expose this functionality for existing bean instances.
>
> 它是 `BeanFactory` 接口的扩展实现，它可以实现自动装配，前提是开发者希望为现有的 bean 实例公开此功能。

这句话的意思如果只是直译，那可能比较难理解，所以我在下面贴翻译的时候让这句话更好理解了一点。由这句话也能粗略的有一个概念：AutowireCapableBeanFactory 本身可以支持自动装配，而且还可以为**现有的一些 Bean 也能支持自动装配**。而这个“现有”的概念，实际上指的是那些**不被 SpringFramework 管理的 Bean** ，下面两段话就有解释。

#### 1.4.2 AutowireCapableBeanFactory用于框架集成

> This subinterface of BeanFactory is not meant to be used in normal application code: stick to BeanFactory or ListableBeanFactory for typical use cases.
>
> Integration code for other frameworks can leverage this interface to wire and populate existing bean instances that Spring does not control the lifecycle of. This is particularly useful for WebWork Actions and Tapestry Page objects, for example.
>
> `AutowireCapableBeanFactory` 这个子接口不能在常规的应用程序代码中使用：一般情况下，请坚持使用 `BeanFactory` 或 `ListableBeanFactory` 。 其他框架的集成代码可以利用此接口来连接和注入 SpringFramework 无法控制其生命周期的现有 bean 实例。例如，这对于 WebWork 操作和 Tapestry 页面对象特别有用。

这两段话想表达的意思，主要是说这个 `AutowireCapableBeanFactory` 一般不要让咱自己用，而是在**与其他框架进行集成时才使用**。注意这里面它的描述：**利用此接口来连接和注入 SpringFramework 无法控制其生命周期的现有 bean 实例**，这其实已经把它的作用完整的描述出来了：你要是真想用它，那也是**在跟其它框架集成时**，如果**其它框架的一些 Bean 实例无法让 SpringFramework 控制，但又需要注入一些由 SpringFramework 管理的对象**，那就可以用它了。

可能小伙伴有些疑惑，这个思路有什么使用场景吗？来，试想一个场景：

你自己编写了一个 Servlet ，而这个 Servlet 里面需要引入 IOC 容器中的一个存在的 Service ，应该如何处理呢？

根据 IOC 的思路，很明显还是两种思路：**DL 和 DI** ：

- DL ：由 Servlet 自己取到 IOC 容器，并直接从 IOC 容器中获取到对应的 Service 并保存至成员属性中【拉】
- DI ：给需要注入的 Service 上标注 `@Autowired` 等自动注入的注解，并且让 IOC 容器识别这个 Servlet ，完成自动注入【推】

对于 DL 的实现，SpringFramework 有一种机制可以让 Servlet 取到 IOC 容器；而 DI 的实现，就需要这个 `AutowireCapableBeanFactory` 帮忙注入了。至于这部分怎么搞，咱放到后面介绍 Web 部分时再讲解。

#### 1.4.3 AutowireCapableBeanFactory不由ApplicationContext实现但可获取

> Note that this interface is not implemented by ApplicationContext facades, as it is hardly ever used by application code. That said, it is available from an application context too, accessible through ApplicationContext's getAutowireCapableBeanFactory() method.
>
> 请注意，该接口没有在 `ApplicationContext` 中实现，因为应用程序代码几乎从未使用过此接口。也就是说，它也可以从应用程序上下文中获得：可以通过 `ApplicationContext` 的 `getAutowireCapableBeanFactory()` 方法进行访问。

这段话已经很明确的表示了：**这个扩展你们一般用不到，但我给你取的方式，你们需要的时候自己拿**。

#### 1.4.4 AutowireCapableBeanFactory可以借助BeanFactoryAware注入

> You may also implement the org.springframework.beans.factory.BeanFactoryAware interface, which exposes the internal BeanFactory even when running in an ApplicationContext, to get access to an AutowireCapableBeanFactory: simply cast the passed-in BeanFactory to AutowireCapableBeanFactory.
>
> 您还可以实现 `BeanFactoryAware` 接口，该接口即使在 `ApplicationContext` 中运行时也公开内部 `BeanFactory` ，以访问 `AutowireCapableBeanFactory` ：只需将传入的 `BeanFactory` 强制转换为 `AutowireCapableBeanFactory` 。

这部分告诉咱，其实通过 `BeanFactoryAware` 接口注入的 `BeanFactory` 也就是 `AutowireCapableBeanFactory` ，可以直接强转拿来用。这个说实话，提不提这个都行，注入 `ApplicationContext` 一样可以拿到它。

### 1.5 ConfigurableBeanFactory【熟悉】

从类名中就能意识到，这个扩展已经具备了“**可配置**”的特性，这个概念咱要拿出来解释一下了。

#### 1.5.0 可读&可写

回想一开始学习面向对象编程时，就知道一个类的属性设置为 private 后，提供 **get** 方法则意味着该属性**可读**，提供 **set** 方法则意味着该属性**可写**。同样的，在 SpringFramework 的这些 `BeanFactory` ，包括后面的 `ApplicationContext` 中，都会有这样的设计。普通的 `BeanFactory` 只有 get 相关的操作，而 **Configurable** 开头的 `BeanFactory` 或者 `ApplicationContext` 就具有了 set 的操作：（节选自 `ConfigurableBeanFactory` 的方法列表）

```java
    void setBeanClassLoader(@Nullable ClassLoader beanClassLoader);
    void setTypeConverter(TypeConverter typeConverter);
    void addBeanPostProcessor(BeanPostProcessor beanPostProcessor);
```

理解了这个概念，咱可以来看 `ConfigurableBeanFactory` 的文档注释了。

#### 1.5.1 ConfigurableBeanFactory提供可配置的功能

> Configuration interface to be implemented by most bean factories. Provides facilities to configure a bean factory, in addition to the bean factory client methods in the BeanFactory interface. 大多数 `BeanFactory` 的实现类都会实现这个带配置的接口。除了 `BeanFactory` 接口中的基础获取方法之外，还提供了配置 `BeanFactory` 的功能。

一上来就说明白了，`ConfigurableBeanFactory` 已经提供了**带配置的功能**，可以调用它里面定义的方法来对 `BeanFactory` 进行修改、扩展等。

#### 1.5.2 ConfigurableBeanFactory不推荐给开发者使用

> This bean factory interface is not meant to be used in normal application code: Stick to BeanFactory or org.springframework.beans.factory.ListableBeanFactory for typical needs. This extended interface is just meant to allow for framework-internal plug'n'play and for special access to bean factory configuration methods.
>
> `ConfigurableBeanFactory` 接口并不希望开发者在应用程序代码中使用，而是坚持使用 `BeanFactory` 或 `ListableBeanFactory` 。此扩展接口仅用于允许在框架内部进行即插即用，并允许对 `BeanFactory` 中的配置方法的特殊访问。

下面又说了，SpringFramework 不希望开发者用 `ConfigurableBeanFactory` ，而是老么实的用最根本的 `BeanFactory` ，原因也很简单，**程序在运行期间按理不应该对 `BeanFactory` 再进行频繁的变动**，此时只应该有读的动作，而不应该出现写的动作。

到这里，有关 `BeanFactory` 和它扩展的重要接口也就了解的差不多了，下面咱看看有关 `BeanFactory` 的实现类，看看 SpringFramework 是如何有层次的划分 `BeanFactory` 的功能职责的。

## 2. BeanFactory的实现类们

跟前面一样，借助 IDEA ，可以将 `BeanFactory` 的实现类取出来，形成一张图：（当然，这里面不是所有的，只包含最核心的实现类）

![img](《从0开始深入学习Spring》/07b6807731d4430185d5ec7ea8483fbc~tplv-k3u1fbpfcp-zoom-1.image)

注意到这里面不止有 `BeanFactory` 接口，还出现了几个陌生的接口（ `SingletonBeanRegistry` 、`BeanDefinitionRegistry` ），这些咱暂时不关心，放到后面的章节再解释。

### 2.1 AbstractBeanFactory【熟悉】

为什么一上来先说它，而不是它的父类 `DefaultSingletonBeanRegistry` 呢？很简单，咱介绍的是 `BeanFactory` 的实现类，`DefaultSingletonBeanRegistry` 并没有实现。

从类名上就知道，它是 `BeanFactory` 最基本的抽象实现，当然作为一个抽象类，一定是只具备了部分功能，不是完整的实现。先看一眼文档注释，对这个类有一个大概的了解。

#### 2.1.1 AbstractBeanFactory是最终BeanFactory的基础实现

> Abstract base class for BeanFactory implementations, providing the full capabilities of the ConfigurableBeanFactory SPI. Does not assume a listable bean factory: can therefore also be used as base class for bean factory implementations which obtain bean definitions from some backend resource (where bean definition access is an expensive operation).
>
> 它是 `BeanFactory` 接口最基础的抽象实现类，提供 `ConfigurableBeanFactory` SPI 的全部功能。我们不假定有一个可迭代的 `BeanFactory` ，因此也可以用作 `BeanFactory` 实现的父类，该实现可以从某些后端资源（其中 bean 定义访问是一项昂贵的操作）获取 bean 的定义。

这段注释说好理解，但又有点不好理解。其实它就想表达一个意思：`AbstractBeanFactory` 是作为 `BeanFactory` 接口下面的第一个抽象的实现类，它具有最基础的功能，并且它可以从配置源（之前看到的 xml 、LDAP 、RDBMS 等）获取 Bean 的定义信息，而这个 Bean 的定义信息就是 `BeanDefinition` ，已经提到了很多遍了，但是不要着急，咱后面会接触到的。

把这些都读完，剩下一个咱不认识的概念：**SPI** ，这是个什么东西呢？这里咱简单提一下，SPI 全称为 **Service Provider Interface**，是 jdk 内置的一种服务提供发现机制。说白了，它可以加载预先在特定位置下配置的一些类。关于 SPI 的部分，会在后面的 “模块装配高级” 中更详细的讲解。

#### 2.1.2 AbstractBeanFactory对Bean的支持

> This class provides a singleton cache (through its base class DefaultSingletonBeanRegistry), singleton/prototype determination, FactoryBean handling, aliases, bean definition merging for child bean definitions, and bean destruction (org.springframework.beans.factory.DisposableBean interface, custom destroy methods). Furthermore, it can manage a bean factory hierarchy (delegating to the parent in case of an unknown bean), through implementing the org.springframework.beans.factory.HierarchicalBeanFactory interface.
>
> 此类可以提供单实例 Bean 的缓存（通过其父类 `DefaultSingletonBeanRegistry` ），单例/原型 Bean 的决定，`FactoryBean` 处理，Bean 的别名，用于子 bean 定义的 bean 定义合并以及 bean 销毁（ `DisposableBean` 接口，自定义 `destroy` 方法）。此外，它可以通过实现 `HierarchicalBeanFactory` 接口来管理 `BeanFactory` 层次结构（在未知 bean 的情况下委托给父工厂）。

从这部分的描述中，咱看到除了在之前 `BeanFactory` 中介绍的功能和特性之外，它还扩展了另外一些功能：别名的处理（来源于 `AliasRegistry` 接口）、Bean 定义的合并（涉及到 Bean 的继承，后续章节讲解）、Bean 的销毁动作支持（ `DisposableBean` ）等等，这些特性有一些咱已经见过了，有一些还没有接触，咱后面都会来展开介绍。

#### 2.1.3 AbstractBeanFactory定义了模板方法

> The main template methods to be implemented by subclasses are getBeanDefinition and createBean, retrieving a bean definition for a given bean name and creating a bean instance for a given bean definition, respectively. Default implementations of those operations can be found in DefaultListableBeanFactory and AbstractAutowireCapableBeanFactory.
>
> 子类要实现的主要模板方法是 `getBeanDefinition` 和 `createBean` ，分别为给定的 bean 名称检索 bean 定义信息，并根据给定的 bean 定义信息创建 bean 的实例。这些操作的默认实现可以在 `DefaultListableBeanFactory` 和 `AbstractAutowireCapableBeanFactory` 中找到。

这一段告诉我们一个很关键的信息：SpringFramework 中大量使用**模板方法模式**来设计核心组件，它的思路是：**父类提供逻辑规范，子类提供具体步骤的实现**。在文档注释中，咱看到 `AbstractBeanFactory` 中对 `getBeanDefinition` 和 `createBean` 两个方法进行了规范上的定义，分别代表获取 Bean 的定义信息，以及创建 Bean 的实例，这两个方法都会在 SpringFramework 的 IOC 容器初始化阶段起到至关重要的作用。

多说一句，`createBean` 是 SpringFramework 能管控的所有 Bean 的创建入口。

### 2.2 AbstractAutowireCapableBeanFactory【掌握】

根据类名，可以看出来，它已经到了 `AutowireCapableBeanFactory` 接口的落地实现了，那就意味着，它可以实现组件的自动装配了。其实它的作用不仅仅是这么点，看小册标注的【掌握】也应该意识到它的重要，这个实现会比较详细的展开解释。

#### 2.2.1 AbstractAutowireCapableBeanFactory提供Bean的创建逻辑实现

> Abstract bean factory superclass that implements default bean creation, with the full capabilities specified by the RootBeanDefinition class. Implements the AutowireCapableBeanFactory interface in addition to AbstractBeanFactory's createBean method.
>
> 它是实现了默认 bean 创建逻辑的的抽象的 `BeanFactory` 实现类，它具有 `RootBeanDefinition` 类指定的全部功能。除了 `AbstractBeanFactory` 的 `createBean` 方法之外，还实现 `AutowireCapableBeanFactory` 接口。

一上来文档注释就告诉咱了，这个 `AbstractAutowireCapableBeanFactory` 继承了 `AbstractBeanFactory` 抽象类，还额外实现了 `AutowireCapableBeanFactory` 接口，那实现了这个接口就代表着，它可以**实现自动注入的功能**了。除此之外，它还把 `AbstractBeanFactory` 的 `createBean` 方法给实现了，代表它还具有**创建 Bean 的功能**。

这个地方要多说一嘴，其实 **`createBean` 方法也不是最终实现 Bean 的创建**，而是有另外一个叫 **`doCreateBean`** 方法，它同样在 `AbstractAutowireCapableBeanFactory` 中定义，而且是 **protected** 方法，没有子类重写它，算是它独享的了。关于这个 `doCreateBean` 的实现，是相当复杂的，涉及到的知识点特别多，咱后面遇到时再解释，或者小伙伴可以参照[《SpringBoot 源码解读与原理分析》](https://juejin.im/book/5da3bc3d6fb9a04e35597a76)小册中的第 14 、15 章进行学习，本小册中对于该部分内容不会特别深的展开。

#### 2.2.2 AbstractAutowireCapableBeanFactory实现了属性赋值和组件注入

> Provides bean creation (with constructor resolution), property population, wiring (including autowiring), and initialization. Handles runtime bean references, resolves managed collections, calls initialization methods, etc. Supports autowiring constructors, properties by name, and properties by type.
>
> 提供 Bean 的创建（具有构造方法的解析），属性填充，属性注入（包括自动装配）和初始化。处理运行时 Bean 的引用，解析托管集合，调用初始化方法等。支持自动装配构造函数，按名称的属性和按类型的属性。

这一段已经把 `AbstractAutowireCapableBeanFactory` 中实现的最最核心功能全部列出来了：**Bean 的创建、属性填充和依赖的自动注入、Bean 的初始化**。这部分是**创建 Bean 最核心的三个步骤**，后续在讲解 Bean 的完整生命周期时，会详细深入的讲解这部分，小伙伴要做好思想准备哦。

#### 2.2.3 AbstractAutowireCapableBeanFactory保留了模板方法

> The main template method to be implemented by subclasses is resolveDependency(DependencyDescriptor, String, Set, TypeConverter), used for autowiring by type. In case of a factory which is capable of searching its bean definitions, matching beans will typically be implemented through such a search. For other factory styles, simplified matching algorithms can be implemented.
>
> 子类要实现的主要模板方法是 `resolveDependency(DependencyDescriptor, String, Set, TypeConverter)` ，用于按类型自动装配。如果工厂能够搜索其 bean 定义，则通常将通过此类搜索来实现匹配的 bean 。对于其他工厂样式，可以实现简化的匹配算法。

跟 `AbstractBeanFactory` 不太一样，`AbstractAutowireCapableBeanFactory` 没有把全部模板方法都实现完，它保留了文档注释中提到的 `resolveDependency` 方法，这个方法的作用是**解析 Bean 的成员中定义的属性依赖关系**。

#### 2.2.4 AbstractAutowireCapableBeanFactory不负责BeanDefinition的注册

> Note that this class does not assume or implement bean definition registry capabilities. See DefaultListableBeanFactory for an implementation of the org.springframework.beans.factory.ListableBeanFactory and BeanDefinitionRegistry interfaces, which represent the API and SPI view of such a factory, respectively.
>
> 请注意，此类不承担或实现 bean 定义注册的功能。有关 `ListableBeanFactory` 和 `BeanDefinitionRegistry` 接口的实现，请参见`DefaultListableBeanFactory` ，它们分别表示该工厂的 API 和 SPI 视图。

最后一段注释，它想表明的是，`AbstractAutowireCapableBeanFactory` 实现了对 Bean 的创建、赋值、注入、初始化的逻辑，但对于 Bean 的定义是如何进入 `BeanFactory` 的，它不负责。这里面涉及到两个流程：**Bean 的创建**、**Bean 定义的进入**，这个咱放到后面 `BeanDefinition` 和 Bean 的完整生命周期中再详细解释。

### 2.3 DefaultListableBeanFactory【掌握】

这个类是**唯一一个目前使用的 `BeanFactory` 的落地实现了**，可想而知它的地位和重要性有多高，小伙伴一定要予以重视。

#### 2.3.1 DefaultListableBeanFactory是BeanFactory最终的默认实现

> Spring's default implementation of the ConfigurableListableBeanFactory and BeanDefinitionRegistry interfaces: a full-fledged bean factory based on bean definition metadata, extensible through post-processors.
>
> Spring 的 `ConfigurableListableBeanFactory` 和 `BeanDefinitionRegistry` 接口的默认实现，它时基于 Bean 的定义信息的的成熟的 `BeanFactory` 实现，它可通过后置处理器进行扩展。

翻看源码就知道，`DefaultListableBeanFactory` 已经没有 **abstract** 标注了，说明它可以算作一个**成熟的落地实现**了。

这里面要多注意的一个点：**`BeanDefinitionRegistry`** ，它又是个啥？字面意思理解为 **“Bean 定义的注册器”** ，它具体能干嘛咱先不用着急深入学习，先有个印象就好，下面的注释就解释它的用途了。

#### 2.3.2 DefaultListableBeanFactory会先注册Bean定义信息再创建Bean

> Typical usage is registering all bean definitions first (possibly read from a bean definition file), before accessing beans. Bean lookup by name is therefore an inexpensive operation in a local bean definition table, operating on pre-resolved bean definition metadata objects.
>
> 典型的用法是在访问 bean 之前先注册所有 bean 定义信息（可能是从有 bean 定义的文件中读取）。因此，按名称查找 Bean 是对本地 Bean 定义表进行的合理操作，该操作对预先解析的 Bean 定义元数据对象进行操作。

由此可见，`DefaultListableBeanFactory` 在 `AbstractAutowireCapableBeanFactory` 的基础上，完成了**注册 Bean 定义信息**的动作，而这个动作就是通过上面的 **`BeanDefinitionRegistry`** 来实现的。所以咱就可以知道一点，完整的 BeanFactory 对 Bean 的管理，应该是**先注册 Bean 的定义信息，再完成 Bean 的创建和初始化动作**。这个流程，在后面讲解完整的 Bean 生命周期时会详细讲到。

#### 2.3.3 DefaultListableBeanFactory不负责解析Bean定义文件

> Note that readers for specific bean definition formats are typically implemented separately rather than as bean factory subclasses: see for example PropertiesBeanDefinitionReader and org.springframework.beans.factory.xml.XmlBeanDefinitionReader.
>
> 请注意，特定 bean 定义信息格式的解析器通常是单独实现的，而不是作为 `BeanFactory` 的子类实现的，有关这部分的内容参见 `PropertiesBeanDefinitionReader` 和 `XmlBeanDefinitionReader` 。

从这一段话上，小伙伴有木有愈发强烈的意识到，SpringFramework 对于**组件的单一职责把控的非常好**？`BeanFactory` 作为一个统一管理 Bean 组件的容器，它的核心工作就是**控制 Bean 在创建阶段的生命周期**，而对于 Bean 从哪里来，如何被创建，都有哪些依赖要被注入，这些统统与它无关，而是有专门的组件来处理（就是包括上面提到的 `BeanDefinitionReader` 在内的一些其它组件）。

#### 2.3.4 DefaultListableBeanFactory的替代实现

> For an alternative implementation of the org.springframework.beans.factory.ListableBeanFactory interface, have a look at StaticListableBeanFactory, which manages existing bean instances rather than creating new ones based on bean definitions.
>
> 对于 `ListableBeanFactory` 接口的替代实现，请看一下 `StaticListableBeanFactory` ，它管理现有的 bean 实例，而不是根据 bean 定义创建新的 bean 实例。

这里它提了另一个实现 `StaticListableBeanFactory` ，它实现起来相对简单且功能也简单，因为它只能管理单实例 Bean ，而且没有跟 Bean 定义等相关的高级概念在里面，于是 SpringFramework 默认也不用它。

### 2.4 XmlBeanFactory【了解】

可能到这里部分了解之前背景的小伙伴会有疑问：`XmlBeanFactory` 呢？这个地方咱做一个解释。

在 SpringFramework 3.1 之后，`XmlBeanFactory` 正式被标注为**过时**，代替的方案是使用 `DefaultListableBeanFactory + XmlBeanDefinitionReader` ，这种设计更**符合组件的单一职责原则**，而且还有一点。自打 SpringFramework 3.0 之后出现了注解驱动的 IOC 容器，SpringFramework 就感觉这种 xml 驱动的方式不应该单独成为一种方案了，倒不如咱都各退一步，**搞一个通用的容器，都组合它来用**，这样就实现了**配置源载体分离**的目的了。

到这里，有关 `BeanFactory` 的重要接口扩展和实现，就了解的差不多了。小伙伴一定要对小册里标注【掌握】的内容有一定的认识和理解，最好能转换为自己的语言描述出来。

## 小结与思考

1. 什么是 `BeanFactory` ？`BeanFactory` 都实现了哪些基础功能？
2. 高级 `BeanFactory` 扩展都有哪些重要特性？
3. `BeanFactory` 的实现类为什么要定义模板方法？目的是什么？
4. 最终的 `BeanFactory` 实现是谁？它都具备哪些特性？

【了解了 `BeanFactory` 的相关扩展和实现，接下来就是更复杂的 `ApplicationContext` 了，这部分的内容会更多，小伙伴一定要慢慢吸收】

# 15. IOC进阶-IOC容器的详细对比-ApplicationContext

上一章，咱对 `BeanFactory` 以及它的扩展和重要实现类都作了一定的了解，但咱在第 6 章就说过，推荐使用 `ApplicationContext` 而不是 `BeanFactory` ，因为 `ApplicationContext` 相比较 `BeanFactory` 扩展的实在是太多了：

| Feature                                                      | `BeanFactory` | `ApplicationContext` |
| ------------------------------------------------------------ | ------------- | -------------------- |
| Bean instantiation/wiring —— Bean的实例化和属性注入          | Yes           | Yes                  |
| Integrated lifecycle management —— **生命周期管理**          | No            | Yes                  |
| Automatic `BeanPostProcessor` registration —— **Bean后置处理器的支持** | No            | Yes                  |
| Automatic `BeanFactoryPostProcessor` registration —— **BeanFactory后置处理器的支持** | No            | Yes                  |
| Convenient `MessageSource` access (for internalization) —— **消息转换服务（国际化）** | No            | Yes                  |
| Built-in `ApplicationEvent` publication mechanism —— **事件发布机制（事件驱动）** | No            | Yes                  |



那既然是这样，咱就一定要更深入的了解 `ApplicationContext` 才是。

## 1. ApplicationContext和它的上下辈们

还是跟上一章一样，咱先把关系图摆出来看看：

![img](《从0开始深入学习Spring》/b31a2ee5069f4234abd048c893126ed0~tplv-k3u1fbpfcp-zoom-1.image)

可以发现 `ApplicationContext` 不仅继承了 `BeanFactory` 的两个扩展接口，还继承了其它几个接口，咱都一并来讲解。

### 1.1 ApplicationContext【掌握】

这是主角之一，但它的文档注释却不是很长，咱一起来读一下。

#### 1.1.1 ApplicationContext是SpringFramework最核心接口

> Central interface to provide configuration for an application. This is read-only while the application is running, but may be reloaded if the implementation supports this.
>
> 它是为应用程序提供配置的中央接口。在应用程序运行时，它是只读的，但是如果受支持的话，它可以重新加载。

很言简意赅，`ApplicationContext` 就是中央接口，它就是 SpringFramework 的最最核心。另外它多提了一个概念：**重新加载**，这个概念很关键，咱会在后面介绍 `ApplicationContext` 的抽象实现中着重介绍它。

#### 1.1.2 ApplicationContext组合多个功能接口

> An ApplicationContext provides:
>
> - Bean factory methods for accessing application components. Inherited from ListableBeanFactory.
> - The ability to load file resources in a generic fashion. Inherited from the ResourceLoader interface.
> - The ability to publish events to registered listeners. Inherited from the ApplicationEventPublisher interface.
> - The ability to resolve messages, supporting internationalization. Inherited from the MessageSource interface.
> - Inheritance from a parent context. Definitions in a descendant context will always take priority. This means, for example, that a single parent context can be used by an entire web application, while each servlet has its own child context that is independent of that of any other servlet.
>
> `ApplicationContext` 提供：
>
> - 用于访问应用程序组件的 Bean 工厂方法。继承自 `ListableBeanFactory` 。
> - 以通用方式加载文件资源的能力。继承自 `ResourceLoader` 接口。
> - 能够将事件发布给注册的监听器。继承自 `ApplicationEventPublisher` 接口。
> - 解析消息的能力，支持国际化。继承自 `MessageSource` 接口。
> - 从父上下文继承。在子容器中的定义将始终优先。例如，这意味着整个 Web 应用程序都可以使用单个父上下文，而每个 servlet 都有其自己的子上下文，该子上下文独立于任何其他 servlet 的子上下文。

这一段它列出了 `ApplicationContext` 的核心功能，注意这里面与上面表里面列举的内容有所不同，这里主要介绍的是功能和来源的接口。

这里面有一点需要注意，`ApplicationContext` 也是支持层级结构的，但这里它的描述是**父子上下文**，这个概念要区分理解。**上下文中包含容器，但又不仅仅是容器。容器只负责管理 Bean ，但上下文中还包括动态增强、资源加载、事件监听机制等多方面扩展功能。**

#### 1.1.3 ApplicationContext负责部分回调注入

> In addition to standard BeanFactory lifecycle capabilities, ApplicationContext implementations detect and invoke ApplicationContextAware beans as well as ResourceLoaderAware , ApplicationEventPublisherAware and MessageSourceAware beans.
>
> 除了标准的 `BeanFactory` 生命周期功能外，`ApplicationContext` 实现还检测并调用 `ApplicationContextAware` bean 以及 `ResourceLoaderAware` bean， `ApplicationEventPublisherAware` 和 `MessageSourceAware` bean。

看到这个，可能小伙伴们会有些惊讶，这里面有些 Aware 接口没见过啊，它们也能注入吗？先别着急，往上看看 `ApplicationContext` 继承的接口们：

- `ResourceLoader` → `ResourceLoaderAware`
- `ApplicationEventPublisher` → `ApplicationEventPublisherAware`
- `MessageSource` → `MessageSourceAware`

是不是突然明白了什么？这些 Aware 注入的最终结果还是 **`ApplicationContext`** 本身啊！

### 1.2 ConfigurableApplicationContext【掌握】

与上一章的 `ConfigurableBeanFactory` 类似，它也给 `ApplicationContext` 提供了 **“可写”** 的功能，实现了该接口的实现类可以被客户端代码修改内部的某些配置。下面还是看看文档注释的描述：

#### 1.2.1 ConfigurableApplicationContext提供了可配置的可能

> SPI interface to be implemented by most if not all application contexts. Provides facilities to configure an application context in addition to the application context client methods in the ApplicationContext interface.
>
> 它是一个支持 SPI 的接口，它会被大多数（如果不是全部）应用程序上下文的落地实现。除了 `ApplicationContext` 接口中的应用程序上下文客户端方法外，还提供了用于配置应用程序上下文的功能。

这里又提到 SPI 了，咱回头讲到模块装配时再解释这个概念。后面它又提了，`ConfigurableApplicationContext` 给 `ApplicationContext` 添加了用于配置的功能，这个说法可以从接口方法中得以体现。`ConfigurableApplicationContext` 中扩展了 `setParent` 、`setEnvironment` 、`addBeanFactoryPostProcessor` 、`addApplicationListener` 等方法，都是可以改变 `ApplicationContext` 本身的方法。

#### 1.2.2 ConfigurableApplicationContext只希望被调用启动和关闭

> Configuration and lifecycle methods are encapsulated here to avoid making them obvious to ApplicationContext client code. The present methods should only be used by startup and shutdown code.
>
> 配置和与生命周期相关的方法都封装在这里，以避免暴露给 `ApplicationContext` 的调用者。本接口的方法仅应由启动和关闭代码使用。

由这段话也能明白，`ConfigurableApplicationContext` 本身扩展了一些方法，但是它一般情况下不希望让咱开发者调用，而是只调用启动（refresh）和关闭（close）方法。注意这个一般情况是在程序运行期间的业务代码中，但如果是为了定制化 `ApplicationContext` 或者对其进行扩展，`ConfigurableApplicationContext` 的扩展则会成为切入的主目标。

好了，对于 `ApplicationContext` 的子接口就这一个，但它还实现了几个其他的接口，咱也一起来看看。

### 1.3 EnvironmentCapable【熟悉】

**capable** 本意为“有能力的”，在这里解释为 **“携带/组合”** 更为合适。

**在 SpringFramework 中，以 Capable 结尾的接口，通常意味着可以通过这个接口的某个特定的方法（通常是 `getXXX()` ）拿到特定的组件。**

按照这个概念说法，这个 `EnvironmentCapable` 接口中就应该通过一个 `getEnvironment()` 方法拿到 **`Environment`** ，事实上也确实如此：

```java
public interface EnvironmentCapable {
	Environment getEnvironment();
}
```

下面咱还是看看官方是如何解释这个接口的。

#### 1.3.1 ApplicationContext都具有EnvironmentCapable的功能

> Interface indicating a component that contains and exposes an Environment reference.
>
> All Spring application contexts are EnvironmentCapable, and the interface is used primarily for performing instanceof checks in framework methods that accept BeanFactory instances that may or may not actually be ApplicationContext instances in order to interact with the environment if indeed it is available.
>
> 它是具有获取并公开 `Environment` 引用的接口。
>
> 所有 Spring 的 `ApplicationContext` 都具有 `EnvironmentCapable` 功能，并且该接口主要用于在接受 `BeanFactory` 实例的框架方法中执行 **instanceof** 检查，以便可以与环境进行交互（如果实际上是 `ApplicationContext` 实例）。

从这部分可以知道，`ApplicationContext` 都实现了这个 `EnvironmentCapable` 接口，也就代表着所有的 `ApplicationContext` 的实现类都可以取到 `Environment` 抽象。至于 `Environment` 是什么，咱后面 IOC 高级部分会解释，这里简单解释一下。

`Environment` 是 SpringFramework 中抽象出来的类似于**运行环境**的**独立抽象**，它内部存放着应用程序运行的一些配置。

现阶段小伙伴可以这么理解：基于 SpringFramework 的工程，在运行时包含两部分：**应用程序本身、应用程序的运行时环境**。

#### 1.3.2 ConfigurableApplicationContext可以获取ConfigurableEnvironment

> As mentioned, ApplicationContext extends EnvironmentCapable, and thus exposes a getEnvironment() method; however, ConfigurableApplicationContext redefines getEnvironment() and narrows the signature to return a ConfigurableEnvironment. The effect is that an Environment object is 'read-only' until it is being accessed from a ConfigurableApplicationContext, at which point it too may be configured.
>
> 如上面所述，`ApplicationContext` 扩展了 `EnvironmentCapable` ，因此公开了 `getEnvironment()` 方法；但是，`ConfigurableApplicationContext` 重新定义了 `getEnvironment()` 并缩小了签名范围，以返回 `ConfigurableEnvironment` 。结果是环境对象是 “只读的” ，直到从 `ConfigurableApplicationContext` 访问它为止，此时也可以对其进行配置。

这里又看到 **Configurable** 的概念了，对于**可配置的** `ApplicationContext` ，就可以获取到**可配置的** `Environment` 抽象，这个也不难理解吧。

### 1.4 MessageSource【熟悉】

上面咱也看到了，它是支持国际化的组件。关于国际化的内容，小册计划放到 SpringWebMvc 部分来一起讲解，这里先简单了解下即可。

**国际化，是针对不同地区、不同国家的访问，可以提供对应的符合用户阅读习惯（语言）的页面和数据。**对于不同地区、使用不同语言的用户，需要分别提供对应语言环境的表述。

对于国际化的概念，目前先了解即可。下面看看 SpringFramework 中是如何设计国际化的：

> Strategy interface for resolving messages, with support for the parameterization and internationalization of such messages. Spring provides two out-of-the-box implementations for production:
>
> - org.springframework.context.support.ResourceBundleMessageSource: built on top of the standard java.util.ResourceBundle, sharing its limitations.
> - org.springframework.context.support.ReloadableResourceBundleMessageSource: highly configurable, in particular with respect to reloading message definitions.
>
> 用于解析消息的策略接口，并支持消息的参数化和国际化。SpringFramework 为生产提供了两种现有的实现：
>
> - `ResourceBundleMessageSource`：建立在标准 `java.util.ResourceBundle` 之上，共享其局限性。
> - `ReloadableResourceBundleMessageSource`：高度可配置，尤其是在重新加载消息定义方面。

这里它又提到了关于 Java 原生的国际化，咱都放一放，现阶段只知道 SpringFramework 支持国际化就 OK 。

### 1.5 ApplicationEventPublisher【熟悉】

类名可以理解为，它是**事件的发布器**。SpringFramework 内部支持很强大的事件监听机制，而 ApplicationContext 作为容器的最顶级，自然也要实现观察者模式中**广播器**的角色。文档注释中对于它的描述也是异常的简单：

> Interface that encapsulates event publication functionality. Serves as a super-interface for ApplicationContext.
>
> 封装事件发布功能的接口，它作为 `ApplicationContext` 的父接口。

所以它就是一个很简单的事件发布/广播器而已，后续在 IOC 进阶部分学习事件驱动机制时会讲解它。

### 1.6 ResourcePatternResolver【熟悉】

这个接口可能是这几个扩展里最复杂的一个，从类名理解可以解释为“**资源模式解析器**”，实际上它是**根据特定的路径去解析资源文件**的。从下面的文档注释中，咱就可以深刻的体会 `ResourcePatternResolver` 的作用和扩展。

#### 1.6.1 ResourcePatternResolver是ResourceLoader的扩展

> Strategy interface for resolving a location pattern (for example, an Ant-style path pattern) into Resource objects. This is an extension to the ResourceLoader interface. A passed-in ResourceLoader (for example, an org.springframework.context.ApplicationContext passed in via org.springframework.context.ResourceLoaderAware when running in a context) can be checked whether it implements this extended interface too.
>
> 它是一个策略接口，用于将位置模式（例如，Ant 样式的路径模式）解析为 `Resource` 对象。 这是 `ResourceLoader` 接口的扩展。可以检查传入的 `ResourceLoader`（例如，在上下文中运行时通过 `ResourceLoaderAware` 传入的 `ApplicationContext` ）是否也实现了此扩展接口。

可以发现，它本身还是 `ResourceLoader` 的扩展，`ResourceLoader` 实现最基本的解析，`ResourcePatternResolver` 可以支持 **Ant** 形式的带星号 ( * ) 的路径解析（ Ant 形式会在下面看到）。

#### 1.6.2 ResourcePatternResolver的实现方式有多种

> PathMatchingResourcePatternResolver is a standalone implementation that is usable outside an ApplicationContext, also used by ResourceArrayPropertyEditor for populating Resource array bean properties.
>
> `PathMatchingResourcePatternResolver` 是一个独立的实现，可在 `ApplicationContext` 外部使用，`ResourceArrayPropertyEditor` 使用它来填充 `Resource` 数组中 Bean 属性。

这一段列出了一种 `ResourcePatternResolver` 的独立实现：**基于路径匹配的解析器**，这种扩展实现的特点是会**根据特殊的路径来返回多个匹配到的资源文件**。

#### 1.6.3 ResourcePatternResolver支持的Ant路径模式匹配

> Can be used with any sort of location pattern (e.g. "/WEB-INF/*-context.xml"): Input patterns have to match the strategy implementation. This interface just specifies the conversion method rather than a specific pattern format.
>
> 可以与任何类型的位置模式一起使用（例如 `"/WEB-INF/*-context.xml"` ）：输入模式必须与策略实现相匹配。该接口仅指定转换方法，而不是特定的模式格式。

根据前面的文档注释也知道，它支持的是 Ant 风格的匹配模式，这种模式可以有如下写法：

- `/WEB-INF/*.xml` ：匹配 `/WEB-INF` 目录下的任意 xml 文件
- `/WEB-INF/**/beans-*.xml` ：匹配 `/WEB-INF` 下面任意层级目录的 `beans-` 开头的 xml 文件
- `/**/*.xml` ：匹配任意 xml 文件

可以发现这种写法还是蛮灵活的，小伙伴们可以从网上搜索学习更多关于 Ant 风格的写法，不过常用的写法大概就上面几种，掌握写法即可。

#### 1.6.4 ResourcePatternResolver可以匹配类路径下的文件

> This interface also suggests a new resource prefix "classpath*:" for all matching resources from the class path. Note that the resource location is expected to be a path without placeholders in this case (e.g. "/beans.xml"); JAR files or classes directories can contain multiple files of the same name.
>
> 此接口还为类路径中的所有匹配资源建议一个新的资源前缀 `"classpath*: "`。请注意，在这种情况下，资源位置应该是没有占位符的路径（例如 `"/beans.xml"` ）； jar 文件或类目录可以包含多个相同名称的文件。

文档注释中又提到了 `ResourcePatternResolver` 还可以匹配类路径下的资源文件，方式是在资源路径中加一个 `classpath*:` 的前缀。由此咱也可以知道，`ResourcePatternResolver` 不仅可以匹配 Web 工程中 webapps 的文件，也可以匹配 classpath 下的文件了。

------

到这里，关于 `ApplicationContext` 相关的接口咱就大概都了解了，下面是 `ApplicationContext` 的实现类们，这里面涉及的内容可能比较难记，小伙伴根据我标注的实现类的重要程度来理解和记录即可。

## 2. ApplicationContext的实现类们

同样的，借助 IDEA 整理出一张继承关系图：

![img](《从0开始深入学习Spring》/001fe910c0344849aebe654534b49cca~tplv-k3u1fbpfcp-zoom-1.image)

这里面涉及到的实现类咱一个一个列出来看。

### 2.1 AbstractApplicationContext【掌握*】

这个类是 `ApplicationContext` **最最最最核心的实现类，没有之一**。`AbstractApplicationContext` 中定义和实现了**绝大部分应用上下文的特性和功能**，一定要给它**最大的重视**。

#### 2.1.1 AbstractApplicationContext只构建功能抽象

> Abstract implementation of the ApplicationContext interface. Doesn't mandate the type of storage used for configuration; simply implements common context functionality. Uses the Template Method design pattern, requiring concrete subclasses to implement abstract methods.
>
> `ApplicationContext` 接口的抽象实现。不强制用于配置的存储类型；简单地实现通用上下文功能。使用模板方法模式，需要具体的子类来实现抽象方法。

一开始人家就解释了，`AbstractApplicationContext` 的抽象实现主要是规范功能（借助模板方法），实际的动作它不管，让子类自行去实现。

#### 2.1.2 AbstractApplicationContext可以处理特殊类型的Bean

> In contrast to a plain BeanFactory, an ApplicationContext is supposed to detect special beans defined in its internal bean factory: Therefore, this class automatically registers BeanFactoryPostProcessors, BeanPostProcessors, and ApplicationListeners which are defined as beans in the context.
>
> 与普通的 `BeanFactory` 相比，`ApplicationContext` 应该能够检测在其内部 Bean 工厂中定义的特殊 bean ：因此，此类自动注册在上下文中定义为 bean 的 `BeanFactoryPostProcessors` ，`BeanPostProcessors` 和 `ApplicationListeners` 。

咱在第 6 章就知道，`ApplicationContext` 比 `BeanFactory` 强大的地方是支持更多的机制，这里面就包括了**后置处理器、监听器**等，而这些器，说白了也都是**一个一个的 Bean** ，`BeanFactory` 不会把它们区别对待，但是 `ApplicationContext` 就可以区分出来，并且赋予他们发挥特殊能力的机会。

#### 2.1.3 AbstractApplicationContext可以转换为多种类型

> A MessageSource may also be supplied as a bean in the context, with the name "messageSource"; otherwise, message resolution is delegated to the parent context. Furthermore, a multicaster for application events can be supplied as an "applicationEventMulticaster" bean of type ApplicationEventMulticaster in the context; otherwise, a default multicaster of type SimpleApplicationEventMulticaster will be used.
>
> 一个 `MessageSource` 也可以在上下文中作为一个普通的 bean 提供，名称为 `"messageSource"` 。否则，将消息解析委托给父上下文。此外，可以在上下文中将用于应用程序事件的广播器作为类型为 `ApplicationEventMulticaster` 的 `"applicationEventMulticaster"` bean 提供。否则，将使用类型为 `SimpleApplicationEventMulticaster` 的默认事件广播器。

咱上面看到了，`ApplicationContext` 实现了国际化的接口 `MessageSource` 、事件广播器的接口 `ApplicationEventMulticaster` ，那作为容器，它也会**把自己看成一个 Bean** ，以支持不同类型的组件注入需要。

#### 2.1.4 AbstractApplicationContext提供默认的加载资源文件策略

> Implements resource loading by extending DefaultResourceLoader. Consequently treats non-URL resource paths as class path resources (supporting full class path resource names that include the package path, e.g. "mypackage/myresource.dat"), unless the getResourceByPath method is overridden in a subclass.
>
> 通过扩展 `DefaultResourceLoader` 实现资源加载。因此，除非在子类中覆盖了 `getResourceByPath()` 方法，否则将非 URL 资源路径视为类路径资源（支持包含包路径的完整类路径资源名称，例如 `"mypackage/myresource.dat"` ）。

默认情况下，`AbstractApplicationContext` 加载资源文件的策略是直接继承了 `DefaultResourceLoader` 的策略，从类路径下加载；但在 Web 项目中，可能策略就不一样了，它可以从 `ServletContext` 中加载（扩展的子类 `ServletContextResourceLoader` 等）。

看完了文档，小册在这个章节中多提一句：`AbstractApplicationContext` 中定义了一个特别特别重要的方法，它是控制 `ApplicationContext` 生命周期的核心方法：**`refresh`** 。下面是基本的方法定义，小伙伴们先对此有个印象即可，不需要深入进去看源码。对于源码的执行，小伙伴可以学完这些基础之后，参考《SpringBoot 源码解读与原理分析》的 11-15 章，学习 `refresh` 方法的核心执行。

```java
public void refresh() throws BeansException, IllegalStateException {
    synchronized (this.startupShutdownMonitor) {
        // Prepare this context for refreshing.
        // 1. 初始化前的预处理
        prepareRefresh();

        // Tell the subclass to refresh the internal bean factory.
        // 2. 获取BeanFactory，加载所有xml配置文件中bean的定义信息（未实例化）
        ConfigurableListableBeanFactory beanFactory = obtainFreshBeanFactory();

        // Prepare the bean factory for use in this context.
        // 3. BeanFactory的预处理配置
        prepareBeanFactory(beanFactory);

        try {
            // Allows post-processing of the bean factory in context subclasses.
            // 4. 准备BeanFactory完成后进行的后置处理
            postProcessBeanFactory(beanFactory);

            // Invoke factory processors registered as beans in the context.
            // 5. 执行BeanFactory创建后的后置处理器
            invokeBeanFactoryPostProcessors(beanFactory);

            // Register bean processors that intercept bean creation.
            // 6. 注册Bean的后置处理器
            registerBeanPostProcessors(beanFactory);

            // Initialize message source for this context.
            // 7. 初始化MessageSource
            initMessageSource();

            // Initialize event multicaster for this context.
            // 8. 初始化事件派发器
            initApplicationEventMulticaster();

            // Initialize other special beans in specific context subclasses.
            // 9. 子类的多态onRefresh
            onRefresh();

            // Check for listener beans and register them.
            // 10. 注册监听器
            registerListeners();
          
            //到此为止，BeanFactory已创建完成

            // Instantiate all remaining (non-lazy-init) singletons.
            // 11. 初始化所有剩下的单例Bean
            finishBeanFactoryInitialization(beanFactory);

            // Last step: publish corresponding event.
            // 12. 完成容器的创建工作
            finishRefresh();
        } // catch ......

        finally {
            // Reset common introspection caches in Spring's core, since we
            // might not ever need metadata for singleton beans anymore...
            // 13. 清除缓存
            resetCommonCaches();
        }
    }
}
```

有个印象即可哈，不要深入进去，不然出不来了就没法继续往下愉快的学习了~~~

### 2.2 GenericApplicationContext【熟悉】

咱先从注解驱动的 IOC 容器看起，`GenericApplicationContext` 已经是一个普通的类（非抽象类）了，它里面已经具备了 `ApplicationContext` 基本的所有能力了。咱来看看官方怎么描述它的。

#### 2.2.1 GenericApplicationContext组合了BeanFactory

> Generic ApplicationContext implementation that holds a single internal DefaultListableBeanFactory instance and does not assume a specific bean definition format. Implements the BeanDefinitionRegistry interface in order to allow for applying any bean definition readers to it.
>
> 通用 `ApplicationContext` 的实现，该实现拥有一个内部 `DefaultListableBeanFactory` 实例，并且不采用特定的 bean 定义格式。另外它实现 `BeanDefinitionRegistry` 接口，以便允许将任何 bean 定义读取器应用于该容器中。

注意划重点：**`GenericApplicationContext` 中组合了一个 `DefaultListableBeanFactory` ！！！\**由此可以得到一个非常非常重要的信息：\**`ApplicationContext` 并不是继承了 `BeanFactory` 的容器，而是组合了 `BeanFactory` ！**

然后后面它说了它还实现了 `BeanDefinitionRegistry` 接口，上一章咱简单说了它是 “Bean 定义的注册器”，它与 Bean 的定义信息有关，咱往后放一放。

#### 2.2.2 GenericApplicationContext借助BeanDefinitionRegistry处理特殊Bean

> Typical usage is to register a variety of bean definitions via the BeanDefinitionRegistry interface and then call refresh() to initialize those beans with application context semantics (handling org.springframework.context.ApplicationContextAware, auto-detecting BeanFactoryPostProcessors, etc).
>
> 典型的用法是通过 `BeanDefinitionRegistry` 接口注册各种 Bean 的定义，然后调用 `refresh()` 以使用应用程序上下文语义来初始化这些 Bean（处理 `ApplicationContextAware` ，自动检测 `BeanFactoryPostProcessors` 等）。

这里又看到了 **`BeanDefinitionRegistry`** 了，上一章咱也提了一嘴它叫 **Bean 定义的注册器**，`GenericApplicationContext` 实现了它，可以自定义注册一些 Bean 。然而在 `GenericApplicationContext` 中，它实现的定义注册方法 `registerBeanDefinition` ，在底层还是调用的 `DefaultListableBeanFactory` 执行 `registerBeanDefinition` 方法，说明它也没有对此做什么扩展。

#### 2.2.3 GenericApplicationContext只能刷新一次

> In contrast to other ApplicationContext implementations that create a new internal BeanFactory instance for each refresh, the internal BeanFactory of this context is available right from the start, to be able to register bean definitions on it. refresh() may only be called once.
>
> 与为每次刷新创建一个新的内部 `BeanFactory` 实例的其他 `ApplicationContext` 实现相反，此上下文的内部 `BeanFactory` 从一开始就可用，以便能够在其上注册 Bean 定义。 `refresh()` 只能被调用一次。

这句话不是很好理解，小册换一种说法尝试着解释一下：由于 `GenericApplicationContext` 中组合了一个 `DefaultListableBeanFactory` ，而这个 `BeanFactory` 是在 `GenericApplicationContext` 的**构造方法中就已经初始化好**了，那么初始化好的 `BeanFactory` 就**不允许在运行期间被重复刷新了**。下面是源码中的实现：

```java
public GenericApplicationContext() {
    // 内置的beanFactory在GenericApplicationContext创建时就已经初始化好了
    this.beanFactory = new DefaultListableBeanFactory();
}

protected final void refreshBeanFactory() throws IllegalStateException {
    if (!this.refreshed.compareAndSet(false, true)) {
        // 利用CAS，保证只能设置一次true，如果出现第二次，就抛出重复刷新异常
        throw new IllegalStateException(
                "GenericApplicationContext does not support multiple refresh attempts: just call 'refresh' once");
    }
    this.beanFactory.setSerializationId(getId());
}
```

可如果是这样的话，它的文档注释为什么不直接说就可以呢，还非得加一句“与...相反”，那是因为有另外一类 `ApplicationContext` 它的设计不是这样的，咱下面会讲到，它就是 `AbstractRefreshableApplicationContext` 。

#### 2.2.4 GenericApplicationContext的替代方案是用xml

> For the typical case of XML bean definitions, simply use ClassPathXmlApplicationContext or FileSystemXmlApplicationContext, which are easier to set up - but less flexible, since you can just use standard resource locations for XML bean definitions, rather than mixing arbitrary bean definition formats. The equivalent in a web environment is org.springframework.web.context.support.XmlWebApplicationContext.
>
> 对于 XML Bean 定义的典型情况，只需使用 `ClassPathXmlApplicationContext` 或 `FileSystemXmlApplicationContext` ，因为它们更易于设置（但灵活性较差，因为只能将从标准的资源配置文件中读取 XML Bean 定义，而不能混合使用任意 Bean 定义的格式）。在 Web 环境中，替代方案是 `XmlWebApplicationContext` 。

这段注释它提到了 xml 的配置，咱之前也讲过，**注解驱动的 IOC 容器可以导入 xml 配置文件**，不过如果大多数都是 xml 配置的话，官方建议还是直接用 `ClassPathXmlApplicationContext` 或者 `FileSystemXmlApplicationContext` 就好。对比起灵活度来讲，咱也能清晰地认识到：注解驱动的方式在开发时很灵活，但如果需要修改配置时，可能需要重新编译配置类；xml 驱动的方式在修改配置时直接修改即可，不需要做任何额外的操作，但能配置的内容实在是有些有限。所以这也建议咱开发者在实际开发中，要权衡对比着使用。

#### 2.2.5 GenericApplicationContext不支持特殊Bean定义的可刷新读取

> For custom application context implementations that are supposed to read special bean definition formats in a refreshable manner, consider deriving from the AbstractRefreshableApplicationContext base class.
>
> 对于应该以可刷新方式读取特殊bean定义格式的自定义应用程序上下文实现，请考虑从 `AbstractRefreshableApplicationContext` 基类派生。

这个概念似乎很难理解，咱大可不必在意啦，它是解释怎么扩展自定义 `ApplicationContext` 实现的，咱目前也搞不了这些复杂的东西 ~ ~ ~

不过注意一点，它提到小册在上面刚刚提到的扩展实现 `AbstractRefreshableApplicationContext` 了，可见它的确很重要了，咱下面就来看它。

### 2.3 AbstractRefreshableApplicationContext【熟悉】

类名直译为 “可刷新的 ApplicationContext ”，它跟上面 `GenericApplicationContext` 的最大区别之一就是它**可以被重复刷新**，那它里面的设计肯定也会不一样咯，咱赶紧来看一看吧！

#### 2.3.1 AbstractRefreshableApplicationContext支持多次刷新

> Base class for ApplicationContext implementations which are supposed to support multiple calls to refresh(), creating a new internal bean factory instance every time. Typically (but not necessarily), such a context will be driven by a set of config locations to load bean definitions from.
>
> 它是 `ApplicationContext` 接口实现的抽象父类，应该支持多次调用 `refresh()` 方法，每次都创建一个新的内部 `BeanFactory` 实例。通常（但不是必须）这样的上下文将由一组配置文件驱动，以从中加载 bean 的定义信息。

注释中明确说明了：每次都**会创建一个新的内部的 `BeanFactory` 实例**（也就是 `DefaultListableBeanFactory` ），而整个 `ApplicationContext` 的初始化中不创建。通过源码来看，它的内部也是**组合 `DefaultListableBeanFactory`** ，但构造方法中什么也没有干：

```java
public abstract class AbstractRefreshableApplicationContext extends AbstractApplicationContext {
    @Nullable
    private DefaultListableBeanFactory beanFactory;

    public AbstractRefreshableApplicationContext() {
    }
```

那它是怎么创建 `BeanFactory` 的呢？借助 IDEA 观察方法列表，其中就有一个方法叫 `creatBeanFactory` ：

```java
protected DefaultListableBeanFactory createBeanFactory() {
    return new DefaultListableBeanFactory(getInternalParentBeanFactory());
}
```

很简单明了吧，小册就不多解释了。至于什么时候这个方法被触发了，咱放到后面 IOC 原理阶段再讲解。

#### 2.3.2 AbstractRefreshableApplicationContext刷新的核心是加载Bean定义信息

> The only method to be implemented by subclasses is loadBeanDefinitions, which gets invoked on each refresh. A concrete implementation is supposed to load bean definitions into the given DefaultListableBeanFactory, typically delegating to one or more specific bean definition readers. Note that there is a similar base class for WebApplicationContexts.
>
> 子类唯一需要实现的方法是 `loadBeanDefinitions` ，它在每次刷新时都会被调用。一个具体的实现应该将 bean 的定义信息加载到给定的 `DefaultListableBeanFactory` 中，通常委托给一个或多个特定的 bean 定义读取器。 注意，`WebApplicationContexts` 有一个类似的父类。

这段话告诉我们，既然是可刷新的 `ApplicationContext` ，那它里面存放的 **Bean 定义信息应该是可以被覆盖加载的**。由于 `AbstractApplicationContext` 就已经实现了 `ConfigurableApplicationContext` 接口，容器本身可以重复刷新，那么每次刷新时就应该重新加载 Bean 的定义信息，以及初始化 Bean 实例。

另外它还说，在 Web 环境下也有一个类似的父类，猜都能猜到肯定是名字里多了个 Web ：`AbstractRefreshableWebApplicationContext` ，它的特征与 `AbstractRefreshableApplicationContext` 基本一致，不重复解释。

#### 2.3.3 AbstractRefreshableWebApplicationContext额外扩展了Web环境的功能

> org.springframework.web.context.support.AbstractRefreshableWebApplicationContext provides the same subclassing strategy, but additionally pre-implements all context functionality for web environments. There is also a pre-defined way to receive config locations for a web context.
>
> `AbstractRefreshableWebApplicationContext` 提供了相同的子类化策略，但是还预先实现了 Web 环境的所有上下文功能。还有一种预定义的方式来接收 Web 上下文的配置位置。

与普通的 `ApplicationContext` 相比，`WebApplicationContext` 额外扩展的是与 Servlet 相关的部分（ request 、`ServletContext` 等），`AbstractRefreshableWebApplicationContext` 内部就组合了一个 `ServletContext` ，并且支持给 Bean 注入 `ServletContext` 、`ServletConfig` 等 Servlet 中的组件。

#### 2.3.4 几个重要的最终实现类

> Concrete standalone subclasses of this base class, reading in a specific bean definition format, are ClassPathXmlApplicationContext and FileSystemXmlApplicationContext, which both derive from the common AbstractXmlApplicationContext base class; org.springframework.context.annotation.AnnotationConfigApplicationContext supports @Configuration-annotated classes as a source of bean definitions.
>
> 以特定的 bean 定义格式读取的该父类的具体独立子类是 `ClassPathXmlApplicationContext` 和 `FileSystemXmlApplicationContext` ，它们均从 `AbstractXmlApplicationContext` 基类扩展。 `AnnotationConfigApplicationContext` 支持 `@Configuration` 注解的类作为 `BeanDefinition` 的源。

最后一段它提了几个内置的最终实现类，分别是基于 xml 配置的 `ClassPathXmlApplicationContext` 和 `FileSystemXmlApplicationContext` ，以及基于注解启动的 `AnnotationConfigApplicationContext` 。这些咱已经有了解了，下面也会展开来讲。

### 2.4 AbstractRefreshableConfigApplicationContext【了解】

与上面的 `AbstractRefreshableApplicationContext` 相比较，只是多了一个 **Config** ，说明它有**扩展跟配置相关的特性**。翻看方法列表，可以看到有它自己定义的 `getConfigLocations` 方法，意为“**获取配置源路径**”，由此也就证明它确实有配置的意思了。

它的文档注释就一段话，解释的内容恰好就是上面刚刚说的：

> AbstractRefreshableApplicationContext subclass that adds common handling of specified config locations. Serves as base class for XML-based application context implementations such as ClassPathXmlApplicationContext and FileSystemXmlApplicationContext, as well as org.springframework.web.context.support.XmlWebApplicationContext.
>
> `AbstractRefreshableApplicationContext` 的子类，用于添加对指定配置位置的通用处理。作为基于 XML 的 `ApplicationContext` 实现（例如`ClassPathXmlApplicationContext` 、 `FileSystemXmlApplicationContext` 以及 `XmlWebApplicationContext` ）的父类。

通篇就抽出来一句话：用于添加对指定配置位置的通用处理。由于它是基于 xml 配置的 `ApplicationContext` 的父类，所以肯定需要传入配置源路径，那这个配置的动作就封装在这个 `AbstractRefreshableConfigApplicationContext` 中了。

### 2.5 AbstractXmlApplicationContext【掌握】

到这里，xml 终于浮出水面了，它就是最终 `ClassPathXmlApplicationContext` 和 `FileSystemXmlApplicationContext` 的直接父类了。

跟前面一样，先看一眼文档注释，这段注释也不算很长：

#### 2.5.1 AbstractXmlApplicationContext已具备基本全部功能

> Convenient base class for ApplicationContext implementations, drawing configuration from XML documents containing bean definitions understood by an XmlBeanDefinitionReader. Subclasses just have to implement the getConfigResources and/or the getConfigLocations method. Furthermore, they might override the getResourceByPath hook to interpret relative paths in an environment-specific fashion, and/or getResourcePatternResolver for extended pattern resolution.
>
> 方便的 `ApplicationContext` 父类，从包含 `XmlBeanDefinitionReader` 解析的 `BeanDefinition` 的 XML 文档中提取配置。
>
> 子类只需要实现 `getConfigResources` 和/或 `getConfigLocations` 方法。此外，它们可能会覆盖 `getResourceByPath` 的钩子回调，以特定于环境的方式解析相对路径，和/或 `getResourcePatternResolver` 来扩展模式解析。

看上去有点难懂，小册大概解释一下意思哈。

由于 `AbstractXmlApplicationContext` 已经接近于最终的 xml 驱动 IOC 容器的实现了，所以它应该有基本上所有的功能。又根据子类的两种不同的配置文件加载方式，说明**加载配置文件的策略是不一样的**，所以文档注释中有说子类只需要实现 `getConfigLocations` 这样的方法就好。

对于 `AbstractXmlApplicationContext` ，还有一个非常关键的部分需要咱知道，那就是加载到配置文件后如何处理。

#### 2.5.2 AbstractXmlApplicationContext中有loadBeanDefinitions的实现

定位到源码中，可以在 `AbstractXmlApplicationContext` 中找到 `loadBeanDefinitions` 的实现：

```java
@Override
protected void loadBeanDefinitions(DefaultListableBeanFactory beanFactory) throws BeansException, IOException {
    // Create a new XmlBeanDefinitionReader for the given BeanFactory.
    // 借助XmlBeanDefinitionReader解析xml配置文件
    XmlBeanDefinitionReader beanDefinitionReader = new XmlBeanDefinitionReader(beanFactory);

    // Configure the bean definition reader with this context's
    // resource loading environment.
    beanDefinitionReader.setEnvironment(this.getEnvironment());
    beanDefinitionReader.setResourceLoader(this);
    beanDefinitionReader.setEntityResolver(new ResourceEntityResolver(this));

    // Allow a subclass to provide custom initialization of the reader,
    // then proceed with actually loading the bean definitions.
    // 初始化BeanDefinitionReader，后加载BeanDefinition
    initBeanDefinitionReader(beanDefinitionReader);
    loadBeanDefinitions(beanDefinitionReader);
}
```

可以看到，它解析 xml 配置文件不是自己干活，是**组合了一个 `XmlBeanDefinitionReader`** ，让它去解析。而实际解析配置文件的动作，就很好理解了：

```java
protected void loadBeanDefinitions(XmlBeanDefinitionReader reader) throws BeansException, IOException {
    Resource[] configResources = getConfigResources();
    if (configResources != null) {
        reader.loadBeanDefinitions(configResources);
    }
    String[] configLocations = getConfigLocations();
    if (configLocations != null) {
        reader.loadBeanDefinitions(configLocations);
    }
}
```

可以看到就是调用上面文档注释中提到的 `getConfigResources` 和 `getConfigLocations` 方法，取到配置文件的路径 / 资源类，交给 `BeanDefinitionReader` 解析。

### 2.6 ClassPathXmlApplicationContext【掌握】

终于到了一个咱非常熟悉的 `ApplicationContext` 了，咱已经很清楚它是从 classpath 下加载 xml 配置文件的 `ApplicationContext` 了，不过文档注释中也描述了一些内容和建议，咱还是要看一看的。

#### 2.6.1 ClassPathXmlApplicationContext是一个最终落地实现

> Standalone XML application context, taking the context definition files from the class path, interpreting plain paths as class path resource names that include the package path (e.g. "mypackage/myresource.txt"). Useful for test harnesses as well as for application contexts embedded within JARs.
>
> 独立的基于 XML 的 `ApplicationContext` ，它从 classpath 中获取配置文件，将纯路径解释为包含包路径的 classpath 资源名称（例如 `mypackage / myresource.txt` ）。对于测试工具以及 jar 包中嵌入的 `ApplicationContext` 很有用。

这段话写的很明白，它支持的配置文件加载位置都是 classpath 下取，这种方式的一个好处是：如果工程中依赖了一些其他的 jar 包，而工程启动时需要同时传入这些 jar 包中的配置文件，那 `ClassPathXmlApplicationContext` 就可以加载它们。

#### 2.6.2 ClassPathXmlApplicationContext使用Ant模式声明配置文件路径

> The config location defaults can be overridden via getConfigLocations, Config locations can either denote concrete files like "/myfiles/context.xml" or Ant-style patterns like "/myfiles/*-context.xml" (see the org.springframework.util.AntPathMatcher javadoc for pattern details).
>
> 可以通过 `getConfigLocations` 方法覆盖配置文件位置的默认值，配置位置可以表示具体的文件，例如 `/myfiles/context.xml` ，也可以表示Ant样式的模式，例如 `/myfiles/*-context.xml`（请参见 `AntPathMatcher` 的 javadoc 以获取模式详细信息）。

上面 `AbstractXmlApplicationContext` 中就说了，可以重写 `getConfigLocations` 方法来调整配置文件的默认读取位置，它这里又重复了一遍。除此之外它还提到了，加载配置文件的方式可以**使用 Ant 模式匹配**（比较经典的写法当属 web.xml 中声明的 `application-*.xml` ）。

#### 2.6.3 ClassPathXmlApplicationContext解析的配置文件有先后之分

> Note: In case of multiple config locations, later bean definitions will override ones defined in earlier loaded files. This can be leveraged to deliberately override certain bean definitions via an extra XML file.
>
> 注意：如果有多个配置位置，则较新的 `BeanDefinition` 会覆盖较早加载的文件中的 `BeanDefinition` ，可以利用它来通过一个额外的 XML 文件有意覆盖某些 `BeanDefinition` 。

这一点是配合第一点的多配置文件读取来的。通常情况下，如果在一个 jar 包的 xml 配置文件中声明了一个 Bean ，并且又在工程的 resources 目录下又声明了同样的 Bean ，则 jar 包中声明的 Bean 会被覆盖，这也就是配置文件加载优先级的设定。

#### 2.6.4 ApplicationContext可组合灵活使用

> This is a simple, one-stop shop convenience ApplicationContext. Consider using the GenericApplicationContext class in combination with an org.springframework.beans.factory.xml.XmlBeanDefinitionReader for more flexible context setup.
>
> 这是一个简单的一站式便利 `ApplicationContext` 。可以考虑将 `GenericApplicationContext` 类与 `XmlBeanDefinitionReader` 结合使用，以实现更灵活的上下文配置。

最后文档中并没有非常强调 `ClassPathXmlApplicationContext` 的作用，而是提了另外一个建议：由于 `ClassPathXmlApplicationContext` 继承了 `AbstractXmlApplicationContext` ，而 `AbstractXmlApplicationContext` 实际上是内部组合了一个 `XmlBeanDefinitionReader` ，所以就可以有一种组合的使用方式：利用 `GenericApplicationContext` 或者子类 `AnnotationConfigApplicationContext` ，配合 `XmlBeanDefinitionReader` ，就可以做到注解驱动和 xml 通吃了。

### 2.7 AnnotationConfigApplicationContext【掌握】

最后一个，咱介绍一个也用过很多次的了，就是注解驱动的 IOC 容器。它本身继承了 `GenericApplicationContext` ，那自然它也只能刷新一次。同样是最终的落地实现，它自然也应该跟 `ClassPathXmlApplicationContext` 类似的有一些特征，下面咱来看看。

#### 2.7.1 AnnotationConfigApplicationContext是一个最终落地实现

> Standalone application context, accepting component classes as input — in particular @Configuration-annotated classes, but also plain @Component types and JSR-330 compliant classes using javax.inject annotations.
>
> 独立的注解驱动的 `ApplicationContext` ，接受组件类作为输入，特别是使用 `@Configuration` 注解的类，还可以使用普通的 `@Component` 类型和符合 JSR-330 规范（使用 `javax.inject` 包的注解）的类。

注解驱动，除了 `@Component` 及其衍生出来的几个注解，更重要的是 `@Configuration` 注解，一个被 `@Configuration` 标注的类相当于一个 xml 文件。至于下面还提到的关于 JSR-330 的东西，它没有类似于 `@Component` 的东西（它只是定义了依赖注入的标准，与组件注册无关），它只是说如果一个组件 Bean 里面有 JSR-330 的注解，那它能给解析而已。

#### 2.7.2 AnnotationConfigApplicationContext解析的配置类也有先后之分

> Allows for registering classes one by one using register(Class...) as well as for classpath scanning using scan(String...). In case of multiple @Configuration classes, @Bean methods defined in later classes will override those defined in earlier classes. This can be leveraged to deliberately override certain bean definitions via an extra @Configuration class.
>
> 允许使用 `register(Class ...)` 一对一注册类，以及使用 `scan(String ...)` 进行类路径的包扫描。 如果有多个 `@Configuration` 类，则在以后的类中定义的 `@Bean` 方法将覆盖在先前的类中定义的方法。这可以通过一个额外的 `@Configuration` 类来故意覆盖某些 `BeanDefinition` 。

这个操作就跟上面 `ClassPathXmlApplicationContext` 如出一辙了，它也有配置覆盖的概念。除此之外，它上面还说了初始化的两种方式：要么注册配置类，要么直接进行包扫描。由于注解驱动开发中可能没有一个主配置类，都是一上来就一堆 `@Component` ，这个时候完全可以直接声明根扫描包，进行组件扫描。

有关 `FileSystemXmlApplicationContext` ，以及 Web 环境下扩展的 `ApplicationContext` ，本章不作更多的解析，小伙伴们可以举一反三，根据现有已经了解的知识，对比学习其它的一些 IOC 容器的实现。

## 小结与思考

1. 什么是 `ApplicationContext` ？它与 `BeanFactory` 的关系是什么？
2. `ApplicationContext` 相比较 `BeanFactory` 都扩展了哪些特性？
3. `ApplicationContext` 与 `BeanFactory` 是如何联系起来的？
4. 最终落地实现的 `ApplicationContext` 都应该具备哪些核心特性？

【到这里，`ApplicationContext` 相关的容器类也就全部了解了，容器类也就到此结束了。接下来，咱会介绍更多 SpringFramework 中的进阶使用】

# 16. IOC进阶-事件机制&监听器

接下来的几章，介绍的都是 SpringFramework 中的一些进阶的功能 / 特性，这些特性在平时开发不一定全部用得上，但想熟练掌握 SpringFramework 的开发，这些知识点还是非常有必要的。

> 本章源码均在 `com.linkedbear.spring.event`

本章咱来学习事件驱动和监听器。说到事件和监听器，小伙伴们最先想到的估计就是观察者模式了吧。下面咱先快速回顾一下观察者模式。

## 1. 观察者模式【回顾】

**观察者模式**，也被称为**发布订阅模式**，也有的人叫它**“监听器模式”**，它是 GoF23 设计模式中行为型模式的其中之一。观察者模式关注的点是某**一个对象被修改 / 做出某些反应 / 发布一个信息等，会自动通知依赖它的对象（订阅者）**。

观察者模式的三大核心是：**观察者、被观察主题、订阅者**。观察者（ Observer ）需要绑定要通知的订阅者（ Subscriber ），并且要观察指定的主题（ Subject ）。

## 2. SpringFramework中设计的观察者模式【掌握】

SpringFramework 中，体现观察者模式的特性就是事件驱动和监听器。**监听器**充当**订阅者**，监听特定的事件；**事件源**充当**被观察的主题**，用来发布事件；**IOC 容器**本身也是事件广播器，可以理解成**观察者**。

不过我个人比较喜欢把 SpringFramework 的事件驱动核心概念划分为 4 个：**事件源、事件、广播器、监听器**。

- **事件源：发布事件的对象**

- **事件：事件源发布的信息 / 作出的动作**

- 广播器：事件真正广播给监听器的对象

  【即

   

  `ApplicationContext`

   

  】

  - `ApplicationContext` 接口有实现 `ApplicationEventPublisher` 接口，具备**事件广播器的发布事件的能力**
  - `ApplicationEventMulticaster` 组合了所有的监听器，具备**事件广播器的广播事件的能力**

- **监听器：监听事件的对象**

也许这样理解起来会更容易一些：

![img](《从0开始深入学习Spring》/d2d55f5256e448248c39e00482fa4396~tplv-k3u1fbpfcp-zoom-1.image)

## 3. 快速体会事件与监听器【掌握】

下面咱先通过一个最简单的实例来体会 SpringFramework 中监听器的使用。

### 3.1 编写监听器

SpringFramework 中内置的监听器接口是 `ApplicationListener` ，它还带了一个泛型，代表要监听的具体事件：

```java
@FunctionalInterface
public interface ApplicationListener<E extends ApplicationEvent> extends EventListener {
	void onApplicationEvent(E event);
}
```

我们要自定义监听器，只需要实现这个 `ApplicationListener` 接口即可。

为快速体会事件和监听器的功能，下面咱先介绍两个事件：`ContextRefreshedEvent` 和 `ContextClosedEvent` ，它们分别代表**容器刷新完毕**和**即将关闭**。下面咱编写一个监听器，来监听 `ContextRefreshedEvent` 事件。

```java
@Component
public class ContextRefreshedApplicationListener implements ApplicationListener<ContextRefreshedEvent> {
    
    @Override
    public void onApplicationEvent(ContextRefreshedEvent event) {
        System.out.println("ContextRefreshedApplicationListener监听到ContextRefreshedEvent事件！");
    }
}
```

记得用 `@Component` 注解标注监听器哦，一会要进行包扫描的。监听器必须要注册到 SpringFramework 的 IOC 容器才可以生效。

### 3.2 编写启动类

写好监听器，就可以编写启动类，驱动 IOC 容器来测试效果了。这个时候可能有小伙伴有点懵：我去，我思想工作还没建设好呢，这就完事了？然而真的就是这么回事，下面代码一写你就恍然大悟了。

```java
public class QuickstartListenerApplication {
    
    public static void main(String[] args) throws Exception {
        System.out.println("准备初始化IOC容器。。。");
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                "com.linkedbear.spring.event.a_quickstart");
        System.out.println("IOC容器初始化完成。。。");
        ctx.close();
        System.out.println("IOC容器关闭。。。");
    }
}
```

哈哈，不会真的有小伙伴忘了 `AnnotationConfigApplicationContext` 可以直接传包扫描路径吧，不会吧不会吧！（狗头保命）

运行 `main` 方法，控制台会根据流程依次打印如下信息：

```
准备初始化IOC容器。。。
ContextRefreshedApplicationListener监听到ContextRefreshedEvent事件！
IOC容器初始化完成。。。
IOC容器关闭。。。
```

### 3.3 注解式监听器

除了实现 `ApplicationListener` 接口之外，还可以使用注解的形式注册监听器。

使用注解式监听器，组件不再需要实现任何接口，而是直接在需要作出事件反应的方法上标注 `@EventListener` 注解即可：

```java
@Component
public class ContextClosedApplicationListener {
    
    @EventListener
    public void onContextClosedEvent(ContextClosedEvent event) {
        System.out.println("ContextClosedApplicationListener监听到ContextClosedEvent事件！");
    }
}
```

重新运行 `QuickstartListenerApplication` 的 `main` 方法，控制台可以打印出 `ContextClosedApplicationListener` 监听事件的反应：

```
准备初始化IOC容器。。。
ContextRefreshedApplicationListener监听到ContextRefreshedEvent事件！
IOC容器初始化完成。。。
ContextClosedApplicationListener监听到ContextClosedEvent事件！
IOC容器关闭。。。
```

由这两种监听器的 Demo ，可以得出几个结论：

- `ApplicationListener` 会在容器初始化阶段就准备好，在容器销毁时一起销毁；
- `ApplicationListener` 也是 IOC 容器中的普通 Bean ；
- IOC 容器中有内置的一些事件供我们监听。

## 4. SpringFramework中的内置事件【熟悉】

在 SpringFramework 中，已经有事件的默认抽象，以及 4 个默认的内置事件了，下面咱了解一下它们。

### 4.1 ApplicationEvent

很明显，它是事件模型的抽象，它是一个抽象类，里面也没有定义什么东西，只有事件发生时的时间戳。值得关注的是，它是继承自 jdk 原生的观察者模式的事件模型，并且把它声明为抽象类：

```java
public abstract class ApplicationEvent extends EventObject
```

关于这个设计，它的文档注释就已经说明了：

> Class to be extended by all application events. Abstract as it doesn't make sense for generic events to be published directly.
>
> 由所有应用程序事件扩展的类。它被设计为抽象的，因为**直接发布一般事件没有意义**。

如果说只是有这么一个派生，那看上去没什么太大的意义，所以 SpringFramework 中又给这个 ApplicationEvent 进行了一次扩展。

### 4.2 ApplicationContextEvent

先看一眼源码，从这里面或许就能意识到什么：

```java
public abstract class ApplicationContextEvent extends ApplicationEvent {
    
	public ApplicationContextEvent(ApplicationContext source) {
		super(source);
	}
    
	public final ApplicationContext getApplicationContext() {
		return (ApplicationContext) getSource();
	}
}
```

它在构造时，会把 IOC 容器一起传进去，这意味着事件发生时，可以**通过监听器直接取到 `ApplicationContext` 而不需要做额外的操作**，这才是 SpringFramework 中事件模型扩展最值得的地方。下面列举的几个内置的事件，都是基于这个 `ApplicationContextEvent` 扩展的。

### 4.3 ContextRefreshedEvent&ContextClosedEvent

这两个是一对，分别对应着 **IOC 容器刷新完毕但尚未启动**，以及 **IOC 容器已经关闭但尚未销毁所有 Bean** 。这个时机可能记起来有点小困难，小伙伴们可以不用记很多，只通过字面意思能知道就 OK ，至于这些事件触发的真正时机，在我的 SpringBoot 源码小册第 16 章中有提到，感兴趣的小伙伴可以去看一看。在后面的 IOC 原理篇中，这部分也会略有涉及。

### 4.4 ContextStartedEvent&ContextStoppedEvent

这一对跟上面的时机不太一样了。`ContextRefreshedEvent` 事件的触发是所有单实例 Bean 刚创建完成后，就发布的事件，此时那些实现了 `Lifecycle` 接口的 Bean 还没有被回调 `start` 方法。当这些 `start` 方法被调用后，`ContextStartedEvent` 才会被触发。同样的，`ContextStoppedEvent` 事件也是在 `ContextClosedEvent` 触发之后才会触发，此时单实例 Bean 还没有被销毁，要先把它们都停掉才可以释放资源，销毁 Bean 。

## 5. 自定义事件开发【熟悉】

上面咱了解了 SpringFramework 中内置的事件，如果我们想自己在合适的时机发布一些事件，让指定的监听器来以此作出反应，执行特定的逻辑，那就需要自定义事件了。下面咱模拟一个场景，来体会自定义事件的开发过程。

本节可能会使人产生不适感，请做好心理准备再继续往下阅读 **-.-**

### 5.1 场景概述

论坛应用，当新用户注册成功后，会同时发送短信、邮件、站内信，通知用户注册成功，并且发放积分。

在这个场景中，用户注册成功后，广播一个“用户注册成功”的事件，将用户信息带入事件广播出去，发送短信、邮件、站内信的监听器监听到注册成功的事件后，会分别执行不同形式的通知动作。

### 5.2 自定义用户注册成功事件

SpringFramework 中的自定义事件的方式就是通过继承 `ApplicationEvent` ：

```java
/**
 * 注册成功的事件
 */
public class RegisterSuccessEvent extends ApplicationEvent {
    
    public RegisterSuccessEvent(Object source) {
        super(source);
    }
}
```

对，没了，这样写就 OK 。

### 5.3 编写监听器

使用上述的两种方式，分别编写发送短信、发送邮件，和发送站内信的监听器：

```java
@Component
public class SmsSenderListener implements ApplicationListener<RegisterSuccessEvent> {
    
    @Override
    public void onApplicationEvent(RegisterSuccessEvent event) {
        System.out.println("监听到用户注册成功，发送短信。。。");
    }
}
@Component
public class EmailSenderListener {
    
    @EventListener
    public void onRegisterSuccess(RegisterSuccessEvent event) {
        System.out.println("监听到用户注册成功！发送邮件中。。。");
    }
}
@Component
public class MessageSenderListener {
    
    @EventListener
    public void onRegisterSuccess(RegisterSuccessEvent event) {
        System.out.println("监听到用户注册成功，发送站内信。。。");
    }
}
```

### 5.4 编写注册逻辑业务层

只有事件和监听器还不够，还需要有一个事件源来持有事件发布器，在应用上下文中发布事件。

Service 层中，需要注入 `ApplicationEventPublisher` 来发布事件，此处选择使用回调注入的方式。

```java
@Service
public class RegisterService implements ApplicationEventPublisherAware {
    
    ApplicationEventPublisher publisher;
    
    public void register(String username) {
        // 用户注册的动作。。。
        System.out.println(username + "注册成功。。。");
        // 发布事件
        publisher.publishEvent(new RegisterSuccessEvent(username));
    }
    
    @Override
    public void setApplicationEventPublisher(ApplicationEventPublisher publisher) {
        this.publisher = publisher;
    }
}
```

### 5.5 编写测试启动类

测试代码都准备好了，下面咱就来写一把启动类，模拟一次用户注册。

```java
public class RegisterEventApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                "com.linkedbear.spring.event.b_registerevent");
        RegisterService registerService = ctx.getBean(RegisterService.class);
        registerService.register("张大三");
    }
}
```

运行 `main` 方法，控制台打印出注册动作，以及监听器的触发反应：

```
张大三注册成功。。。
监听到用户注册成功，发送邮件中。。。
监听到用户注册成功，发送站内信。。。
监听到用户注册成功，发送短信。。。
```

由此又得出来另外一个结论：**注解式监听器的触发时机比接口式监听器早**。

### 5.6 调整监听器的触发顺序

如果业务需要调整，需要先发送站内信，后发送邮件，这个时候就需要配合另外一个注解了：**`@Order`** 。标注上这个注解后，默认的排序值为 **`Integer.MAX_VALUE`** ，代表**最靠后**。

按照这个规则，那咱在 `MessageSenderListener` 的 `onRegisterSuccess` 方法上标注 `@Order(0)` ，重新运行启动类的 `main` 方法，观察控制台的打印：

```
张大三注册成功。。。
监听到用户注册成功，发送站内信。。。
监听到用户注册成功，发送邮件中。。。
监听到用户注册成功，发送短信。。。
```

需求得以解决。不过这个时候我们再思考一个问题：如果不标注 `@Order` 注解，默认的顺序是多少呢？

尝试着把刚才的 `@Order` 注解中，`value` 改为 `Integer.MAX_VALUE - 1` ，重新运行，发现运行结果还是像上面那样打印，证明**默认的排序值是 `Integer.MAX_VALUE`** 。

### 5.7 理性看待自定义事件

到这里，估计部分小伙伴快看不下去了，这有点多此一举呀！我完全可以用一个监听器搞三个方法一块写就完了呀！甚至，完全可以把发送信息、邮件的动作，整合在注册的逻辑中。那这自定义事件到底有什么刚需吗？讲道理，**真的非常少**。很多场景下，使用自定义事件可以处理的逻辑，完全可以通过一些其它的方案来替代，这样真的会显得自定义事件很鸡肋。所以，一定要理性看待自定义事件的使用，千万不要一学到点东西，就疯狂输出哦 (￣▽￣)／。

## 小结与练习

1. 什么是事件驱动？SpringFramework 中的事件和监听器模型是什么？
2. SpringFramework 中有几个内置的事件？
3. 自行实现一个自定义事件，体会两种监听器的开发方式。

【事件和监听器的难度整体不大，当然使用的地方也不很多。下面咱继续介绍更多 SpringFramework 的进阶特性】

# 17. IOC进阶-模块装配

接下来的两章，咱来介绍关于 IOC 进阶部分，模块装配与条件装配的使用。这一部分相当重要，对于以后学习 SpringBoot 的核心**自动装配**有巨大的帮助（ **SpringBoot 的自动装配，基础就是模块装配 + 条件装配**），小伙伴们一定要好好学习这两章呀。

> 如果小伙伴之前有学习或接触过 SSH 或者 SSM 的框架整合，应该还记得那些配置文件有多烦吧，又多又不好记真的很让人头大。在处理配置文件的同时，小伙伴是否有想过：如果能有一种方式，可以使用很少的配置，甚至不配置就可以完成一个功能的装载，那岂不是省了很多事？这个疑问在 SpringBoot 中得以解决，而这个解决的核心技术就是模块装配 + 条件装配。

注：本章所有代码均使用**注解驱动开发**。

> 本章源码均在 `com.linkedbear.spring.configuration.a_module`

## 1. 原生手动装配【回顾】

在最原始的 SpringFramework 中，是不支持注解驱动开发的（当时最低支持版本是 1.3 、1.4 ），直到 SpringFramework 2.0 版本，才初步出现了模式注解（ `@Repository` ），到了 SpringFramework 2.5 出现了 `@Component` 和它的几个派生注解，到了 SpringFramework 3.0 才完全的支持注解驱动开发（当时最低支持版本已经升级到 1.5）。

使用 `@Configuration` + `@Bean` 注解组合，或者 `@Component` + `@ComponentScan` 注解组合，可以实现编程式 / 声明式的手动装配。这两种方式咱前面已经写过很多了，不再赘述。

不过，咱思考一个问题：如果使用这两种方式，如果要注册的 Bean 很多，要么一个一个的 `@Bean` 编程式写，要么就得选好包进行组件扫描，而且这种情况还得每个类都标注好 `@Component` 或者它的衍生注解才行。面对数量很多的 Bean ，这种装配方式很明显会比较麻烦，需要有一个新的解决方案。

## 2. 模块装配【掌握】

SpringFramework 3.0 的发布，全面支持了注解驱动开发，随之而来的就是快速方便的模块装配。在正式了解模块装配之前，咱先思考一个问题。

### 2.1 什么是模块【理解】

通常理解下，模块可以理解成一个一个的可以分解、组合、更换的独立的单元，模块与模块之间可能存在一定的依赖，模块的内部通常是高内聚的，一个模块通常都是解决一个独立的问题（如引入事务模块是为了解决数据库操作的最终一致性）。其实按照这个理解来看，我们平时写的一个一个的功能，也可以看成一个个的模块；封装的一个个组件，可以看做是模块。

简单总结下，模块通常具有以下几个特征：

- 独立的
- 功能高内聚
- 可相互依赖
- 目标明确

### 2.2 什么是模块装配【掌握】

明确了模块的定义，下面就可以思考下一个问题了：什么是模块装配？

既然模块是功能单元，那模块装配，就可以理解为**把一个模块需要的核心功能组件都装配好**，当然如果能有尽可能简便的方式那最好。

### 2.3 SpringFramework中的模块装配【了解】

SpringFramework 中的模块装配，是在 **3.1** 之后引入大量 **`@EnableXXX`** 注解，来快速整合激活相对应的模块。

从现在 5.x 的官方文档中已经很难找到 `@EnableXXX` 的介绍了，小伙伴们可以回溯到 SpringFramework 3.1.0 的官方文档：

[docs.spring.io/spring/docs…](https://docs.spring.io/spring/docs/3.1.0.RELEASE/reference/htmlsingle/)

在 3.1.5 节中，它有介绍 `@EnableXXX` 注解的使用，并且它还举了不少例子，这里面不乏有咱可能熟悉的：

- `EnableTransactionManagement `：开启注解事务驱动
- `EnableWebMvc` ：激活 SpringWebMvc
- `EnableAspectJAutoProxy` ：开启注解 AOP 编程
- `EnableScheduling` ：开启调度功能（定时任务）

这些内容，咱在后面的学习中都会慢慢遇到的，小伙伴们没有必要现在就搞明白这些注解都是干嘛用的，一步一个脚印学习就好。

下面，咱先来体会一下最简单的模块装配。

### 2.4 快速体会模块装配【掌握】

先记住使用模块装配的核心原则：**自定义注解 + `@Import` 导入组件。**

#### 2.4.1 模块装配场景概述

下面咱构建一个场景：使用代码模拟构建出一个**酒馆**，酒馆里得有**吧台**，得有**调酒师**，得有**服务员**，还得有**老板**。这里面具体的设计咱不过多深入，小伙伴自己练习时可以自由发挥。

在这个场景中，`ApplicationContext` 看作一个酒馆，酒馆里的吧台、调酒师、服务员、老板，这些元素统统看作一个一个的**组件**。咱用代码模拟实现的最终目的，是可以**通过一个注解，同时把这些元素都填充到酒馆中**。

目的明确了，下面就开始动手吧。一开始咱先实现最简单的装配方式。

#### 2.4.2 声明自定义注解

既然是酒馆，那咱仿照着 SpringFramework 的写法，咱就来一个 **`@EnableTavern`** 吧！

```java
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.TYPE)
public @interface EnableTavern {
    
}
```

注意注解上面要标注三个元注解，代表它在运行时起效，并且只能标注在类上。

还没完事，模块装配需要一个最核心的注解是 **`@Import`** ，它要标注在 `@EnableTavern` 上。不过这个 `@Import` 中需要传入 `value` 值，点开看一眼它的源码吧：

```java
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Documented
public @interface Import {

	/**
	 * {@link Configuration @Configuration}, {@link ImportSelector},
	 * {@link ImportBeanDefinitionRegistrar}, or regular component classes to import.
	 */
	Class<?>[] value();
}
```

看，文档注释已经写得非常明白了：它可以导入**配置类**、**`ImportSelector` 的实现类**，**`ImportBeanDefinitionRegistrar` 的实现类**，或者**普通类**。咱这里先来快速上手，所以咱先选择使用**普通类**导入。

#### 2.4.3 声明老板类

既然先导入普通类，那咱就来整一个老板的类吧，毕竟酒馆必须有老板经营才是呀！

```java
public class Boss {

}
```

没了，这点代码就够了，连 `@Component` 注解都不用标注。

然后！咱在上面 `@EnableTavern` 的 `@Import` 注解中，填入 Boss 的类：

```java
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.TYPE)
@Import(Boss.class)
public @interface EnableTavern {
    
}
```

这样就代表，如果**标注了 `@EnableTavern` 注解，就会触发 `@Import` 的效果，向容器中导入一个 `Boss` 类型的 Bean** 。

#### 2.4.4 创建配置类

注解驱动，自然少不了配置类。咱声明一个 `TavernConfiguration` 的配置类，并在类上标注 `@Configuration` 和 `@EnableTavern` 注解：

```java
@Configuration
@EnableTavern
public class TavernConfiguration {
    
}
```

配置类中什么都不用写，只要标注好注解即可。

#### 2.4.5 编写启动类测试

下面就可以编写启动类测试装配的效果了，咱新建一个 `TavernApplication` ，并用刚写的 `TavernConfiguration` 驱动初始化 IOC 容器：

```java
public class TavernApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(TavernConfiguration.class);
        Boss boss = ctx.getBean(Boss.class);
        System.out.println(boss);
    }
}
```

运行 `main` 方法，可以发现使用 `getBean` 能够正常取到 `Boss` 的对象，说明 `Boss` 类已经被注册到 IOC 容器生成了一个对象。

```java
com.linkedbear.spring.configuration.a_module.component.Boss@b9afc07
```

这样我们就完成了最简单的模块装配。

这个时候可能有小伙伴开始不耐烦了：我去原本我可以用 `@Configuration` + `@Bean` 就能完事的，你非得给我整这么一堆，这不是**徒增功耗**吗？别着急，往上翻一翻 `@Import` 可以传入的东西，是不是发现普通类是最简单的呀？下面咱就来学习剩下几种更复杂的方式。

### 2.5 模块装配的四种方式【掌握】

#### 2.5.1 导入普通类

上面的方式就是导入普通类。

#### 2.5.2 导入配置类

如果需要直接导入一些现有的配置类，使用 `@Import` 也可以直接加载进来。下面咱来把调酒师搞定。

##### 2.5.2.1 声明调酒师类

调酒师的模型，咱加一个 **`name`** 的属性吧，暗示着咱要搞不止一个调酒师咯：

```java
public class Bartender {
    
    private String name;
    
    public Bartender(String name) {
        this.name = name;
    }
    
    public String getName() {
        return name;
    }
}
```

##### 2.5.2.2 注册调酒师的对象

如果要注册多个相同类型的 Bean ，现在咱能想到的办法就是通过配置类了。下面咱编写一个 `BartenderConfiguration` ：

```java
@Configuration
public class BartenderConfiguration {
    
    @Bean
    public Bartender zhangxiaosan() {
        return new Bartender("张小三");
    }
    
    @Bean
    public Bartender zhangdasan() {
        return new Bartender("张大三");
    }
    
}
```

注意哦，如果小伙伴用 **IDEA** 开发的话，此时这个类会报黄，提示这个配置类还没有被用到过，事实上也确实是这样，咱在驱动 IOC 容器初始化时，用的是只传入一个配置类的方式，所以它肯定不会用到。那想让它起作用，只需要在 `@EnableTavern` 的 `@Import` 中把这个配置类加上即可：

```java
@Import({Boss.class, BartenderConfiguration.class})
public @interface EnableTavern {
    
}
```

> 注意这里有一个小细节，有小伙伴在学习的时候，启动类里或者配置类上用了**包扫描**，恰好把这个类扫描到了，导致即使没有 `@Import` 这个 `BartenderConfiguration` ，`Bartender` 调酒师也被注册进 IOC 容器了。这里一定要细心哈，包扫描本身就会扫描配置类，并且让其生效的。如果既想用包扫描，又不想扫到这个类，很简单，把这些配置类拿到别的包里，让包扫描找不到它就好啦。

##### 2.5.2.3 测试运行

修改启动类，使用 `ApplicationContext` 的 `getBeansOfType` 方法可以一次性取出 IOC 容器指定类型的所有 Bean ：

```java
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(TavernConfiguration.class);
        Stream.of(ctx.getBeanDefinitionNames()).forEach(System.out::println);
        System.out.println("--------------------------");
        Map<String, Bartender> bartenders = ctx.getBeansOfType(Bartender.class);
        bartenders.forEach((name, bartender) -> System.out.println(bartender));
    }
```

运行 `main` 方法，可以发现控制台有打印出两个调酒师：

```
org.springframework.context.annotation.internalConfigurationAnnotationProcessor
org.springframework.context.annotation.internalAutowiredAnnotationProcessor
org.springframework.context.annotation.internalCommonAnnotationProcessor
org.springframework.context.event.internalEventListenerProcessor
org.springframework.context.event.internalEventListenerFactory
tavernConfiguration
com.linkedbear.spring.configuration.a_module.component.Boss
com.linkedbear.spring.configuration.a_module.config.BartenderConfiguration
zhangxiaosan
zhangdasan
--------------------------
com.linkedbear.spring.configuration.a_module.component.Bartender@23bb8443
com.linkedbear.spring.configuration.a_module.component.Bartender@1176dcec
```

注意里面一个小细节，`BartenderConfiguration` 配置类也被注册到 IOC 容器成为一个 Bean 了。

#### 2.5.3 导入ImportSelector

借助 IDE 打开 `ImportSelector` ，会发现它是一个**接口**，它的功能可以从文档注释中读到一些信息：

> Interface to be implemented by types that determine which @Configuration class(es) should be imported based on a given selection criteria, usually one or more annotation attributes.
>
> 它是一个接口，它的实现类可以根据指定的筛选标准（通常是一个或者多个注解）来决定导入哪些配置类。

文档注释中想表达的是可以导入配置类，但其实 `ImportSelector` 也可以导入普通类。下面咱先演示如何使用。

##### 2.5.3.1 声明吧台类

吧台的模型类咱就不搞花里胡哨了，最简单的类模型即可：

```java
public class Bar {
    
}
```

##### 2.5.3.2 声明注册吧台的配置类

咱为了说明 `ImportSelector` 不止可以导入配置类，也可以导入普通类，所以这里咱也造一个配置类，来演示两种类型皆可的效果。

```java
@Configuration
public class BarConfiguration {
    
    @Bean
    public Bar bbbar() {
        return new Bar();
    }
}
```

##### 2.5.3.3 编写ImportSelector的实现类

咱编写一个 `BarImportSelector` ，来实现 `ImportSelector` 接口，实现 `selectImports` 方法：

```java
public class BarImportSelector implements ImportSelector {
    
    @Override
    public String[] selectImports(AnnotationMetadata importingClassMetadata) {
        return new String[0];
    }
}
```

注意，`selectImports` 方法的返回值是一个 String 类型的数组，它这样设计的目的是什么呢？咱来看看 selectImports 方法的文档注释：

> Select and return the names of which class(es) should be imported based on the AnnotationMetadata of the importing @Configuration class.
>
> 根据导入的 `@Configuration` 类的 `AnnotationMetadata` 选择并返回要导入的类的类名。

哦，合着它要的是一组类名呀，自然肯定是**全限定类名**咯（没有全限定类名没办法定位具体的类）。那既然这样，咱就在这里面把上面的 `Bar` 和 `BarConfiguration` 的类名写进去：

```java
    public String[] selectImports(AnnotationMetadata importingClassMetadata) {
        return new String[] {Bar.class.getName(), BarConfiguration.class.getName()};
    }
```

最后，把 `@EnableTavern` 的 `@Import` 中把这个 `BarImportSelector` 导入进去即可。

```java
@Import({Boss.class, BartenderConfiguration.class, BarImportSelector.class})
public @interface EnableTavern {
    
}
```

##### 2.5.3.4 测试运行

修改启动类的 `main` 方法，这次只打印 IOC 容器中所有 bean 的 name 吧（主要是 bean 真的越来越多了）。运行 `main` 方法，控制台会打印出两个 `Bar` （倒数第 1 行和第 3 行），说明 `ImportSelector` 可以导入普通类和配置类：

```
org.springframework.context.annotation.internalConfigurationAnnotationProcessor
org.springframework.context.annotation.internalAutowiredAnnotationProcessor
org.springframework.context.annotation.internalCommonAnnotationProcessor
org.springframework.context.event.internalEventListenerProcessor
org.springframework.context.event.internalEventListenerFactory
tavernConfiguration
com.linkedbear.spring.configuration.a_module.component.Boss
com.linkedbear.spring.configuration.a_module.config.BartenderConfiguration
zhangxiaosan
zhangdasan
com.linkedbear.spring.configuration.a_module.component.Bar
com.linkedbear.spring.configuration.a_module.config.BarConfiguration
bbbar
```

另外注意一点，`BarImportSelector` 本身没有注册到 IOC 容器哦。

#### 2.5.4 导入ImportBeanDefinitionRegistrar

如果说 `ImportSelector` 更像声明式导入的话，那 `ImportBeanDefinitionRegistrar` 就可以解释为编程式向 IOC 容器中导入 Bean 。不过由于它导入的实际是 `BeanDefinition` （ Bean 的定义信息），这部分咱还没有接触到，就先不展开大篇幅解释了（如果要解释，那可真的是大篇幅的）。咱先对 `ImportBeanDefinitionRegistrar` 有一个快速的使用入门即可，后面在讲到 IOC 高级和原理部分，会回过头来详细解析 `ImportBeanDefinitionRegistrar` 的使用和原理。

##### 2.5.4.1 声明服务员类

离最后的酒馆只剩服务员了：

```java
public class Waiter {
    
}
```

> 这里就先不把服务员的模型类搞得很复杂了，咱的目的是学会模块装配，而不是搞 `BeanDefinition` 的复杂操作。

##### 2.5.4.2 编写ImportBeanDefinitionRegistrar的实现类

咱编写一个 `WaiterRegistrar` ，实现 `ImportBeanDefinitionRegistrar` 接口：

```java
public class WaiterRegistrar implements ImportBeanDefinitionRegistrar {
    
    @Override
    public void registerBeanDefinitions(AnnotationMetadata metadata, BeanDefinitionRegistry registry) {
        registry.registerBeanDefinition("waiter", new RootBeanDefinition(Waiter.class));
    }
}
```

这里面的写法小伙伴们先不要过度纠结，跟着写就完事了。简单解释下，这个 `registerBeanDefinition` 方法传入的两个参数，第一个参数是 Bean 的名称（id），第二个参数中传入的 `RootBeanDefinition` 要指定 Bean 的字节码（ **`.class`** ）。

最后，把 `WaiterRegistrar` 标注在 `@EnableTavern` 的 `@Import` 中：

```java
@Import({Boss.class, BartenderConfiguration.class, BarImportSelector.class, WaiterRegistrar.class})
public @interface EnableTavern {
    
}
```

##### 2.5.4.3 测试运行

直接重新运行 `main` 方法，控制台可以打印出服务员（最后一行）：

```
org.springframework.context.annotation.internalConfigurationAnnotationProcessor
org.springframework.context.annotation.internalAutowiredAnnotationProcessor
org.springframework.context.annotation.internalCommonAnnotationProcessor
org.springframework.context.event.internalEventListenerProcessor
org.springframework.context.event.internalEventListenerFactory
tavernConfiguration
com.linkedbear.spring.configuration.a_module.component.Boss
com.linkedbear.spring.configuration.a_module.config.BartenderConfiguration
zhangxiaosan
zhangdasan
com.linkedbear.spring.configuration.a_module.component.Bar
com.linkedbear.spring.configuration.a_module.config.BarConfiguration
bbbar
waiter
```

注意这里 `WaiterRegistrar` 也没有注册到 IOC 容器中。

到这里，`@Import` 的四种导入的方式也就全部过了一遍，**模块装配**说白了**就是这四种方式的综合使用**。

> 学完这几种方式后，可能小伙伴对模块装配的概念和重要性不是很能感知到，没有关系，后面咱学到 AOP 、事务等章节时，会以这些模块的激活，了解一下模块装配在 SpringFramework 内部的体现。

## 小结与练习

1. 什么是模块装配？模块装配的核心是什么？
2. 模块装配的方式有哪几种？
3. 构造一个场景：超市中有店长、服务员、收银员、货架，使用模块装配实现这个场景。

【模块装配学完之后，下一章咱学习条件装配】

# 18. IOC进阶-条件装配

上一章咱完整的学习了模块装配的核心使用方法，通过模块装配，咱可以通过一个注解，一次性导入指定场景中需要的组件和配置。那么只靠模块装配的内容，就可以把这些装配都考虑到位吗？

## 1. 模块装配考虑不到的地方

还是拿上一章的酒馆为例。如果这套代码模拟的环境放到**一片荒野**，那这个时候可能吧台还在，老板还在，但是**调酒师**肯定就**不干活了**（荒郊野外哪来那些闲情雅致的人去喝酒呢），所以这个时候调酒师就不应该注册到 IOC 容器了。这种情况下，如果只是模块装配，那就没办法搞定了：只要配置类中声明了 `@Bean` 注解的方法，那这个方法的返回值就一定会被注册到 IOC 容器成为一个 Bean 。

所以，有没有办法解决这个问题呢？当然是有（不然咱这一章讲个啥呢），先来学习第一种方式：**Profile** 。

## 2. Profile【掌握】

SpringFramework 3.1 中就已经引入 Profile 的概念了，可它是什么意思呢？咱先了解一下。

### 2.1 什么是Profile【理解】

从字面上理解，并不能 get 到它真正的含义（外形？简介？概述？），实际上如果小伙伴借助词典查看网络翻译，profile 有“配置文件”的意思，倒不是说一个 profile 是一个配置文件，它更像是一个标识。最具权威的描述，自然还是去找官方文档和 javadoc 吧。

SpringFramework 的官方文档中并没有对 Profile 进行过多的描述，而是借助了一篇官网的博客来详细介绍 Profile 的使用：[spring.io/blog/2011/0…](https://spring.io/blog/2011/02/14/spring-3-1-m1-introducing-profile/) ，咱这里的讲解也会参考这篇博客的内容。另外的，javadoc 中有对 `@Profile` 注解的介绍，这个介绍可以说是把 Profile 的设计思想介绍的很到位了：

> Indicates that a component is eligible for registration when one or more specified profiles are active. A profile is a named logical grouping that may be activated programmatically via ConfigurableEnvironment.setActiveProfiles or declaratively by setting the spring.profiles.active property as a JVM system property, as an environment variable, or as a Servlet context parameter in web.xml for web applications. Profiles may also be activated declaratively in integration tests via the @ActiveProfiles annotation.
>
> `@Profile` 注解可以标注一些组件，当应用上下文的一个或多个指定配置文件处于活动状态时，这些组件允许被注册。
>
> 配置文件是一个命名的逻辑组，可以通过 `ConfigurableEnvironment.setActiveProfiles` 以编程方式激活，也可以通过将 `spring.profiles.active` 属性设置为 JVM 系统属性，环境变量或 `web.xml` 中用于 Web 应用的 `ServletContext` 参数来声明性地激活，还可以通过 `@ActiveProfiles` 注解在集成测试中声明性地激活配置文件。

简单理解下这段文档注释的意思：`@Profile` 注解可以标注在组件上，当一个配置属性（并不是文件）激活时，它才会起作用，而激活这个属性的方式有很多种（启动参数、环境变量、`web.xml` 配置等）。

如果小伙伴看完这段话开始有点感觉了，那说明你可能已经知道它的作用了。说白了，profile 提供了一种可以理解成“**基于环境的配置**”：**根据当前项目的运行时环境不同，可以动态的注册当前运行环境匹配的组件**。

下面咱就上一章的场景，为酒馆添加外置的环境因素。

### 2.2 @Profile的使用【掌握】

> 本小节源码位置：`com.linkedbear.spring.configuration.b_profile`

咱把上一章的代码原样复制一份，粘贴到上面所述的包中：

![img](《从0开始深入学习Spring》/5c6a1f3fb0594205829b7b4b9efeaaea~tplv-k3u1fbpfcp-zoom-1.image)

下面咱开始改造。

#### 2.2.1 Bartender添加@Profile

刚在上面说了，荒郊野外下，调酒师率先不干了，跑路了，此时调酒师就不会在荒郊野外的环境下存在，只会在城市存在。用代码来表达，就是在注册调酒师的配置类上标注 `@Profile` ：

```java
@Configuration
@Profile("city")
public class BartenderConfiguration {
    @Bean
    public Bartender zhangxiaosan() {
        return new Bartender("张小三");
    }
    
    @Bean
    public Bartender zhangdasan() {
        return new Bartender("张大三");
    }
}
```

#### 2.2.2 编程式设置运行时环境

如果现在直接运行 `TavernProfileApplication` 的 `main` 方法，控制台中不会打印 `zhangxiaosan` 和 `zhangdasan` ：（已省略一些内部的组件打印）

```
tavernConfiguration
com.linkedbear.spring.configuration.b_profile.component.Boss
com.linkedbear.spring.configuration.b_profile.component.Bar
com.linkedbear.spring.configuration.b_profile.config.BarConfiguration
bbbar
waiter
```

默认情况下，`ApplicationContext` 中的 profile 为 **“default”**，那上面 `@Profile("city")` 不匹配，`BartenderConfiguration` 不会生效，那这两个调酒师也不会被注册到 IOC 容器中。要想让调酒师注册进 IOC 容器，就需要给 `ApplicationContext` 中设置一下：

```java
public static void main(String[] args) throws Exception {
    AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(TavernConfiguration.class);
    // 给ApplicationContext的环境设置正在激活的profile
    ctx.getEnvironment().setActiveProfiles("city");
    Stream.of(ctx.getBeanDefinitionNames()).forEach(System.out::println);
}
```

重新运行 `main` 方法，发现控制台还是只打印上面那些，两个调酒师还是没有被注册到 IOC 容器中。

这个时候可能有小伙伴要一脸问号了：我去你这不是逗我玩吗？你告诉我用 `setActiveProfiles` 激活，我好不容易写上，结果不好使？？？你在骗我吗？

不要着急嘛，这都是节目效果而已（狗头保命）。在生气之余，我希望小伙伴们能停下来思考一下：既然这样写不好使，但我又告诉你这么写，那是不是哪里出了问题呢？结合前面 15 章，咱对 `ApplicationContext` 的认识，是不是突然意识到了点什么？如果你还记得有个 **`refresh`** 方法的话，那这个地方就可以大胆猜测了：**是不是在 `new AnnotationConfigApplicationContext` 的时候，如果传入了配置类，它内部就自动初始化完成了，那些 Bean 也就都创建好了？**如果小伙伴能意识到这一点，说明对前面 `ApplicationContext` 的学习足够的认真了！（不记得的小伙伴可以回头看 15 章的 2.2.3 章节）

那应该怎么写才行呢？既然在构造方法中传入配置类就自动初始化完成了，那我不传呢？

```java
    AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext();
```

诶？这也不报错啊！那我先这样 new 一个空的呗？然后再设置 profile 是不是就好使了呢？赶紧来试试：

```java
public static void main(String[] args) throws Exception {
    AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext();
    ctx.getEnvironment().setActiveProfiles("city");
    ctx.register(TavernConfiguration.class);
    ctx.refresh();
    Stream.of(ctx.getBeanDefinitionNames()).forEach(System.out::println);
}
```

这样子一写，再重新运行 `main` 方法，果然控制台就打印 zhangxiaosan 和 zhangdasan 了！

```
tavernConfiguration
com.linkedbear.spring.configuration.b_profile.component.Boss
com.linkedbear.spring.configuration.b_profile.config.BartenderConfiguration
zhangxiaosan
zhangdasan
com.linkedbear.spring.configuration.b_profile.component.Bar
com.linkedbear.spring.configuration.b_profile.config.BarConfiguration
bbbar
waiter
```

> 通过这个小小的曲折，作者在这里想表达的是，小伙伴在跟小册学习时最好跟着作者的思路来，这样小伙伴在学习时学到的可能就不仅仅是这个技术怎么用，而是带入自己的思考进去，能有更多的收获。(≖ᴗ≖)✧

#### 2.2.3 声明式设置运行时环境

上面编程式配置虽然可以用了，但仔细思考一下，这种方式似乎不实用吧！我都把 profile 硬编码在 .java 里了，那要是切换环境，我还得重新编译来，那图个啥呢？所以肯定还有更好的办法。上面的文档注释中也说了，它可以使用的方法很多，下面咱来演示最容易演示的一种：命令行参数配置。

测试命令行参数的环境变量，需要在 IDEA 中配置启动选项：

![img](《从0开始深入学习Spring》/f672ef3d2526466fa74cb94d4cc682d0~tplv-k3u1fbpfcp-zoom-1.image)

这样配置好之后，在 `main` 方法中改回原来的构造方法传入配置类的形式，运行，控制台仍然会打印 zhangxiaosan 和 zhangdasan 。

修改传入的 jvm 参数，将 city 改成 **wilderness** ，重新运行 `main` 方法，发现控制台不再打印 zhangxiaosan 和 zhangdasan ，说明使用 jvm 命令行参数也可以控制 profile 。

除了 jvm 命令行参数，通过 web.xml 的方式也可以设置，不过咱还没有学习到集成 web 开发环境，所以这部分先放一放，后续讲 SpringWebMvc 时会提到它的。

### 2.3 @Profile在实际开发的用途【熟悉】

以数据源为例，在开发环境、测试环境、生产环境中，项目连接的数据库都是不一样的。如果每切换一个环境都要重新改一遍配置文件，那真的是太麻烦了，所以咱就可以采用 @Profile 的方式来解决。下面咱来模拟演示这种配置。

声明一个 `DataSourceConfiguration` 类，并一次性声明 3 个 `DataSource` ：（实际创建数据源的部分咱就不写了，还没学到 jdbc 部分不好剧透）

```java
@Configuration
public class DataSourceConfiguration {

    @Bean
    @Profile("dev")
    public DataSource devDataSource() {
        return null;
    }

    @Bean
    @Profile("test")
    public DataSource testDataSource() {
        return null;
    }

    @Bean
    @Profile("prod")
    public DataSource prodDataSource() {
        return null;
    }
}
```

这样写完之后，通过 `@PropertySource` 注解 + 外部配置文件，就可以做到**只切换 profile 即可切换不同的数据源**。

### 2.4 profile控制不到的地方

profile 强大吗？当然很强大，但它还有一些无法控制的地方。下面咱把场景进一步复杂化：

**吧台应该是由老板安置好的，如果酒馆中连老板都没有，那吧台也不应该存在。**

这种情况下，用 profile 就不好使了：因为 **profile 控制的是**整个项目的运行**环境**，无法根据单个 Bean 的因素决定是否装配。也是因为这个问题，出现了第二种条件装配的方式：**`@Conditional` 注解**。

## 3. Conditional【掌握】

看这个注解的名，condition ，很明显就是条件的意思啊，这也太直白明了了。按照惯例，咱先对 Conditional 有个清楚的认识。

### 3.1 什么是Conditional【理解】

`@Conditional` 是在 SpringFramework 4.0 版本正式推出的，它可以让 Bean 的装载基于一些指定的条件，换句话说，被标注 `@Conditional` 注解的 Bean 要注册到 IOC 容器时，必须全部满足 `@Conditional` 上指定的所有条件才可以。

在 SpringFramework 的官方文档中，并没有花什么篇幅介绍 `@Conditional` ，而是让咱们直接去看 javadoc ，不过有一说一，javadoc 里基本上把 `@Conditional` 的作用都描述明白了：

> Indicates that a component is only eligible for registration when all specified conditions match.
>
> A condition is any state that can be determined programmatically before the bean definition is due to be registered (see Condition for details).
>
> The @Conditional annotation may be used in any of the following ways:
>
> - as a type-level annotation on any class directly or indirectly annotated with @Component, including @Configuration classes
> - as a meta-annotation, for the purpose of composing custom stereotype annotations
> - as a method-level annotation on any @Bean method
>
> If a @Configuration class is marked with @Conditional, all of the @Bean methods, @Import annotations, and @ComponentScan annotations associated with that class will be subject to the conditions.
>
> 被 `@Conditional` 注解标注的组件，只有所有指定条件都匹配时，才有资格注册。条件是可以在要注册 `BeanDefinition` 之前以编程式确定的任何状态。
>
> `@Conditional` 注解可以通过以下任何一种方式使用：
>
> - 作为任何直接或间接用 `@Component` 注解的类的类型级别注解，包括 `@Configuration` 类
> - 作为元注解，目的是组成自定义注解
> - 作为任何 `@Bean` 方法上的方法级注解
>
> 如果 `@Configuration` 配置类被 `@Conditional` 标记，则与该类关联的所有 `@Bean` 的工厂方法，`@Import` 注解和 `@ComponentScan` 注解也将受条件限制。

简单理解下这段文档注释：`@Conditional` 注解可以指定匹配条件，而被 `@Conditional` 注解标注的 组件类 / 配置类 / 组件工厂方法 必须满足 `@Conditional` 中指定的所有条件，才会被创建 / 解析。

下面咱改造上面提到的场景，来体会 `@Conditional` 条件装配的实际使用。

### 3.2 @Conditional的使用【掌握】

> 本小节源码位置：`com.linkedbear.spring.configuration.c_conditional`

继续复制上面 `b_profile` 包下的所有代码，粘贴到上面所述的包中：

![img](《从0开始深入学习Spring》/46ddda8da0274259a2ab6c52e3a12375~tplv-k3u1fbpfcp-zoom-1.image)

下面开始改造。

#### 3.2.1 Bar的创建要基于Boss

在 `BarConfiguration` 的 Bar 注册中，要指定 Bar 的创建需要 Boss 的存在，反映到代码上就是在 bbbar 方法上标注 `@Conditional` ：

```java
    @Bean
    @Conditional(???)
    public Bar bbbar() {
        return new Bar();
    }
```

发现 `@Conditional` 注解中需要传入一个 `Condition` 接口的实现类数组，说明咱还需要编写条件匹配类做匹配依据。那咱就先写一个匹配条件：

#### 3.2.2 条件匹配规则类的编写

声明一个 `ExistBossCondition` 类，表示它用来判断 IOC 容器中是否存在 `Boss` 的对象：

```java
public class ExistBossCondition implements Condition {

    @Override
    public boolean matches(ConditionContext context, AnnotatedTypeMetadata metadata) {
        return context.getBeanFactory().containsBeanDefinition(Boss.class.getName());
    }
}
```

注意这个地方用 **`BeanDefinition`** 做判断而不是 **Bean** ，考虑的是当条件匹配时，可能 `Boss` 还没被创建，导致条件匹配出现偏差。

然后，把这个 `ExistBossCondition` 规则类放入 `@Conditional` 注解中。

#### 3.2.3 测试运行

运行启动类的 `main` 方法，发现吧台被成功创建：

```
tavernConfiguration
com.linkedbear.spring.configuration.c_conditional.component.Boss
com.linkedbear.spring.configuration.c_conditional.component.Bar
com.linkedbear.spring.configuration.c_conditional.config.BarConfiguration
bbbar
waiter
```

所以上面的 `@Conditional` 到底真的起作用了吗？咱把 `@EnableTavern` 中导入的 `Boss` 类去掉：

```java
@Import({BartenderConfiguration.class, BarImportSelector.class, WaiterRegistrar.class})
public @interface EnableTavern {
    
}
```

重新运行 `main` 方法，发现 `Boss` 和 `bbbar` 都没了，说明 `@Conditional` 真的起作用了。

```
tavernConfiguration
com.linkedbear.spring.configuration.c_conditional.component.Bar
com.linkedbear.spring.configuration.c_conditional.config.BarConfiguration
waiter
```

### 3.3 通用抽取【熟悉】

思考一个问题：如果一个项目中，有比较多的组件需要依赖另一些不同的组件，如果每个组件都写一个 `Condition` 条件，那工程量真的太大了。这个时候咱就要想想了：如果能把这个匹配的规则抽取为通用的方式，那岂不是让条件装配变得容易得多？抱着这个想法，咱来试着修改一下现有的代码。

#### 3.3.1 抽取传入的beanName

由于上面咱在文档注释中看到了 `@Conditional` 可以派生，那就来写一个新的注解吧：`@ConditionalOnBean` ，意为**“存在指定的 Bean 时匹配”**：

```java
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target({ElementType.TYPE, ElementType.METHOD})
@Conditional(OnBeanCondition.class)
public @interface ConditionalOnBean {

    String[] beanNames() default {};
}
```

传入的 `Condition` 类型为自己声明的 `OnBeanCondition` ：

```java
public class OnBeanCondition implements Condition {

    @Override
    public boolean matches(ConditionContext context, AnnotatedTypeMetadata metadata) {
        // 先获取目标自定义注解ConditionalOnBean上的beanNames属性
        String[] beanNames = (String[]) metadata.getAnnotationAttributes(ConditionalOnBean.class.getName()).get("beanNames");
        // 逐个校验IOC容器中是否包含传入的bean名称
        for (String beanName : beanNames) {
            if (!context.getBeanFactory().containsBeanDefinition(beanName)) {
                return false;
            }
        }
        return true;
    }
}
```

#### 3.3.2 替换上面的原生@Conditional注解

在 `BarConfiguration` 中，将 `bbbar` 方法上的 `@Conditional(ExistBossCondition.class)` 去掉，换用 `@ConditionalOnBean` 注解：

```java
@Bean
@ConditionalOnBean(beanNames = "com.linkedbear.spring.configuration.c_conditional.component.Boss")
public Bar bbbar() {
    return new Bar();
}
```

重新运行 `main` 方法，发现 `bbbar` 依然没有创建（此时 `@EnableTavern` 中已经没有导入 Boss 类了），证明自定义注解已经生效。

#### 3.3.3 加入类型匹配

上面只能是抽取 `beanName` ，传整个类的全限定名真的很费劲。如果当前类路径下本来就有这个类，那直接写进去就好呀。我们希望代码最终改造成这个样子：

```java
@Bean
@ConditionalOnBean(Boss.class)
public Bar bbbar() {
    return new Bar();
}
```

这样子多简洁啊，因为我已经有 `Boss` 类了，所以直接写进去就好嘛。那下面咱来改造这个效果。

给 `@ConditionalOnBean` 注解上添加默认的 `value` 属性，类型为 `Class[]` ，这样就可以传入类型了：

```java
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target({ElementType.TYPE, ElementType.METHOD})
@Conditional(OnBeanCondition.class)
public @interface ConditionalOnBean {
    
    Class<?>[] value() default {};

    String[] beanNames() default {};
}
```

之后，在 `OnBeanCondition` 中添加 `value` 的属性解析：

```java
public class OnBeanCondition implements Condition {

    @Override
    public boolean matches(ConditionContext context, AnnotatedTypeMetadata metadata) {
        Map<String, Object> attributes = metadata.getAnnotationAttributes(ConditionalOnBean.class.getName());
        // 匹配类型
        Class<?>[] classes = (Class<?>[]) attributes.get("value");
        for (Class<?> clazz : classes) {
            if (!context.getBeanFactory().containsBeanDefinition(clazz.getName())) {
                return false;
            }
        }
        // 匹配beanName
        String[] beanNames = (String[]) attributes.get("beanNames");
        for (String beanName : beanNames) {
            if (!context.getBeanFactory().containsBeanDefinition(beanName)) {
                return false;
            }
        }
        return true;
    }
}
```

这样，就可以匹配 bean 的名称为默认的全限定名的情况了。

> 最后多说一句，小伙伴们在自己动手练习这部分内容时不要过于纠结这里面的内容，其实咱写的这个 `@ConditionalOnBean` 是参考 SpringBoot 中的 `@ConditionalOnBean` 注解，人家 SpringBoot 官方实现的功能更严密完善，后续你在项目中用到了 SpringBoot ，那这些 `@Conditional` 派生的注解尽情用就好。

## 小结与练习

1. 为什么需要条件装配？
2. 条件装配都有哪些方式？它们分别基于什么？
3. 动手实现一个动物园的场景，利用上 profile 和 conditional 的条件装配。

【装配的部分讲完啦，接下来咱还会介绍更多 IOC 部分的特性哦 ~ 】

# 19. IOC进阶-组件扫描高级

前面在第 7 章中，咱介绍了最基础的注解驱动 IOC ，以及组件扫描的最基本使用方式。然而，组件扫描本身可是大有文章的，深入了解组件扫描中的各个细节，对了解这部分内容很有帮助。本章咱就来学习组件扫描中的一些高级使用和底层实现原理。

## 1. 包扫描的路径【掌握】

第 7 章中咱有讲过，`@ComponentScan` 注解可以指定包扫描的路径（而且还可以声明不止一个），它的写法是使用 `@ComponentScan` 的 `value` / `basePackages` 属性：

```java
@Configuration
@ComponentScan("com.linkedbear.spring.annotation.e_basepackageclass.bean")
public class BasePackageClassConfiguration {
    
}
```

这种方式是最常用的，也是最推荐使用的。除此之外，还有一种声明方式，它使用的是类的 Class 字节码：

```java
@Repeatable(ComponentScans.class)
public @interface ComponentScan {
	@AliasFor("basePackages")
	String[] value() default {};

	@AliasFor("value")
	String[] basePackages() default {};

    // 注意这个
	Class<?>[] basePackageClasses() default {};
```

它的这个 `basePackageClasses` 属性，可以传入一组 Class 进去，它代表的意思，是扫描**传入的这些 Class 所在包及子包下的所有组件**。

下面用一个简单的例子演示一下效果。

> 本小节源码位置：`com.linkedbear.spring.annotation.e_basepackageclass`

### 1.1 声明几个组件类+配置类

继续沿用之前注解驱动 IOC 的包吧，咱这里创建一个 `e_basepackageclass` 包，声明几个组件和配置类：

![img](《从0开始深入学习Spring》/74ac99edff2a4c1c81bc781e8d5dc65d~tplv-k3u1fbpfcp-zoom-1.image)

### 1.2 标注配置类的包扫描规则

配置类中，声明包扫描配置，咱先拿 `DemoService` 传进去：

```java
@Configuration
@ComponentScan(basePackageClasses = DemoService.class)
public class BasePackageClassConfiguration {
    
}
```

### 1.3 测试运行

编写启动类，驱动 IOC 容器，并打印容器中所有的 Bean 的名称：

```java
public class BasePackageClassApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(BasePackageClassConfiguration.class);
        String[] beanDefinitionNames = ctx.getBeanDefinitionNames();
        Stream.of(beanDefinitionNames).forEach(System.out::println);
    }
}
```

运行 `main` 方法，发现控制台中只打印了 `DemoService` 与 `DemoDao` ：

```
org.springframework.context.annotation.internalConfigurationAnnotationProcessor
org.springframework.context.annotation.internalAutowiredAnnotationProcessor
org.springframework.context.annotation.internalCommonAnnotationProcessor
org.springframework.context.event.internalEventListenerProcessor
org.springframework.context.event.internalEventListenerFactory
basePackageClassConfiguration
demoDao
demoService
```

说明它确实以 `DemoService` 所在的包为基准扫描了，不过没有扫描到 `DemoComponent` 。

### 1.4 加入DemoComponent

在 `@ComponentScan` 中，再加入 `DemoComponent` 的字节码：

```java
@Configuration
@ComponentScan(basePackageClasses = {DemoService.class, DemoComponent.class})
public class BasePackageClassConfiguration {
    
}
```

重新运行 `main` 方法，控制台中多了 `DemoComponent` 与 `InnerComponent` 的打印，由此体现出 `basePackageClasses` 的作用。

## 2. 包扫描的过滤【掌握】

在实际开发的场景中，我们用包扫描拿到的组件不一定全部都需要，也或者只有一部分需要，这个时候就需要用到包扫描的过滤了。

> 如果小伙伴之前有用 SpringWebMvc 的 xml 配置开发 Web 应用的话，应该印象蛮深刻吧！`spring-mvc.xml` 中配置只能扫描 `@Controller` 注解，`applicationContext.xml` 中又要设置不扫描 `@Controller` 注解，这就是扫描过滤的规则设置。

> 本小节源码位置：`com.linkedbear.spring.annotation.f_typefilter`

下面咱先来创建一些组件类。

### 2.1 声明好多组件类+配置类

这次声明的更多了，可想而知接下来得有多少种过滤的规则哦（滑稽）

![img](《从0开始深入学习Spring》/b1e87da9645449ecb66111006edf9a00~tplv-k3u1fbpfcp-zoom-1.image)

简单说一下这些组件的编写。

- ```
  @Animal
  ```

   

  是一个普通的注解，它可以标注在类上

  - `Cat` 、`Dog` 、`Pikachu` 是三个最简单的类，其中 `Cat` 和 `Dog` 上除了标注 `@Component` 注解外，还标注 `@Animal`

- color 包下的

   

  ```
  Color
  ```

   

  是一个父类

  - 下面的红黄绿三个类均标注 `@Component` ，不过只有 `Red` 和 `Yellow` 继承 `Color`

- bean 包的 `DemoService` 与 `DemoDao` 均是普通的类，且都没有标注任何注解

下面咱开始介绍过滤的几种方式。

### 2.2 按注解过滤包含

在 `TypeFilterConfiguration` 中，声明 `@ComponentScan` 注解，扫描整个 `f_typefilter` 包，之后在 `@ComponentScan` 注解中声明 `includeFilters` 属性，让它把含有 `@Animal` 注解的类带进来：

```java
@Configuration
@ComponentScan(basePackages = "com.linkedbear.spring.annotation.f_typefilter",
               includeFilters = @ComponentScan.Filter(type = FilterType.ANNOTATION, value = Animal.class))
public class TypeFilterConfiguration {
    
}
```

注意这里面的 `@Filter` 是 `@ComponentScan` 注解的内部类哦。

编写启动类，驱动 IOC 容器，并打印容器中所有 Bean 的名称，发现所有标注了模式注解的类全加载进来了：

```
typeFilterConfiguration
cat
dog
pikachu
green
red
yellow
```

这跟咱的预想似乎不是很一致：我想只让你把 `@Animal` 注解过的类带进来，你咋把这么一大堆都给我注册了呢？那是因为，`@ComponentScan` 注解中还有一个属性：`useDefaultFilters` ，它代表的是“是否启用默认的过滤规则”。咱之前也讲过了，默认规则就是扫那些以 `@Component` 注解为基准的模式注解。其实这个属性的文档注释也写的很明白了：

> Indicates whether automatic detection of classes annotated with @Component @Repository, @Service, or @Controller should be enabled.
>
> 指示是否应启用对以 `@Component` 、`@Repository` 、`@Service` 或 `@Controller` 注解的类的自动检测。

合着人家默认就扫这几个注解的原因在这里啊，那我指定了我自己想过滤的规则你还不理呗？这是瞧谁不起啊？

莫急莫急，**你声明了自己的过滤规则，不耽误人家的呀**。换句话说，**这些 include 的过滤规则之间互相不受影响，且不会互相排除**：你包含的组件我也包含，那咱就一起加载；你不包含的我包含，那我也把它们带过来，而不是我拿过来了你又给我扔了。

也许这样理解起来更容易一些（有颜色的部分代表匹配规则）：

![img](《从0开始深入学习Spring》/4cc6502a040548d6966aa52e89d6542a~tplv-k3u1fbpfcp-zoom-1.image)

### 2.3 按注解排除

这次咱反过来，刚才不是 include 了吗？这次咱换用 **exclude** ：

```java
@Configuration
@ComponentScan(basePackages = "com.linkedbear.spring.annotation.f_typefilter",
               excludeFilters = @ComponentScan.Filter(type = FilterType.ANNOTATION, value = Animal.class))
public class TypeFilterConfiguration {
    
}
```

重新运行 `main` 方法，可以发现 `Cat` 和 `Dog` 都不见了：

```
typeFilterConfiguration
pikachu
green
red
yellow
```

由此可以得出结论：**排除型过滤器会排除掉其他过滤规则已经包含进来的 Bean** 。

跟上面对比起来，很明显这种情况下包含的组件会少一些（只要是带 `@Animal` 的都不会被匹配）：

![img](《从0开始深入学习Spring》/9b8246722a7844fe9b10793033120120~tplv-k3u1fbpfcp-zoom-1.image)

### 2.3 按类型过滤

继续在 `@ComponentScan` 注解上添加过滤规则，这次咱把所有 `Color` 类型都包含进来：

```java
@Configuration
@ComponentScan(basePackages = "com.linkedbear.spring.annotation.f_typefilter",
               includeFilters = {@ComponentScan.Filter(type = FilterType.ASSIGNABLE_TYPE, value = Color.class)},
               excludeFilters = {@ComponentScan.Filter(type = FilterType.ANNOTATION, value = Animal.class)})
public class TypeFilterConfiguration {
    
}
```

重新运行 `main` 方法，发现这次连父类 `Color` 也给带进来了：（第 5 个）

```java
typeFilterConfiguration
pikachu
color
green
red
yellow
```

如果把这个规则也挪到 **exclude** 中，则 color 、red 、yellow 都就没了：

```
typeFilterConfiguration
pikachu
green
```

### 2.4 正则表达式过滤

除了按注解过滤、按类型过滤，它内置的模式还有两种表达式的过滤规则，分别是 “切入点表达式过滤” 和 “正则表达式过滤” 。关于切入点表达式的概念咱放到 AOP 中再讲，这里先讲正则表达式的方式。

这次咱想通过正则表达式的方式，把那两个 Demo 开头的组件加载进来，正则表达式就可以这样编写：

```java
@Configuration
@ComponentScan(basePackages = "com.linkedbear.spring.annotation.f_typefilter",
               includeFilters = {
                       @ComponentScan.Filter(type = FilterType.REGEX, pattern = "com.linkedbear.spring.annotation.f_typefilter.+Demo.+")
               },
               excludeFilters = {
                       @ComponentScan.Filter(type = FilterType.ANNOTATION, value = Animal.class),
                       @ComponentScan.Filter(type = FilterType.ASSIGNABLE_TYPE, value = Color.class)
               })
public class TypeFilterConfiguration {
    
}
```

这样编写好后，重新运行 `main` 方法，`DemoService` 和 `DemoDao` 就会被注册到 IOC 容器了：

```java
typeFilterConfiguration
pikachu
demoDao
demoService
green
```

### 2.5 自定义过滤

如果预设的几种模式都不能满足要求，那就需要用编程式过滤方式了，也就是自定义过滤规则。

先定个目标吧，这次编写自定义过滤后，咱们把 green 也过滤掉。

#### 2.5.1 TypeFilter接口

编程式自定义过滤，需要编写过滤策略，实现 `TypeFilter` 接口。这个接口只有一个 `match` 方法：

```java
@FunctionalInterface
public interface TypeFilter {
	boolean match(MetadataReader metadataReader, MetadataReaderFactory metadataReaderFactory) throws IOException;
}
```

这个 `match` 方法有两个参数，咱是一个也看不懂呀！好在文档注释中有描述，咱可以来参考一下：

- metadataReader

   

  ：the metadata reader for the target class

  - 通过这个 Reader ，可以读取到正在扫描的类的信息（包括类的信息、类上标注的注解等）

- metadataReaderFactory

   

  ：a factory for obtaining metadata readers for other classes (such as superclasses and interfaces)

  - 借助这个 Factory ，可以获取到其他类的 Reader ，进而获取到那些类的信息
  - 可以这样理解：**借助 ReaderFactory 可以获取到 Reader ，借助 Reader 可以获取到指定类的信息**

现在看不懂没关系，咱把上面的需求实现出来就好了嘛。

#### 2.5.2 编写自定义过滤规则

`MetadataReader` 中有一个 `getClassMetadata` 方法，可以拿到正在扫描的类的基本信息，咱可以由此取到全限定类名，进而与咱需求中的 `Green` 类做匹配：

```java
public boolean match(MetadataReader metadataReader, MetadataReaderFactory metadataReaderFactory)
         throws IOException {
    ClassMetadata classMetadata = metadataReader.getClassMetadata();
    return classMetadata.getClassName().equals(Green.class.getName());
}
```

返回 true ，则说明已经匹配上了。

#### 2.5.3 添加过滤规则声明

`TypeFilter` 写完了，不要忘记加在 `@ComponentScan` 上：

```java
@Configuration
@ComponentScan(basePackages = "com.linkedbear.spring.annotation.f_typefilter",
               includeFilters = {
                       @ComponentScan.Filter(type = FilterType.REGEX, pattern = "com.linkedbear.spring.annotation.f_typefilter.+Demo.+")
               },
               excludeFilters = {
                       @ComponentScan.Filter(type = FilterType.ANNOTATION, value = Animal.class),
                       @ComponentScan.Filter(type = FilterType.ASSIGNABLE_TYPE, value = Color.class),
                       @ComponentScan.Filter(type = FilterType.CUSTOM, value = GreenTypeFilter.class)
               })
public class TypeFilterConfiguration {
    
}
```

重新运行启动类的 `main` 方法，可以发现 `Green` 也没了，自定义 `TypeFilter` 生效。

```
typeFilterConfiguration
pikachu
demoDao
demoService
```

更多的 `MetadataReader` 和 `MetadataReaderFactory` 的使用，小伙伴们可以自行探索，小册不过多列举。

#### 2.5.4 metadata的概念

讲到这里了，咱先不着急往下走，停一停，咱讲讲 **metadata** 的概念。

回想一下 JavaSE 的反射，它是不是可以根据咱写好的类，获取到类的全限定名、属性、方法等信息呀。好，咱现在就建立起这么一个概念：咱定义的类，它叫什么名，它有哪些属性，哪些方法，这些信息，统统叫做**元信息**，**元信息会描述它的目标的属性和特征**。

在 SpringFramework 中，元信息大量出现在框架的底层设计中，不只是 **metadata** ，前面咱屡次见到的 **definition** ，也是元信息的体现。后面到了 IOC 高级部分，咱会整体的学习 SpringFramework 中的元信息、元定义设计，以及 `BeanDefinition` 的全解析。

## 3. 包扫描的其他特性【熟悉】

两个比较重头的特性咱说完之后，还有一些小零碎，咱也盘点盘点。

### 3.1 包扫描可以组合使用

小伙伴们在写 `@ComponentScan` 注解时一定有发现还有一个 `@ComponentScans` 注解吧！不过比较靠前的版本是看不到它的，它起源自 4.3 ：

```java
// @since 4.3
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.TYPE)
@Documented
public @interface ComponentScans {
	ComponentScan[] value();
}
```

其实它就是一次性组合了一堆 `@ComponentScan` 注解而已了，没啥好说的。

### 3.2 包扫描的组件名称生成

咱在前面刚学习注解驱动时，就知道默认情况下生成的 bean 的名称是类名的首字母小写形式（ Person → person ），可是它为啥就有这个规则呢？这个问题，也可以从 `@ComponentScan` 注解中找到。

在 `@ComponentScan` 注解的属性中，有一个 `nameGenerator` ，它的默认值是 `BeanNameGenerator` 。不过这个 `BeanNameGenerator` 是一个接口，从文档注释中不难找到实现类是 `AnnotationBeanNameGenerator` 。

#### 3.2.1 BeanNameGenerator

从名称上就知道它是 Bean 的名字生成器了，它只有一个 `generateBeanName` 方法：

```java
public interface BeanNameGenerator {
	String generateBeanName(BeanDefinition definition, BeanDefinitionRegistry registry);
}
```

又出现 `BeanDefinition` 和 `BeanDefinitionRegistry` 了，可见元信息、元定义在底层真的太常见了！

不过咱先不要把精力放在这里，实现类才是重点。

#### 3.2.2 AnnotationBeanNameGenerator的实现

找到 `AnnotationBeanNameGenerator` 的实现：

```java
public String generateBeanName(BeanDefinition definition, BeanDefinitionRegistry registry) {
    // 组件的注册方式是注解扫描的
    if (definition instanceof AnnotatedBeanDefinition) {
        // 尝试从注解中获取名称
        String beanName = determineBeanNameFromAnnotation((AnnotatedBeanDefinition) definition);
        if (StringUtils.hasText(beanName)) {
            // Explicit bean name found.
            return beanName;
        }
    }
    // Fallback: generate a unique default bean name.
    // 如果没有获取到，则创建默认的名称
    return buildDefaultBeanName(definition, registry);
}
```

看这段源码的实现，整体的逻辑还是非常容易理解的：

1. 只有注解扫描注册进来的 Bean 才会被处理（ `AnnotationBeanNameGenerator` ，看类名 ￣へ￣ ）

2. 既然是注解扫描进来的，那我就要看看有木有在注解中声明好了

   > 这种声明方式就是 `@Component("person")`

3. 注解中找不到名，那好吧，我给你构造一个，不过这个名是按照我默认规则来的，你就别挑挑拣拣咯

上面从注解中获取的部分咱留到后面再看，这里咱只看 `buildDefaultBeanName` 的实现。

#### 3.2.3 buildDefaultBeanName的实现

```java
protected String buildDefaultBeanName(BeanDefinition definition, BeanDefinitionRegistry registry) {
    return buildDefaultBeanName(definition);
}

protected String buildDefaultBeanName(BeanDefinition definition) {
    String beanClassName = definition.getBeanClassName();
    Assert.state(beanClassName != null, "No bean class name set");
    String shortClassName = ClassUtils.getShortName(beanClassName);
    return Introspector.decapitalize(shortClassName);
}
```

一路走到最底下的方法中，它会根据组件类的全限定名，截取出短类名（如 `com.linkedbear.Person` → `Person` ），最后用一个叫 `Introspector` 的类，去生成 bean 的名称。那想必这个 `Introspector.decapitalize` 方法肯定就可以把类名的首字母转为小写咯，点进去发现确实如此：

```java
public static String decapitalize(String name) {
    if (name == null || name.length() == 0) {
        return name;
    }
    if (name.length() > 1 && Character.isUpperCase(name.charAt(1)) &&
        Character.isUpperCase(name.charAt(0))){
        return name;
    }
    char chars[] = name.toCharArray();
    // 第一个字母转小写
    chars[0] = Character.toLowerCase(chars[0]);
    return new String(chars);
}
```

原理实现看完了，小伙伴们肯定有一个疑惑：`Introspector` 是个什么鬼哦？？

#### 3.2.4 Java的内省机制【扩展】

说到这个**内省**，或许好多小伙伴都没听说过。其实**它是 JavaSE 中就有的，对 JavaBean 中属性的默认处理规则**。

回想一下咱写的所有模型类，包括 vo 类，是不是都是写好了属性，之后借助 IDE 生成 `getter` 和 `setter` ，或者借助 `Lombok` 的注解生成 `getter` 和 `setter` ？其实这个生成规则，就是利用了 Java 的内省机制。

**Java 的内省默认规定，所有属性的获取方法以 get 开头（ boolean 类型以 is 开头），属性的设置方法以 set 开头。**根据这个规则，才有的默认的 getter 和 setter 方法。

`Introspector` 类是 Java 内省机制中最核心的类之一，它可以进行很多默认规则的处理（包括获取类属性的 get / set 方法，添加方法描述等），当然它也可以处理这种类名转 beanName 的操作。SpringFramework 深知这个设计之妙，就直接利用过来了。

有关更多的 Java 内省机制，小伙伴们可以搜索相关资料学习，小册不多展开讲解了（这部分适当了解即可）。

## 小结与练习

1. 包扫描指定扫描路径的方式有几种？分别如何指定？
2. 包扫描如何处理过滤规则？默认有哪几种规则？
3. 自行编写几个具有不同特征的 bean ，并练习包扫描过滤的使用方法。

【组件扫描的部分差不多就这些了，是不是感觉前面学到的还是太少了呢？所以在重要的环节上咱还是会有深入讲解的。下一章咱稍微放松一下，讲一点编码成分相对少的部分：资源管理】

# 20. IOC进阶-资源管理

前面咱在学习 `ApplicationContext` 的章节中，有看到 `ClassPathXmlApplicationContext` 的直接父类 `AbstractXmlApplicationContext` 中组合了一个 `XmlBeanDefinitionReader` 组件来解析 xml 配置文件。其中，`XmlBeanDefinitionReader` 接收的 xml 配置文件是一组 **`Resource`** ：

```java
protected void loadBeanDefinitions(XmlBeanDefinitionReader reader) throws BeansException, IOException {
    Resource[] configResources = getConfigResources();
    if (configResources != null) {
        reader.loadBeanDefinitions(configResources);
    }
    // ......
}
```

这个 **`Resource`** 就是 SpringFramework 中定义的资源模型。这一章咱就来学习 SpringFramework 中的资源管理部分。

> 本章基本上没什么代码，对于实际开发中可能重要程度不是非常高，小伙伴们以了解为主即可。

## 1. SpringFramework为什么要自己造【了解】

一看到资源管理，或许会有小伙伴立马想到 `ClassLoader` 的 `getResource` 和 `getResourceAsStream` 方法，它们本身就是 jdk 内置的加载资源文件的方式。然而 SpringFramework 中并没有直接拿它的这一套，而是自己重新造了一套比原生 jdk 更强大的资源管理。既然是造了，那就肯定有原因（人家的挺好你为啥不用呢，肯定是你觉得它不好），而这个原因，咱们可以翻看 SpringFramework 的官方文档：

[docs.spring.io/spring/docs…](https://docs.spring.io/spring/docs/5.2.x/spring-framework-reference/core.html#resources-introduction)

原文咱就不在这里贴了，概述一下就是说，jdk 原生的 URL 那一套资源加载方式，对于加载 classpath 或者 `ServletContext` 中的资源来说没有标准的处理手段，而且即便是实现起来也很麻烦，倒不如我自己写一套。（大佬就是强啊）

如果对比原生 jdk 和 SpringFramework 中的资源管理，可能 SpringFramework 的资源管理真的要更强大吧，下面咱来了解下 SpringFramework 中定义的资源模型都有什么结构，分别负责哪些功能。

## 2. SpringFramework中的资源模型【了解】

先来一张图概览一下吧：

![img](《从0开始深入学习Spring》/dcf8b03d274f4de1a52bbc2c02706277~tplv-k3u1fbpfcp-zoom-1.image)

可以发现，SpringFramework 中资源模型最顶级的其实不是 `Resource` ，而是一个叫 `InputStreamSource` 的接口：

#### 2.1 InputStreamSource

```java
public interface InputStreamSource {
	InputStream getInputStream() throws IOException;
}
```

这个接口只有一个 `getInputStream` 方法，很明显它表达了一件事情：实现了 `InputStreamSource` 接口的实现类，都可以从中取到资源的输入流。

#### 2.2 Resource

然后就是 `InputStreamSource` 的子接口 `Resource` 了，它的文档注释中有写到这么一句话：

> Interface for a resource descriptor that abstracts from the actual type of underlying resource, such as a file or class path resource.
>
> 它是资源描述符的接口，它可以从基础资源的实际类型中抽象出来，例如文件或类路径资源。

这个翻译看起来很生硬，不过咱只需要关注到一个点：**文件或类路径的资源**，仅凭这一个点，咱就可以说，`Resource` 确实更适合 SpringFramework 做资源加载（配置文件通常都放到类路径下）。

#### 2.3 EncodedResource

在 `Resource` 的旁边，有一个 `EncodedResource` 直接实现了 `InputStreamSource` 接口，从类名上也能看得出来它是编码后的资源。通过源码，发现它内部组合了一个 `Resource` ，说明它本身并不是直接加载资源的。

```java
public class EncodedResource implements InputStreamSource {
	private final Resource resource;
    // ......
```

#### 2.4 WritableResource

继续往下看，自打 SpringFramework 3.1 之后，`Resource` 有了一个新的子接口：`WritableResource` ，它代表着“可写的资源”，那 `Resource` 就可以理解为“可读的资源”（有木有想起来 `BeanFactory` 与 `ConfigurableBeanFactory` ？）。

#### 2.5 ContextResource

跟 `WritableResource` 并列的还有一个 `ContextResource` ，看到类名是不是突然一阵狂喜？它肯定是跟 `ApplicationContext` 有关系吧！打开源码，看一眼文档注释：

> Extended interface for a resource that is loaded from an enclosing 'context', e.g. from a javax.servlet.ServletContext but also from plain classpath paths or relative file system paths (specified without an explicit prefix, hence applying relative to the local ResourceLoader's context).
>
> 从一个封闭的 “上下文” 中加载的资源的扩展接口，例如来自 `javax.servlet.ServletContext` ，也可以来自普通的类路径路径或相对的文件系统路径（在没有显式前缀的情况下指定，因此相对于本地 `ResourceLoader` 的上下文应用）。

emmm它是跟 `ServletContext` 有关的？那跟 `ApplicationContext` 没关系咯。。。是的，它强调的是从一个**封闭的 “上下文” 中加载**，这其实就是说像 `ServletContext` 这种域（当然文档也说了只是举个例子）。

以上就是 SpringFramework 中设计的资源模型，不过平时咱用的只有 `Resource` 接口而已。

## 3. SpringFramework中的资源模型实现【熟悉】

说完了接口，下面说说实现类。不过在说实现类之前，咱先说另外一件事，就是 Java 原生的资源加载方式。

### 3.1 Java原生资源加载方式

回想一下，Java 原生能加载到哪些地方的资源？应该大致上分 3 种吧：

- 借助 ClassLoader 加载类路径下的资源
- 借助 File 加载文件系统中的资源
- 借助 URL 和不同的协议加载本地 / 网络上的资源

这三种方式基本上就囊括了大部分的加载方式了。为什么要提它呢？那是因为，SpringFramework 中的资源模型实现，就是这三种的体现。

### 3.2 SpringFramework的实现

SpringFramework 分别对上面提到的这三种情况提供了三种不同的实现：

- ClassLoader → `ClassPathResource` [ classpath:/ ]
- File → `FileSystemResource` [ file:/ ]
- URL → `UrlResource` [ xxx:/ ]

注意每一行最后的方括号，它代表的是资源路径的前缀：如果是 **classpath** 开头的资源路径，SpringFramework 解析到后会自动去类路径下找；如果是 **file** 开头的资源路径，则会去文件系统中找；如果是 URL 支持的协议开头，则底层会使用对应的协议，去尝试获取相应的资源文件。

除了这三种实现，还有对应于 `ContextResource` 的实现：`ServletContextResource` ，它意味着资源是去 `ServletContext` 域中寻找。

## 4. SpringFramework加载资源的方式【了解】

其实关于 SpringFramework 的资源加载，在 15 章的 1.6 节就已经提到过一个 `ResourcePatternResolver` ，它的父接口 `ResourceLoader` 就是那个真正负责加载资源的角色。另外在 15 章的 2.1.4 节，咱也提过在 `AbstractApplicationContext` 中，通过类继承关系可以得知它继承了 `DefaultResourceLoader` ，也就是说，**`ApplicationContext` 具有加载资源的能力**。

下面咱简单了解一下 `DefaultResourceLoader` 是如何根据一个路径，加载到相应的资源的。

这段源码的篇幅稍微有点长，咱分开几个部分来看：

### 4.1 DefaultResourceLoader组合了一堆ProtocolResolver

```java
private final Set<ProtocolResolver> protocolResolvers = new LinkedHashSet<>(4);

public Resource getResource(String location) {
    Assert.notNull(location, "Location must not be null");

    for (ProtocolResolver protocolResolver : getProtocolResolvers()) {
        Resource resource = protocolResolver.resolve(location, this);
        if (resource != null) {
            return resource;
        }
    }
    // ......
}
```

这一段，它会先取它内部组合的几个 `ProtocolResolver` 来尝试着加载资源，而这个 `ProtocolResolver` 的设计也是跟 `ResourceLoader` 有关。

#### 4.1.1 ProtocolResolver

它的设计倒是蛮简单了：

```java
// @since 4.3
@FunctionalInterface
public interface ProtocolResolver {
	Resource resolve(String location, ResourceLoader resourceLoader);
}
```

它只有一个接口，而且是在 SpringFramework 4.3 版本才出现的（蛮年轻哦），它本身可以搭配 `ResourceLoader` ，在 `ApplicationContext` 中实现**自定义协议的资源加载**，但它还可以脱离 `ApplicationContext` ，直接跟 `ResourceLoader` 搭配即可。这个特性蛮有趣的，咱可以稍微写点代码演示一下效果。

#### 4.1.2 ProtocolResolver使用方式

在工程的 `resources` 目录下新建一个 `Dog.txt` 文件（随便放哪儿都行，只要能找得到），然后写一个 `DogProtocolResolver` ，实现 `ProtocolResolver` 接口：

```java
public class DogProtocolResolver implements ProtocolResolver {

    public static final String DOG_PATH_PREFIX = "dog:";

    @Override
    public Resource resolve(String location, ResourceLoader resourceLoader) {
        if (!location.startsWith(DOG_PATH_PREFIX)) {
            return null;
        }
        // 把自定义前缀去掉
        String realpath = location.substring(DOG_PATH_PREFIX.length());
        String classpathLocation = "classpath:resource/" + realpath;
        return resourceLoader.getResource(classpathLocation);
    }
}
```

然后，编写启动类，分别实例化 `DefaultResourceLoader` 与 `DogProtocolResolver` ，并将 `DogProtocolResolver` 加入到 `ResourceLoader` 中：

```java
public class ProtocolResolverApplication {

    public static void main(String[] args) throws Exception {
        DefaultResourceLoader resourceLoader = new DefaultResourceLoader();
        DogProtocolResolver dogProtocolResolver = new DogProtocolResolver();
        resourceLoader.addProtocolResolver(dogProtocolResolver);
    }
}
```

然后，用 `ResourceLoader` 获取刚编写好的 `Dog.txt` ，并用缓冲流读取：

```java
public static void main(String[] args) throws Exception {
    DefaultResourceLoader resourceLoader = new DefaultResourceLoader();
    DogProtocolResolver dogProtocolResolver = new DogProtocolResolver();
    resourceLoader.addProtocolResolver(dogProtocolResolver);

    Resource resource = resourceLoader.getResource("dog:Dog.txt");
    InputStream inputStream = resource.getInputStream();
    InputStreamReader reader = new InputStreamReader(inputStream, StandardCharsets.UTF_8);
    BufferedReader br = new BufferedReader(reader);
    String readLine;
    while ((readLine = br.readLine()) != null) {
        System.out.println(readLine);
    }
    br.close();
}
```

运行 `main` 方法，控制台打印出 `Dog.txt` 的内容，证明 `DogProtocolResolver` 已经起到了作用：

```
wangwangwang
```

### 4.2 DefaultResourceLoader可自行加载类路径下的资源

```java
public Resource getResource(String location) {
    // ......
    if (location.startsWith("/")) {
        return getResourceByPath(location);
    } else if (location.startsWith(CLASSPATH_URL_PREFIX)) {
        return new ClassPathResource(location.substring(CLASSPATH_URL_PREFIX.length()), getClassLoader());
    }
    // ......
}
```

这部分，且不看上面的 `startsWith` ，只看中间的 else if 部分返回的类型，就知道它能解析类路径下的资源了，而上面的 `getResourceByPath` 方法，点进去发现默认还是加载类路径下：

```java
protected Resource getResourceByPath(String path) {
    return new ClassPathContextResource(path, getClassLoader());
}
```

不过这个不是绝对的，如果小伙伴现在手头的工程还有引入 `spring-web` 模块的 pom 依赖，会发现 `DefaultResourceLoader` 的几个 Web 级子类中有重写这个方法，以 `GenericWebApplicationContext` 为例：

```java
protected Resource getResourceByPath(String path) {
    Assert.state(this.servletContext != null, "No ServletContext available");
    return new ServletContextResource(this.servletContext, path);
}
```

可以发现这里创建的不再是类路径下了，Web 环境下 SpringFramework 更倾向于从 `ServletContext` 中加载。

### 4.3 DefaultResourceLoader可支持特定协议

```java
public Resource getResource(String location) {
    // ......
    else {
        try {
            // Try to parse the location as a URL...
            URL url = new URL(location);
            return (ResourceUtils.isFileURL(url) ? new FileUrlResource(url) : new UrlResource(url));
        }
        catch (MalformedURLException ex) {
            // No URL -> resolve as resource path.
            return getResourceByPath(location);
        }
    }
}
```

如果上面它不能处理类路径的文件，就会尝试通过 URL 的方式加载，这里面包含文件系统的资源，和特殊协议的资源。这里面咱就不进一步深入了，小伙伴们了解 `DefaultResourceLoader` 能加载的资源类型和大体的流程即可。

## 小结与思考

1. SpringFramework 的资源模型是什么？都有哪几种类型？
2. SpringFramework 默认可以加载的资源都有哪些？顺序分别是什么？

【资源管理这一章相对比较短，小伙伴了解即可。下面咱顺着资源的思路，深入学习一个跟资源很相关的东西：`PropertySource` 】

# 21. IOC进阶-PropertySource的使用

承接上一章的内容，本章咱来介绍一个重要的资源加载注解：`@PropertySource` 。之前咱早在第 8 章的属性注入中就使用过这个注解，但也仅仅是最简单的使用，本章我们来深入探讨这个注解的使用。

## 1. @PropertySource引入properties文件【掌握】

常规的使用方式，当然是引入 properties 文件了，下面咱快速回顾一下这种使用方式。

> 本小节源码位置：`com.linkedbear.spring.annotation.g_propertysource`

### 1.1 声明properties文件

在 `resources` 目录下新建一个 `propertysource` 文件夹，此处存放本章声明的所有资源文件。

新建一个 `jdbc.properties` 文件，用来代表声明一个 jdbc 的连接属性（这种写法在后续的 jdbc 整合时非常常见，不过咱还没有学到跟 jdbc 打交道，所以此处只是单纯的声明下而已）：

```properties
jdbc.url=jdbc:mysql://localhost:3306/test
jdbc.driver-class-name=com.mysql.jdbc.Driver
jdbc.username=root
jdbc.password=123456
```

### 1.2 编写配置模型类

为了方便观察资源文件是否注入到了 IOC 容器，咱写一个模型类来接收这些配置项，就叫 `JdbcProperties` 吧：

```java
@Component
public class JdbcProperties {

    @Value("${jdbc.url}")
    private String url;
    
    @Value("${jdbc.driver-class-name}")
    private String driverClassName;
    
    @Value("${jdbc.username}")
    private String username;
    
    @Value("${jdbc.password}")
    private String password;
    
    // 省略getter setter toString
}
```

### 1.3 编写配置类

新建一个 `JdbcPropertiesConfiguration` ，扫描配置模型类所在的包，并声明导入上面的 `jdbc.properties` 文件：

```java
@Configuration
@ComponentScan("com.linkedbear.spring.annotation.g_propertysource.bean")
@PropertySource("classpath:propertysource/jdbc.properties")
public class JdbcPropertiesConfiguration {
    
}
```

### 1.4 测试运行

编写启动类，驱动 `JdbcPropertiesConfiguration` 配置类，并尝试打印容器中的配置模型类的属性：

```java
public class PropertySourcePropertiesApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                JdbcPropertiesConfiguration.class);
        System.out.println(ctx.getBean(JdbcProperties.class).toString());
    }
}
```

运行 `main` 方法，控制台打印了 `jdbc.properties` 中的属性，证明 properties 文件导入成功。

```
JdbcProperties{url='jdbc:mysql://localhost:3306/test', driverClassName='com.mysql.jdbc.Driver', username='root', password='123456'}
```

## 2. @PropertySource引入xml文件【了解】

意料之外吧，`@PropertySource` 还可以引入 xml 文件，其实在它的注解属性上已经有标注了：

> Indicate the resource location(s) of the properties file to be loaded. Both traditional and XML-based properties file formats are supported.
>
> 指示要加载的属性文件的资源位置。 支持原生 properties 和基于 XML 的属性文件格式。

那下面咱就来体会一下导入 xml 的方式。

> 本小节源码位置：`com.linkedbear.spring.annotation.h_propertyxml`

### 2.1 声明xml文件

新建一个 `jdbc.xml` 文件，但是这里面的写法可是有严格的格式要求的：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE properties SYSTEM "http://java.sun.com/dtd/properties.dtd">
<properties>
    <entry key="xml.jdbc.url">jdbc:mysql://localhost:3306/test</entry>
    <entry key="xml.jdbc.driver-class-name">com.mysql.jdbc.Driver</entry>
    <entry key="xml.jdbc.username">root</entry>
    <entry key="xml.jdbc.password">123456</entry>
</properties>
```

可能这个时候小伙伴们的表情已经有点 “地铁老人看手机” 的样子了。

![img](《从0开始深入学习Spring》/4185024610e04e54b06f9922e61e98eb~tplv-k3u1fbpfcp-zoom-1.image)

写个这玩意咋还这么费劲了？然而没招，这是 sun 当时给出的 Properties 格式的 xml 标准规范写法，必须按照这个格式来，才能解析为 `Properties` 。咱先这么写，稍后会解释这样写的原因。

### 2.2 编写配置模型类

仿造上面的配置模型类，搞一个基本一样的出来：（注意这里的 `@Value` 取值加了 xml 前缀）

```java
@Component
public class JdbcXmlProperty {
    
    @Value("${xml.jdbc.url}")
    private String url;
    
    @Value("${xml.jdbc.driver-class-name}")
    private String driverClassName;
    
    @Value("${xml.jdbc.username}")
    private String username;
    
    @Value("${xml.jdbc.password}")
    private String password;
    
    // 省略getter setter toString
}
```

### 2.3 编写配置类

仿造上面的配置类写法，造一个基本一样的配置类，注意扫描包的位置不要写错了：

```java
@Configuration
@ComponentScan("com.linkedbear.spring.annotation.h_propertyxml.bean")
@PropertySource("classpath:propertysource/jdbc.xml")
public class JdbcXmlConfiguration {
    
}
```

### 2.4 测试运行

编写启动类，驱动 `JdbcXmlConfiguration` ，并打印 IOC 容器中的 `JdbcXmlProperty` ：

```java
public class PropertySourceXmlApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(JdbcXmlConfiguration.class);
        System.out.println(ctx.getBean(JdbcXmlProperty.class).toString());
    }
}
```

运行 `main` 方法，控制台也可以打印出各项属性：

```
JdbcXmlProperty{url='jdbc:mysql://localhost:3306/test', driverClassName='com.mysql.jdbc.Driver', username='root', password='123456'}
```

### 2.5 xml格式被限制的原因

好了，来解答上面那个问题：为了完成跟 `.properties` 文件一样的写法，反而在 xml 中要写这么一大堆乱七八糟的格式，这都哪来的？？？别着急，在这个问题之前，先请小伙伴思考另一个问题：SpringFramework 是怎么加载那些 `.properties` 文件的呢？

答案很简单嘛，肯定是走的 jdk 原生的 `Properties` 类咯。下面咱来解答这个问题。

#### 2.5.1 解析Properties的入口

答案的追踪可以从 `@PropertySource` 注解的一个属性入手：

```java
public @interface PropertySource {
    // ......

	/**
	 * Specify a custom {@link PropertySourceFactory}, if any.
	 * <p>By default, a default factory for standard resource files will be used.
	 * @since 4.3
	 */
	Class<? extends PropertySourceFactory> factory() default PropertySourceFactory.class;
}
```

这里有一个 `factory` 的属性，它自 SpringFramework 4.3 开始出现，它代表的是：**使用什么类型的解析器解析当前导入的资源文件**，说的简单点，它想表达的是,用 `@ProperySource` 注解引入的资源文件需要用什么策略来解析它。默认情况下它只放了一个 `PropertySourceFactory` 在这里，看一眼 `factory` 属性的泛型也能大概猜得出来，`PropertySourceFactory` 应该是一个接口 / 抽象类，它肯定有默认实现的子类。果不其然，借助 IDEA 咱很容易就能找到它在 SpringFramework 中默认的唯一实现：`DefaultPropertySourceFactory` 。

#### 2.5.2 默认的Properties解析工厂

```java
public class DefaultPropertySourceFactory implements PropertySourceFactory {

	@Override
	public PropertySource<?> createPropertySource(@Nullable String name, EncodedResource resource) throws IOException {
		return (name != null ? new ResourcePropertySource(name, resource) : new ResourcePropertySource(resource));
	}
}
```

默认实现中，它只是 new 了一个 `ResourcePropertySource` 而已，而这个构造方法中有一句让我们很敏感的方法调用：`PropertiesLoaderUtils.loadProperties`

```java
public ResourcePropertySource(String name, EncodedResource resource) throws IOException {
    super(name, PropertiesLoaderUtils.loadProperties(resource));
    this.resourceName = getNameForResource(resource.getResource());
}
```

进入这个 `loadProperties` 方法中：

```java
public static Properties loadProperties(EncodedResource resource) throws IOException {
    Properties props = new Properties();
    fillProperties(props, resource);
    return props;
}
```

得了，它的底层果然是这么用的，那问题自然也就解开了。`@PropertySource` 解析 xml 也是用 `Properties` 这个类解析的。可是我们在之前的 JavaSE 中可能没学过 `Properties` 解析 xml 啊，这还第一次听说咧。

#### 2.5.3 【扩展】jdk原生Properties解析xml

其实在 jdk 内置的 `Properties` 类中有这么一个方法可以解析 xml 文件：

```java
public synchronized void loadFromXML(InputStream in) throws IOException, InvalidPropertiesFormatException {
    XmlSupport.load(this, Objects.requireNonNull(in));
    in.close();
}
```

只是这个 xml 的要求，属实有点高，它是 sun 公司在很早之前就制定的一个 xml 表达 properties 的标准：（以下是 dtd 约束文件内容）

```java
<!--
   Copyright 2006 Sun Microsystems, Inc.  All rights reserved.
  -->

<!-- DTD for properties -->

<!ELEMENT properties ( comment?, entry* ) >

<!ATTLIST properties version CDATA #FIXED "1.0">

<!ELEMENT comment (#PCDATA) >

<!ELEMENT entry (#PCDATA) >

<!ATTLIST entry key CDATA #REQUIRED>
```

可以发现确实是有固定格式的，必须按照这个约束来编写 xml 文件。这个东西知道就好了，估计你以后也用不到 ~ ~ ~

#### 2.5.4 properties与xml的对比

对比一下 properties 与 xml 的编写风格：

```properties
jdbc.url=jdbc:mysql://localhost:3306/test
jdbc.driver-class-name=com.mysql.jdbc.Driver
jdbc.username=root
jdbc.password=123456
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE properties SYSTEM "http://java.sun.com/dtd/properties.dtd">
<properties>
    <entry key="xml.jdbc.url">jdbc:mysql://localhost:3306/test</entry>
    <entry key="xml.jdbc.driver-class-name">com.mysql.jdbc.Driver</entry>
    <entry key="xml.jdbc.username">root</entry>
    <entry key="xml.jdbc.password">123456</entry>
</properties>
```

难易程度高下立判，properties 完胜，所以对于这种配置型的资源文件，通常都是使用 properties 来编写。

当然，properties 也不是完全 OK ，由于它的特征是 key-value 的形式，整个文件排下来是没有任何层次性可言的（换句话说，每个配置项之间的地位都是平等的）。这个时候 xml 的优势就体现出来了，它可以非常容易的体现出层次性，不过咱不能因为这一个点就觉得 xml 还可以，因为有一个更适合解决这个问题的配置格式：**yml** 。

## 3. @PropertySource引入yml文件【了解】

接触过 SpringBoot 的小伙伴对 yml 肯定很熟悉了，当然也不乏有一些新学习的小伙伴，所以咱还是在这里简单介绍下 yml 。

### 3.1 yml的语法格式

**yml** 又称 **yaml** ，它是可以代替 properties 同时又可以表达层级关系的标记语言，它的基本格式如下：

```yaml
person: 
  name: zhangsan
  age: 18
  cat: 
    name: mimi
    color: white
dog: 
  name: wangwang
```

可以发现这种写法既可以表达出 properties 的 key-value 形式，同时可以非常清晰的看到层级之间的关系（ cat 在 person 中，person 与 dog 在一个层级）。这种写法同等于下面的 properties ：

```properties
person.name=zhangsan
person.age=18
person.cat.name=mimi
person.cat.color=white
dog.name=wangwang
```

两种写法各有优劣，在 SpringBoot 中这两种写法都予以支持。不过这不是咱本章讨论的重点了，下面咱介绍如何把 yml 引入到 IOC 容器中。

> 本小节源码位置：`com.linkedbear.spring.annotation.i_propertyyml`

### 3.2 声明yml文件

根据上面的 yaml 格式，可以编写出如下 yml 的内容：

```yaml
yml: 
  jdbc:
    url: jdbc:mysql://localhost:3306/test
    driver-class-name: com.mysql.jdbc.Driver
    username: root
    password: 123456
```

### 3.3 编写配置模型类

写法与上面的一模一样，不过 `@Value` 中的 key 前缀改为了 yml ：

```java
@Component
public class JdbcYmlProperty {
    
    @Value("${yml.jdbc.url}")
    private String url;
    
    @Value("${yml.jdbc.driver-class-name}")
    private String driverClassName;
    
    @Value("${yml.jdbc.username}")
    private String username;
    
    @Value("${yml.jdbc.password}")
    private String password;
    
    // 省略getter setter toString
}
```

### 3.4 编写配置类

继续仿照上面的写法，把配置类也造出来：

```java
@Configuration
@ComponentScan("com.linkedbear.spring.annotation.i_propertyyml.bean")
@PropertySource("classpath:propertysource/jdbc.yml")
public class JdbcYmlConfiguration {
    
}
```

### 3.5 测试运行

直接编写启动类，驱动 `JdbcYmlConfiguration` ，取出 `JdbcYmlProperty` 并打印：

```java
public class PropertySourceYmlApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(JdbcYmlConfiguration.class);
        System.out.println(ctx.getBean(JdbcYmlProperty.class).toString());
    }
}
```

运行 `main` 方法，发现属性是一个也没有注入呀：

```
JdbcYmlProperty{url='${yml.jdbc.url}', driverClassName='${yml.jdbc.driver-class-name}', username='${yml.jdbc.username}', password='${yml.jdbc.password}'}
```

小伙伴们是不是又开始 “地铁老人看手机” 了？如果你真的在 “地铁老人看手机” ，那你可得往回翻一翻了哦，上面咱看到解析资源文件的默认实现策略是 `DefaultPropertySourceFactory` ，它是解析 properties 和标准 xml 文件的，要是能把 yml 文件也解析出来，那才奇了怪呢！

```java
    Class<? extends PropertySourceFactory> factory() default PropertySourceFactory.class;
```

那这个时候小伙伴们又有话说了：咋地搁这玩我呐，正经方法不教，净搁这乱跳 ~ ~ ~ 好吧，不闹了，下面介绍如何把 yml 文件也解析出来，并且加载进 IOC 容器。

### 3.6 自定义PropertySourceFactory解析yml

解析 yml 文件，讲道理咱能搞，但是太费劲了，而且现有的开源技术中已经有很成熟的组件能解决 yml 文件的解析，所以咱就来引入一个目前来讲非常成熟，且一直被 SpringBoot 使用的 yml 解析器：snake-yaml 。

#### 3.6.1 导入snake-yaml的maven坐标

在 2020 年 2 月，snake-yaml 升级了 1.26 版本，自此之后很长一段时间没有再升级过，且观察最近几个版本的更新速度也非常慢，基本可以断定它的近几个版本都是很稳定的，于是咱就选择这个 1.26 版本作为 yml 文件的解析底层。

```xml
<dependency>
    <groupId>org.yaml</groupId>
    <artifactId>snakeyaml</artifactId>
    <version>1.26</version>
</dependency>
```

#### 3.6.2 自定义PropertySourceFactory

为了代替原有的 `DefaultPropertySourceFactory` ，就需要咱来自定义一个 `PropertySourceFactory` 的实现了，那就造一个吧，名就叫 `YmlPropertySourceFactory` ：

```java
public class YmlPropertySourceFactory implements PropertySourceFactory {
    
    @Override
    public PropertySource<?> createPropertySource(String name, EncodedResource resource) throws IOException {
        return null;
    }
}
```

之后，把这个 `YmlPropertySourceFactory` 设置到 `@PropertySource` 中：

```java
@PropertySource(value = "classpath:propertysource/jdbc.yml", factory = YmlPropertySourceFactory.class)
```

注意看这个接口的方法，它要返回一个 `PropertySource<?>` ，借助 IDEA 观察它的继承关系，可以发现它里头有一个实现类叫 `PropertiesPropertySource` ：

![img](《从0开始深入学习Spring》/8a17375783cc4a42989f9aeff408281b~tplv-k3u1fbpfcp-zoom-1.image)

那估计咱用这个返回就可以吧！点开它，发现它只有一个公开的构造方法：

```java
public PropertiesPropertySource(String name, Properties source) {
    super(name, (Map) source);
}
```

果然，它只需要传 name 和 `Properties` 对象就可以了。

于是，现在的目标就变成了：如何把 yml 资源文件的对象，转换为 `Properties` 的对象。

#### 3.6.3 资源文件转换为Properties对象

在 snake-yaml 中有一个能快速解析 yml 文件的类，叫 `YamlPropertiesFactoryBean` ，它可以快速加载 `Resource` 并转为 `Properties` ，具体写法可参加下面的实现：

```java
@Override
public PropertySource<?> createPropertySource(String name, EncodedResource resource) throws IOException {
    YamlPropertiesFactoryBean yamlPropertiesFactoryBean = new YamlPropertiesFactoryBean();
    // 传入resource资源文件
    yamlPropertiesFactoryBean.setResources(resource.getResource());
    // 直接解析获得Properties对象
    Properties properties = yamlPropertiesFactoryBean.getObject();
    // 如果@PropertySource没有指定name，则使用资源文件的文件名
    return new PropertiesPropertySource((name != null ? name : resource.getResource().getFilename()), properties);
}
```

> 注意这个 `EncodedResource` ，它就是上一章 2.3 节中提到的封装式资源哦。

### 3.7 重新测试

重新运行 `main` 方法，控制台打印出配置文件的内容，证明 yml 文件解析成功。

```
JdbcYmlProperty{url='jdbc:mysql://localhost:3306/test', driverClassName='com.mysql.jdbc.Driver', username='root', password='123456'}
```

## 小结与练习

1. `@PropertySource` 可以加载什么类型的资源文件？
2. 动手练习 properties 与 yml 的资源文件加载方式，并熟练掌握。

【到这里，IOC 的进阶部分也就结束了，这些难度相对不算很大，主要都是一些特性的使用和了解。下面，我们要进入 IOC 高级部分的学习，这部分难度会更大，接触到的知识深度会更深，小伙伴们如果要深入学习，接下来的这部分一定要好好跟着小册学习哦】

# 22. IOC高级-配置源&配置元信息

从这一章开始，咱开始进入到难度更高的 IOC 高级部分了。对于要深入学习 SpringFramework 中 IOC 的高级特性或者深入原理部分的小伙伴们来讲，这部分真的很重要呀，一定要好好学习哦。

本章介绍 SpringFramework 中的配置源和配置元信息。说到配置源，可能有部分小伙伴的第一反应是：数据源？不是还没到 jdbc 吗？那当然没到啦，配置源是针对 SpringFramework 的，不是对数据库的，这个概念，以及元信息的概念可能理解起来会比较困难，本章会尽可能的用比较容易理解的例子来解释清楚。

## 1. 配置源【理解】

### 1.1 如何理解配置源

**配置源**，简单理解，就是**配置的来源**。在前面的超多例子中，都是使用 xml 配置文件或者注解配置类来驱动 IOC 容器，那么对于 IOC 容器而言，xml 配置文件或者注解配置类就可以称之为配置源。

解释这个概念倒是不难，不过我想请小伙伴们思考一个问题：我们自己写好的配置源给了 Spring 之后，Spring 是如何驱动起整个应用上下文的呢？

这个问题倒是不难回答，Spring 拿到配置源后肯定是**先加载**，**再解析**，**最后注册**那些定义好的 **bean 到 IOC 容器**，这个过程基本也就算结束了。下面咱来简单捋一捋这个过程中配置源的**解析**部分。

### 1.2 配置源的解析思路

咱现在已经学过的配置源就是 xml 配置文件，以及注解配置类两种，咱分别来看。

#### 1.2.1 xml配置文件

仔细端倪一会之前写过的 xml 配置文件：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd http://www.springframework.org/schema/context https://www.springframework.org/schema/context/spring-context.xsd">

    <context:component-scan base-package="com.linkedbear.spring.basic_di.c_value_spel.bean"/>

    <context:property-placeholder location="classpath:basic_di/value/red.properties"/>

    <bean id="person" class="com.linkedbear.spring.basic_di.a_quickstart_set.bean.Person">
        <property name="name" value="test-person-byset"/>
        <property name="age" value="18"/>
    </bean>
</beans>
```

这个 xml 中包含几个部分：

- xml 头信息
- `component-scan` 声明包扫描
- `property-placeholder` 引入外部 properties 文件
- `<bean>` 注册 bean 并属性赋值

再思考一个问题：为什么在 xml 中能写这些标签呢？很简单，xml 头上的那些约束声明的可以写呗。

那 xml 头上的约束又是从哪来的呢？当然是 SpringFramework 中的 jar 包自带的呗。

> 那 jar 包是哪里来。。。【给劳资停下！tm说什么狗话呢？】皮一下很开心 ~ ~ ~
>
> ![img](《从0开始深入学习Spring》/013c67e797f74e4b8452b23c2ca46980~tplv-k3u1fbpfcp-zoom-1.image)

思考到这里就可以了，要是真的问 jar 包是哪里来的，可能不出 10 个问题，我们就要开始思考人生了。。。

回到正题上，xml 中定义的这些信息，如果给这些信息一个定义，那它们就可以这样解释：

- xml 中包含 1 条组件扫描的声明
- 包含一条 properties 资源文件引入的声明
- 包含一个 bean 的注册

于是这个 xml 可以用如下的一种抽象语言描述：

```
beans.xml {
    context: [component-scan, property-placeholder]
    beans: [person]
}
```

这里面不会描述具体的组件扫描路径等等，只会**记录这个 xml 中声明了哪些标签**。

#### 1.2.2 注解配置类

跟上面一样，咱先找一个之前写过的注解配置类：

```java
@Configuration
@ComponentScan("com.linkedbear.spring.bean.b_scope.bean")
public class BeanScopeConfiguration {
    
    @Bean
    public Child child1(Toy toy) {
        Child child = new Child();
        child.setToy(toy);
        return child;
    }
    
    @Bean
    public Child child2(Toy toy) {
        Child child = new Child();
        child.setToy(toy);
        return child;
    }
}
```

根据上面的抽象思维，这个注解配置类也可以进行如下转换：

```
BeanScopeConfiguration.java: {
    annotations: [ComponentScan]
    beans: [child1, child2]
}
```

与上面一样，只会记录配置类中的**配置结构**而已，任何配置信息都不会体现在这里面。

> 注意，这个解析思路仅仅是我们自己分析的，与 SpringFramework 没有关系。

## 2. 元信息【理解】

突然跳到元信息的章节了，是不是有点猝不及防？先缓缓神，想想上面为什么会叨叨这个解析思路呢？

也或者，可能会有一些小伙伴产生一种感觉：这种解析思路像是把**整个文件中配置的所有定义都抽取出来**了，形成了一个类似于**配置定义信息**的东西。

好，如果真的有这个感觉，请一直保持住；如果没有感觉到，那也没有关系，咱来解释一下这里头的重要概念：**元信息**。

### 2.1 如何理解元信息

> 我们不讲究那些通用的概念哈，仅仅是针对 SpringFramework 而言，所以不会涉及到像数据分析与数据挖掘这样的概念进来。

**元信息**，又可以理解为**元定义**，简单的说，它就是**定义的定义**。

干说太抽象，直接上例子吧，方便理解：

- 张三，男，18岁
  - 它的元信息就是它的属性们：`Person {name, age, sex}`
- 咪咪，美国短毛，黑白毛，主人是张三
  - 它的元信息可以抽取为：`Cat {name, type, color, master}`

写到这里是不是突然产生一种感觉：这不就是**对象和类**吗？？？是的，所以我们可以这样说：**类中包含对象的元信息**。

想一个小问题，类有元信息吗？当然有，**`Class`** 这个类里面就包含一个类的所有定义（属性、方法、继承实现、注解等），所以我们可以说：**`Class` 中包含类的元信息**。

再举一个小伙伴们都比较熟悉的吧：数据库表与表结构信息，这也是非常典型的**信息与元信息**：数据库表结构描述了数据库表的整体表属性，以及表字段的属性。

### 2.2 SpringFramework中的配置元信息

理解了元信息的概念，接下来就可以来看 SpringFramework 中的元信息了。不过在 SpringFramework 中涉及到的元信息更多，咱先从最熟悉的开始看。

#### 2.2.1 Bean的定义元信息【重点】

跟上面的 Class 描述类相似，SpringFramework 中定义的 Bean 也会封装为一个个的 Bean 的元信息，也就是 **`BeanDefinition`** 。它包含了一个 Bean 所需要的几乎所有维度的定义：

- Bean 的全限定名 className
- Bean 的作用域 scope
- Bean 是否延迟加载 lazy
- Bean 的工厂 Bean 名称 factoryBean
- Bean 的构造方法参数列表 constructorArgumentValues
- Bean 的属性值 propertyValues
- ......

可以发现，通过这些定义，基本上一个 Bean 的所有特征、属性就全部都描述出来了。

有关 `BeanDefinition` 的内容，咱们放到后面专门开 2 章来讲解，这里先一带而过了。

#### 2.2.2 IOC容器的配置元信息【了解】

IOC 容器的配置元信息分为 beans 和 context 两部分，分别展开来看。

##### 2.2.2.1 beans的配置元信息

IOC 容器本身也是有元信息的，只不过这些元信息咱基本没怎么接触。以 xml 配置文件为例，如果你仔细注意一下整个配置文件的最顶层标签，会发现 `<beans>` 其实是有属性的：

![img](《从0开始深入学习Spring》/1bd653d381db4bc0a9483ae256fb3df0~tplv-k3u1fbpfcp-zoom-1.image)

只不过这些属性我们几乎不怎么用，都是用它默认的值了。

这个时候可能会有小伙伴一脸楞逼了，我去这都哪来的，我咋不知道呢，还有默认值呢？好吧没有关系，咱下面列出来这些属性的含义和默认值。

| 配置元信息                  | 含义 / 作用                                                  | 默认值           |
| --------------------------- | ------------------------------------------------------------ | ---------------- |
| profile                     | 基于环境的配置                                               | ""               |
| default-autowire            | 默认的自动注入模式（不需要声明 `@Autowired` 等注解即可注入组件） | default（no）    |
| default-autowire-candidates | 满足指定属性名规则的属性才会被自动注入                       | ""               |
| default-init-method         | 全局 bean 的初始化方法                                       | ""               |
| default-destroy-method      | 全局 bean 的销毁方法                                         | ""               |
| default-lazy-init           | 全局 bean 是否延迟加载                                       | default（false） |
| default-merge               | 继承父 bean 时直接合并父 bean 的属性值                       | default（false） |



> 注：默认值中提到的 default 是在没有声明时继承父配置的默认值（ `<beans>` 标签是可以嵌套使用的），如果都没有声明，则配置的默认值是括号内的值。

##### 2.2.2.2 context的配置元信息

除此之外，还有一部分 IOC 容器的配置源信息来自于 `spring-context` 包的 context 前缀标签中（如之前写过的 `<component-scan />` 标签）。

![img](《从0开始深入学习Spring》/6c4a59d8759a4ceebf0f8c7920da304f~tplv-k3u1fbpfcp-zoom-1.image)

同样的，咱也把这些配置元信息都列出来，小伙伴们对里面几个相对常见的配置有一个了解即可。

| 配置元信息                        | 含义 / 作用                                               |
| --------------------------------- | --------------------------------------------------------- |
| `<context:annotation-config/>`    | 开启注解驱动                                              |
| `<context:component-scan/>`       | 开启组件扫描                                              |
| `<context:property-placeholder/>` | 引入外部的资源文件（ properties xml yml 等）              |
| `<context:property-override/>`    | 指定配置源会覆盖全局配置（可用于配置覆盖）                |
| `<context:spring-configured/>`    | 可以对没有注册到 IOC 容器的 bean 实现依赖注入             |
| `<context:load-time-weaver/>`     | 与 AOP 相关（放到 AOP 章节介绍）                          |
| `<context:mbean-server/>`         | 暴露应用运行状态监控（与 JMX 管理监控有关）               |
| `<context:mbean-export/>`         | 注册 MBean 到 JMX 实现运行状态监控（与 JMX 管理监控有关） |



相对比较常用的标签是前三个，小伙伴们只需要对前三个比较了解即可。

到这里，针对 IOC 容器的基本配置也就都列举完毕了，需要了解的不多，而且大多都接触过了，小伙伴们注意巩固前面的知识点即可。

### 2.3 beans的其他配置元信息

前面介绍 `<beans>` 的配置元信息中，只是介绍了 `<beans>` 标签的属性，在 beans 的命名空间里还有两个常用的标签，而且也都比较简单：

| 配置元信息   | 含义 / 作用                 | 使用方式举例                                                 |
| ------------ | --------------------------- | ------------------------------------------------------------ |
| `<alias />`  | 给指定的 bean 指定别名      | `<alias name="person" alias="zhangsan"/>`                    |
| `<import />` | 导入外部现有的 xml 配置文件 | `<import resource="classpath:basic_dl/quickstart-byname.xml"/>` |



使用方式也比较简单，小伙伴们可以自行试探着借助 IDEA 写一写。

### 2.4 properties等配置元信息

上一章我们反复研究的 properties 、xml 、yml 文件，它们的作用都是为了将具体的配置抽取为一个可任意修改的配置文件，防止在程序代码中出现硬编码配置，导致修改配置还需要重新编译的麻烦。这种**将配置内容抽取为配置文件**的动作，我们称之为 **“配置外部化”**，抽取出来的配置文件又被成为 **“外部化配置文件”** （其实这个概念在第 3 章 4.2 节就提过了）。而加载这些外部化配置文件的方式，要么通过上面的 `<context:property-placeholder/>` ，要么通过 `@PropertySource` 注解，它们最终都会被封装为一个一个的 `PropertySource` 对象（ properties 文件被封装为 `PropertiesPropertySource` ）了，而这个 `PropertySource` 对象内部就持有了这些外部化配置文件的所有内容。

这部分在上一章已经介绍的很多啦，这里就不再赘述了。

到这里，差不多 SpringFramework 中的配置源和配置元信息就介绍的差不多了，不过还没有完全介绍完，后面还会有一部分是 Java 编程式驱动 IOC ，届时也会有一部分元信息的提及。

多啰嗦一句，这个**元信息**的概念会贯穿整个 IOC 高级和后面的原理部分，非常重要，小伙伴一定要建立起这个概念来呀。

## 小结与思考

1. SpringFramework 中的配置源通常有哪些？
2. SpringFramework 中的配置元信息包含哪几部分？分别的代表是什么？

【上一章的 `@PropertySource` 和这一章的配置元信息中都提到了 properties 等资源文件的加载，最终它们都去哪里了？IOC 容器中的组件属性又是从哪里获得的来源呢？下一章我们就要接触这个很重要的概念了：**`Environment`** 】

# 23. IOC高级-Environment抽象

上一章的最后，小册提出了一个问题：加载的 properties 资源配置，以及 `ApplicationContext` 内部的一些默认配置属性，都放在哪里了？组件 Bean 又是怎么把配置值注入进去到对象的属性中的？本章就会解答这些问题。

## 1. Environment概述【理解】

先对 `Environment` 有一个大体的认识吧。`Environment` 是从 SpringFramework 3.1 开始引入的一个抽象模型，之前咱在第 4 章 SpringFramework 概述中也提过它的出现时机了。至于抽象模型，和具体的理解，我想小伙伴们可以先自行思索一下。

【以下内容可能比较啰里八嗦，想直接拿来面试的小伙伴请直接移步 1.5 节】

### 1.1 第一感觉

其实第一眼看到这个名词，我们就应该有一个模糊的猜想了，它应该是基于 SpringFramework 的工程的**运行时环境**。所以我们可以这样看待我们编写的基于 SpringFramework 的应用程序：

![img](《从0开始深入学习Spring》/461c0349a0964aa8925dc92648796803~tplv-k3u1fbpfcp-zoom-1.image)

> 这个概念的理解，在 SpringBoot 源码的小册中也有提过，当时也是画了这样一个概念图来帮助小伙伴们理解。

这个理解是否正确呢？我们可以去官方文档加以验证。

### 1.2 官方文档的描述

当我们去翻 SpringFramework 的官方文档时，会发现官方是这样概述 `Environment` 的：

[docs.spring.io/spring/docs…](https://docs.spring.io/spring/docs/5.2.x/spring-framework-reference/core.html#beans-environment)

> The `Environment` interface is an abstraction integrated in the container that models two key aspects of the application environment: profiles and properties. A profile is a named, logical group of bean definitions to be registered with the container only if the given profile is active. Beans may be assigned to a profile whether defined in XML or with annotations. The role of the `Environment` object with relation to profiles is in determining which profiles (if any) are currently active, and which profiles (if any) should be active by default. Properties play an important role in almost all applications and may originate from a variety of sources: properties files, JVM system properties, system environment variables, JNDI, servlet context parameters, ad-hoc `Properties` objects, `Map` objects, and so on. The role of the `Environment` object with relation to properties is to provide the user with a convenient service interface for configuring property sources and resolving properties from them.
>
> `Environment` 接口是集成在容器中的抽象，可对应用程序环境的两个关键方面进行建模：Profile 和 properties 。 Profiles 是仅在指定 profile 处于活动状态（ active ）时才向容器注册 `BeanDefinition` 的命名逻辑组。它可以将 Bean 分配给不同的 profile （无论是以 XML 定义还是注解配置）。与配置文件相关的 `Environment` 作用是确定哪些配置文件当前处于活动状态，以及哪些配置文件在默认情况下应处于活动状态。 Properties 在几乎所有应用程序中都起着重要作用，并且可能源自多种来源：属性文件，JVM 系统属性，系统环境变量，JNDI，`ServletContext` 参数，临时属性对象，`Map` 对象等。`Environment` 与属性相关联的作用是为用户提供方便的接口，它可以用于配置属性源，并从 `Environment` 中解析属性。

讲道理这段话理解起来不是那么容易，不过第一句【`Environment` 是集成在容器中的抽象】，会让我们产生一种感觉：前面的理解是不是出现了一些偏差？如果按照官方文档的说法，`Environment` 与工程的结构应该是这样才对：

![img](《从0开始深入学习Spring》/5166a2a211cf4cb1a36a6bb4f5232755~tplv-k3u1fbpfcp-zoom-1.image)

到底是不是这样呢，根据个人的理解不同，表达出来的也会不太一样。

### 1.3 小册一家之言

作者个人是倾向于如下的结构理解，这样解释起来会相对更合理一些：

- 首先，`Environment` 中包含 profiles 和 properties ，这些配置信息会影响 IOC 容器中的 bean 的注册与创建；
- 其次，`Environment` 的创建是在 `ApplicationContext` 创建后才创建的（ IOC 原理部分会解释），所以 `Environment` 应该是伴随着 `ApplicationContext` 的存在而存在；
- 第三，`ApplicationContext` 中同时包含 `Environment` 和组件 bean ，而且从 `BeanFactory` 的视角来看，`Environment` 也是一个 Bean ，只不过它的地位比较特殊。

基于这三点，`Environment` 与工程的结构应该是下图这样的：

![img](《从0开始深入学习Spring》/07df885666e94a248600430502779905~tplv-k3u1fbpfcp-zoom-1.image)

理解了两者的结构及关系，再来回头看看 `Environment` 的组成部分：**profiles 和 properties** ，咱之前也都了解过了，所以 `Environment` 的整体理解也就相对没有那么难了吧！

### 1.4 javadoc中的描述

上面并没有引用 `Environment` 的 javadoc 来阐述 `Environment` 的概念和定义，原因是 javadoc 并没有对 Application 和 `Environment` 之间的关系进行描述，所以小册选择在这里再贴出。

由于 javadoc 的篇幅太长，咱们拆解开来看。

#### 1.4.1 Environment包含profile于properties

> Interface representing the environment in which the current application is running. Models two key aspects of the application environment: profiles and properties. Methods related to property access are exposed via the `PropertyResolver` superinterface.
>
> `Environment` 是表示当前应用程序正在其中运行的环境的接口。它为应用环境制定了两个关键的方面：**profile** 和 **properties**。与属性访问有关的方法通过 `PropertyResolver` 这个父接口公开。

这一段也是总体的概括 `Environment` 的基本设计和作用，不过它又提到了 `PropertyResolver` 这个接口，这个接口负责解析占位符（ **${...}** ）对应的值，作用也比较容易理解，这里就不多展开解释啦。

#### 1.4.2 profile用于区分不同的环境模式

> A profile is a named, logical group of bean definitions to be registered with the container only if the given profile is active. Beans may be assigned to a profile whether defined in XML or via annotations; see the `spring-beans 3.1 schema` or the `@Profile` annotation for syntax details. The role of the `Environment` object with relation to profiles is in determining which profiles (if any) are currently active, and which profiles (if any) should be active by default. profile 机制保证了仅在给定 profile 处于激活状态时，才向容器注册的 `BeanDefinition` 的命名逻辑组。无论是用 XML 定义还是通过注解定义，都可以将 Bean 分配给指定的 profile。有关语法的详细信息，请参见 `spring-beans 3.1规范文档` 或 `@Profile` 注解。`Environment` 的作用是决定当前哪些配置文件（如果有）处于活动状态，以及默认情况下哪些配置文件（如果有）应处于活动状态。

通过前面 18 章条件装配的学习，这段文档注释也就不难理解了吧。`Environment` 配合 profile 可以完成**指定模式的环境的组件装配**，以及不同的配置属性注入。

#### 1.4.3 properties用于配置属性和注入值

> Properties play an important role in almost all applications, and may originate from a variety of sources: properties files, JVM system properties, system environment variables, JNDI, servlet context parameters, ad-hoc Properties objects, Maps, and so on. The role of the environment object with relation to properties is to provide the user with a convenient service interface for configuring property sources and resolving properties from them. `Properties` 在几乎所有应用程序中都起着重要作用，并且可能来源自多种途径：属性文件，JVM 系统属性，系统环境变量，JNDI，`ServletContext` 参数，临时属性对象，Map等。`Environment` 与 `Properties` 的关系是为用户提供方便的服务接口，以配置属性源，并从中解析属性值。

上一章的配置元信息中我们已经知道 properties 的最大作用之一是做**外部化配置**，`Environment` 中存放了很多 properties ，它们的来源有很多种，而最终的作用都是**提供了属性配置**，或者**给组件注入属性值**。

#### 1.4.4 Environment不建议直接使用

> Beans managed within an `ApplicationContext` may register to be `EnvironmentAware` or `@Inject` the Environment in order to query profile state or resolve properties directly. In most cases, however, application-level beans should not need to interact with the Environment directly but instead may have to have ${...} property values replaced by a property placeholder configurer such as `PropertySourcesPlaceholderConfigurer`, which itself is EnvironmentAware and as of Spring 3.1 is registered by default when using `<context:property-placeholder/>`.
>
> 在 `ApplicationContext` 中管理的 Bean 可以注册为 `EnvironmentAware` 或使用 `@Inject` 标注在 `Environment` 上，以便直接查询 profile 的状态或解析 `Properties`。 但是，在大多数情况下，应用程序级 Bean 不必直接与 `Environment` 交互，而是通过将 **${...}** 属性值替换为属性占位符配置器进行属性注入（例如 `PropertySourcesPlaceholderConfigurer`），该属性本身是 `EnvironmentAware`，当配置了 `<context:property-placeholder/>` 时，默认情况下会使用 Spring 3.1 的规范注册。

这一段的描述主要讲了两件事情：`Environment` 可以注入到组件中，用于获取当前环境激活的所有 profile 模式；但是又不推荐开发者直接使用它，而是通过占位符注入配置属性的值。为什么会这么说呢，其实这个又要说回 `Environment` 设计的原始意图。`Environment` 的设计本身就应该是一个**不被应用程序接触到的 “环境”** ，我们**只能从环境中获取一些它已经有的信息，但不应该获取它本身**。所以，在处理 properties 的获取时，直接使用占位符就可以获取了。

#### 1.4.5 ApplicationContext获取到的是ConfigurableEnvironment

> Configuration of the environment object must be done through the `ConfigurableEnvironment` interface, returned from all `AbstractApplicationContext` subclass `getEnvironment()` methods. See `ConfigurableEnvironment Javadoc` for usage examples demonstrating manipulation of property sources prior to application context `refresh()` .
>
> 必须通过从所有 `AbstractApplicationContext` 子类的 `getEnvironment()` 方法返回的 `ConfigurableEnvironment` 接口完成环境对象的配置。请参阅 `ConfigurableEnvironment` 的 javadoc 以获取使用示例，这些示例演示在应用程序上下文 `refresh()` 方法被调用之前对属性源进行的操作。

注意这里，`ApplicationContext` 的根实现类 `AbstractApplicationContext` 获取到的是 `ConfigurableEnvironment` ，它具有 **“可写”** 的特征，换言之我们可以修改它内部的属性值 / 数据。不过话又说回来，通常情况下我们都不会直接改它，除非要对 SpringFramework 应用的启动流程或者运行中进行一些额外的扩展或者修改。

到这里，整个 javadoc 也就读完了，最后总结一下吧，这部分最终还是要理解，并且最好用自己的话概括出来。

### 1.5 【面试题】面试中如何概述Environment

以下答案仅供参考，可根据自己的理解调整回答内容：

**`Environment` 是 SpringFramework 3.1 引入的抽象的概念，它包含 profiles 和 properties 的信息，可以实现统一的配置存储和注入、配置属性的解析等。其中 profiles 实现了一种基于模式的环境配置，properties 则应用于外部化配置。**

## 2. Environment的结构【了解】

了解了概念和设计的思想，下面咱来看看 `Environment` 在 SpringFramework 中设计的结构。

借助 IDEA ，可以看到 `Environment` 的上下级继承和派生关系：

![img](《从0开始深入学习Spring》/7ace9b0f0c144ca4a49e3083fbece4eb~tplv-k3u1fbpfcp-zoom-1.image)

这里面的几个重要的接口和类关注一下。

### 2.1 PropertyResolver

这个接口，只从接口名就知道它应该是处理占位符 **${}** 的。观察接口的方法定义，直接实锤了它就是做配置属性值的获取和解析的：（下面是 `PropertyResolver` 的部分方法定义）

```java
public interface PropertyResolver {

    // 检查所有的配置属性中是否包含指定key
    boolean containsProperty(String key);

    // 以String的形式返回指定的配置属性的值
    String getProperty(String key);

    // 带默认值的获取
    String getProperty(String key, String defaultValue);

    // 指定返回类型的配置属性值获取
    <T> T getProperty(String key, Class<T> targetType);

    // ......

    // 解析占位符
    String resolvePlaceholders(String text);

    // ......
}
```

所以由此也就证明了：**`Environment` 可以获取配置元信息，同时也可以解析占位符的信息**。

### 2.2 ConfigurableEnvironment

老套路了，看到 **Configurable** 开头，立马应该想到它又扩展了什么 set 方法吧！果然，可以从接口的方法定义中看到这样的方法名：`setActiveProfiles` 、`addActiveProfile` 。。。好了不用说了，这个接口一定可以用编程式设置 profile ！

除此之外，这个接口中还有一个方法比较值得注意：

```java
    MutablePropertySources getPropertySources();
```

看方法名可以知道它会返回所有的 `PropertySource` 对象，可是 `MutablePropertySources` 是个什么鬼呢？点开它的源码，发现它的内部就是一个 **List** ：

```java
public class MutablePropertySources implements PropertySources {

	private final List<PropertySource<?>> propertySourceList = new CopyOnWriteArrayList<>();
```

由此可以总结出一个小小的结论：**Mutable 开头的类名，通常可能是一个类型的 List 组合封装**。

### 2.3 StandardEnvironment

它是 SpringFramework 中默认使用的标准运行时环境的抽象实现，不过它里面的方法实现的非常少，基本都是由 `AbstractEnvironment` 负责实现。在后面的原理部分，我们还会再见到它的，这里先留意一下就好。

## 3. Environment的基本使用【熟悉】

虽说 `Environment` 不建议直接在应用程序中使用，但是部分场景下还是需要直接接触它来操纵。本节小册不会直接介绍 `Environment` 的实际使用，而是先带小伙伴用最简单的方式用一用，体会一下 `Environment` 的作用即可。

> 本章源码均在 `com.linkedbear.spring.environment`

### 3.1 获得Environment的API

既然 `Environment` 存在于 `ApplicationContext` 中，那么获取 `Environment` 的方式自然也就可以想到：`@Autowired` 就可以吧！下面咱来实际操作一下。

任意编写一个 Bean ，并声明注入 `Environment` ：

```java
@Component
public class EnvironmentHolder {
    
    @Autowired
    Environment environment;
    
    public void printEnvironment() {
        System.out.println(environment);
    }
}
```

之后直接使用包扫描的方式，驱动 `AnnotationConfigApplicationContext` ，就可以取到刚写的这个 `EnvironmentHolder` 了：

```java
public class EnvironmentQuickstartApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                "com.linkedbear.spring.environment.a_quickstart.bean");
        EnvironmentHolder environmentHolder = ctx.getBean(EnvironmentHolder.class);
        environmentHolder.printEnvironment();
    }
}
```

运行 `main` 方法，控制台会打印出 `Environment` 的对象信息：

```
StandardEnvironment {activeProfiles=[], defaultProfiles=[default], propertySources=[PropertiesPropertySource {name='systemProperties'}, SystemEnvironmentPropertySource {name='systemEnvironment'}]}
```

除此之外，联想到 `BeanFactory` 、`ApplicationContext` 的注入方式还有回调注入，作为 SpringFramework 的内置 API ，估计也会有一个 **Aware** 回调注入的接口吧！那自然是必须的，`EnvironmentAware` 就是回调注入的接口，小伙伴们可以自行实现操作一下，小册这里就不示范了（实在是简单的一批）。

> 注：使用 `@Autowired` 的方式在某些情况下会注入失败，所以对于小伙伴们而言，注入是否能成功需要亲手测试运行检验才能知道。在后面的后置处理器部分，会演示一种无法使用 `@Autowired` 注入 `Environment` 的方式，小伙伴们到时候可以留意一下。

### 3.2 使用Environment获取配置属性的值

既然上面已经获取到 `Environment` 了，那操作 `Environment` 的方法自然也就不是问题了。

为了方便获取 properties 的配置信息，这里编写一个配置类，把上一章 `PropertySource` 的 `jdbc.properties` 加载进去：

```java
@Configuration
@ComponentScan("com.linkedbear.spring.environment.b_api.bean")
@PropertySource("propertysource/jdbc.properties")
public class EnvironmentPropertyConfiguration {
    
}
```

之后使用该配置类驱动 IOC 容器即可。

`EnvironmentHolder` 中，这次我们取一下默认的 profiles ，以及 `jdbc.properties` 中的配置属性值：

```java
@Component
public class EnvironmentHolder {
    
    @Autowired
    Environment environment;
    
    public void printEnvironment() {
        System.out.println(Arrays.toString(environment.getDefaultProfiles()));
        System.out.println(environment.getProperty("jdbc.url"));
    }
}
```

重新驱动 IOC 容器，并取出 `EnvironmentHolder` 执行 `printEnvironment` 方法，控制台打印如下信息：

```
[default]
jdbc:mysql://localhost:3306/test
```

至此，`Environment` 的功能已正常使用。

`Environment` 中其他的 API ，小伙伴都可以自己动手使用一下，小册就不展开举例了。下面我们来向更深层次研究几个问题。

## 4. Environment深入探讨【原理】

先注意一下上面控制台打印的默认 profiles ，发现它有一个默认值是 **default** ，它是从哪来的呢？我们又没声明呀！

### 4.1 Environment的默认profiles

想知道 profiles 的默认配置，就要进入到 `Environment` 的抽象实现 `AbstractEnvironment` 中了：

```java
@Override
public String[] getDefaultProfiles() {
    return StringUtils.toStringArray(doGetDefaultProfiles());
}
```

看，这里有一个很有意思的操作：`getDefaultProfiles` 调用了 `doGetDefaultProfiles` 方法，**这个设计在 SpringFramework 中大量出现和使用**！

#### 4.1.1 SpringFramework中的方法命名规范【重要】

在 SpringFramework 的框架编码中，如果有出现一个方法是 do 开头，并且去掉 do 后能找到一个与剩余名称一样的方法，则代表如下含义：**不带 do 开头的方法一般负责前置校验处理、返回结果封装，带 do 开头的方法是真正执行逻辑的方法（如 `getBean` 方法的底层会调用 `doGetBean` 来真正的寻找 IOC 容器的 bean ，`createBean` 会调用 `doCreateBean` 来真正的创建一个 bean ）。**

#### 4.1.2 doGetDefaultProfiles的实现

```java
public static final String DEFAULT_PROFILES_PROPERTY_NAME = "spring.profiles.default";

protected Set<String> doGetDefaultProfiles() {
    synchronized (this.defaultProfiles) {
        // 取框架默认的profiles，并与当前的对比
        if (this.defaultProfiles.equals(getReservedDefaultProfiles())) {
            // 如果一致，则尝试从Environment中获取显式声明的profiles
            String profiles = getProperty(DEFAULT_PROFILES_PROPERTY_NAME);
            // 如果有显式声明，则覆盖原有的默认值
            if (StringUtils.hasText(profiles)) {
                setDefaultProfiles(StringUtils.commaDelimitedListToStringArray(
                        StringUtils.trimAllWhitespace(profiles)));
            }
        }
        return this.defaultProfiles;
    }
}
```

看这个方法的实现，整体逻辑也不算复杂，关键是看它取框架默认的 profiles ，它其实就是取的 `AbstractEnvironment` 中内置的常量：

```java
protected static final String RESERVED_DEFAULT_PROFILE_NAME = "default";

protected Set<String> getReservedDefaultProfiles() {
    return Collections.singleton(RESERVED_DEFAULT_PROFILE_NAME);
}
```

由此，可知默认的 default 来源。

#### 4.1.3 覆盖默认的profiles方法

上面的源码中，也可以看到，我们可以通过声明 **`spring.profiles.default`** 的配置，来覆盖 SpringFramework 中原有的默认 profiles ，一个比较常用的方法是在 jvm 的启动参数上添加：

![img](《从0开始深入学习Spring》/1b2c5bf327624be2ac918edecfdf7f20~tplv-k3u1fbpfcp-zoom-1.image)

在 IDEA 的启动配置中，声明 VM options 就可以指定默认的 profiles 了。

同理，指定激活的 profiles 也可以像这样指定，只不过它的参数名称为 **`spring.profiles.active`** 。

### 4.2 Environment解析properties的底层

前面看 `Environment` 的结构，我们已经知道 `Environment` 继承了父接口 `PropertyResolver` ，自然它拥有解析配置元信息的能力，它的底层是如何实现的呢？是 `Environment` 自己干活，还是...有其人？

#### 4.2.1 PropertyResolver的实现类

借助 IDE ，翻看 PropertyResolver 的子接口和实现类，发现仅仅就这么几个而已：

![img](《从0开始深入学习Spring》/28a65c7615f54444ae97480dbb97300d~tplv-k3u1fbpfcp-zoom-1.image)

自然地，我们要去找 `Environment` 的实现类，`StandardEnvironment` ，看它是如何解析配置属性值的。

#### 4.2.2 getProperty的实现是委派

翻看 `StandardEnvironment` ，发现 `getProperty` 方法并没有在此实现，而是父类 `AbstractEnvironment` 中，但是实现类中发现它是直接调用了自身组合的一个 `ConfigurablePropertyResolver` 来处理（果然环境本身不适合干这个事，得让专门的组件来干）：

```java
private final ConfigurablePropertyResolver propertyResolver =
        new PropertySourcesPropertyResolver(this.propertySources);

@Override
@Nullable
public String getProperty(String key) {
    return this.propertyResolver.getProperty(key);
}
```

一般的，我们称这种方式叫做 **“委派”** ，它与代理、装饰者不同：**委派仅仅是将方法的执行转移给另一个对象，而代理可能会在此做额外的处理，装饰者也会在方法执行前后做增强**。

继续往里看，就要进入 `PropertySourcesPropertyResolver` 的底层来研究了，小册认为再往里研究的性价比相对就不高了：这里面的解析逻辑相对复杂，但搞明白后的收益并不大，综合来看不太适合再深入研究。小伙伴们只需要了解 `Environment` 的解析配置属性值的底层是交给 `PropertySourcesPropertyResolver` 来处理就好啦。

## 小结与思考

1. `Environment` 是什么？它与 `ApplicationContext` 的关系是什么？
2. `Environment` 都具有什么功能？
3. `Environment` 与 profile 的关系是什么？如何获取和设置 profile ？

【了解了配置元信息中的环境部分，下面到了 IOC 高级部分可能是最重要的部分：**Bean** 与 **BeanDefinition** ，它是 bean 的元信息。这部分非常重要，小伙伴一定要认真学习这部分哦】

# 24. IOC高级-Bean与BeanDefinition

前面，我们了解了 `Environment` 抽象，以及元信息的概念。在元信息中小册提到了那个拖了好久的概念：`BeanDefinition` ，现在终于到了要解答它的时候了！这个概念相当重要，理解 `BeanDefinition` 有助于我们更深入的进入 SpringFramework 的核心原理内部探索。

## 1. BeanDefinition概述【熟悉】

还是跟往常一样，先对 `BeanDefinition` 有一个整体的认识。

前面我们已经知道，`BeanDefinition` 也是一种**配置元信息**，它描述了 **Bean 的定义信息**。下面咱还是通过多个途径来试着了解 `BeanDefinition` 的概念。

【以下内容可能比较啰里八嗦，想直接拿来面试的小伙伴请直接移步 1.4 节】

### 1.1 官方文档

官方文档对于 `BeanDefinition` 的介绍并没有使用很大的篇幅，基本也只是概述一下就完事了：

[docs.spring.io/spring/docs…](https://docs.spring.io/spring/docs/5.2.x/spring-framework-reference/core.html#beans-child-bean-definitions)

> A bean definition can contain a lot of configuration information, including constructor arguments, property values, and container-specific information, such as the initialization method, a static factory method name, and so on. A child bean definition inherits configuration data from a parent definition. The child definition can override some values or add others as needed. Using parent and child bean definitions can save a lot of typing. Effectively, this is a form of templating.
>
> bean 的定义信息可以包含许多配置信息，包括构造函数参数，属性值和特定于容器的信息，例如初始化方法，静态工厂方法名称等。子 bean 定义可以从父 bean 定义继承配置数据。子 bean 的定义信息可以覆盖某些值，或者可以根据需要添加其他值。使用父 bean 和子 bean 的定义可以节省很多输入（实际上，这是一种模板的设计形式）。

文档已经解释的比较清楚了，bean 的定义就是包含了这个 bean 应该有的所有重要信息，并且它又提到了一个概念：bean 的定义信息也是有**层次性**的（联想 `BeanFactory` 的层次性），bean 的定义信息可以继承自某个已经有的定义信息，并覆盖父信息的一些配置值（而且文档最后也说了这相当于模板的设计）。

### 1.2 javadoc

翻开 `BeanDefinition` 接口的 javadoc ，里面写的不多，不过也已经很精确的说明了 `BeanDefinition` 的基本作用：

> A BeanDefinition describes a bean instance, which has property values, constructor argument values, and further information supplied by concrete implementations. This is just a minimal interface: The main intention is to allow a BeanFactoryPostProcessor such as PropertyPlaceholderConfigurer to introspect and modify property values and other bean metadata.
>
> `BeanDefinition` 描述了一个 bean 的实例，该实例具有属性值，构造函数参数值以及具体实现所提供的更多信息。 这只是一个最小的接口，它的主要目的是允许 `BeanFactoryPostProcessor`（例如 `PropertyPlaceholderConfigurer` ）内省和修改属性值和其他 bean 的元数据。

对比起官方文档，javadoc 额外提了编码设计中 `BeanDefinition` 的使用：`BeanFactoryPostProcessor` 可以任意修改 `BeanDefinition` 中的信息。这里面又提到了一个 `BeanFactoryPostProcessor` 的概念，不要着急不要慌张，后面我们马上就学到后置处理器的部分，自然就都学到啦 ~

### 1.3 BeanDefinition接口的方法定义

借助 IDE ，打开 `BeanDefinition` 的接口定义，从方法列表上看，`BeanDefinition` 整体包含以下几个部分：

- Bean 的类信息 - 全限定类名 ( beanClassName )
- Bean 的属性 - 作用域 ( scope ) 、是否默认 Bean ( primary ) 、描述信息 ( description ) 等
- Bean 的行为特征 - 是否延迟加载 ( lazy ) 、是否自动注入 ( autowireCandidate ) 、初始化 / 销毁方法 ( initMethod / destroyMethod ) 等
- Bean 与其他 Bean 的关系 - 父 Bean 名 ( parentName ) 、依赖的 Bean ( dependsOn ) 等
- Bean 的配置属性 - 构造器参数 ( constructorArgumentValues ) 、属性变量值 ( propertyValues ) 等

由此可见，`BeanDefinition` 几乎把 bean 的所有信息都能收集并封装起来，可以说是很全面了。

### 1.4 【面试题】面试中如何概述BeanDefinition

以下答案仅供参考，可根据自己的理解调整回答内容：

**`BeanDefinition` 描述了 SpringFramework 中 bean 的元信息，它包含 bean 的类信息、属性、行为、依赖关系、配置信息等。`BeanDefinition` 具有层次性，并且可以在 IOC 容器初始化阶段被 `BeanDefinitionRegistryPostProcessor` 构造和注册，被 `BeanFactoryPostProcessor` 拦截修改等。**

> 这里贴出的是完整的回答，由于后置处理器的部分还没有学到，小伙伴们可以暂时把最后一句话理解为 “在 IOC 容器初始化阶段被拦截处理” 即可。

```
还是老套路，如果小伙伴想先了解并快速入门 BeanDefinition ，可以先跳过第 2 章，待基本会使用后再回过头来看 BeanDefinition 的结构。
```

## 2. BeanDefinition的结构【了解】

跟上一章一样，搞明白了 `BeanDefinition` 是什么，下面咱来看看 `BeanDefinition` 在 SpringFramework 中是如何设计的：

借助 IDEA ，可以形成如下的继承关系图：

![img](《从0开始深入学习Spring》/3e4f5db098034b6385f9645092990679~tplv-k3u1fbpfcp-zoom-1.image)

可以发现这里面涉及到的接口、抽象类和扩展居然如此之多，当然我们也不会全部都去探索，只挑其中重要的来看就好啦。

### 2.1 AttributeAccessor

看类名就知道，它是**属性的访问器**，那它一定具有可以访问对象属性的功能咯？文档注释写的非常简单，就一句话：

> Interface defining a generic contract for attaching and accessing metadata to/from arbitrary objects.
>
> 定义用于将元数据附加到任意对象，或从任意对象访问元数据的通用协定的接口。

看上去，它很像是类中定义的 getter 和 setter 方法呀，不过实际上它与 getter 、setter 方法有所区别。

#### 2.1.1 回顾元信息的概念

元信息的部分我们有说过，一个类中有什么属性、什么方法，是封装在 **`Class`** 类对象中的，通过**反射**可以获取类的属性、方法定义信息。

比方说以下一个例子：

```java
public class Person {
    private String name;
    
    public String getName() {
        return name;
    }
    
    public void setName(String name) {
        this.name = name;
    }
}
```

像这样的一个简单的类，如果用定义性质的语言描述，可以抽象成如下内容：

```
className: Person
attributes: [name]
methods: [getName, setName]
```

#### 2.1.2 AttributeAccessor的设计

翻看 `AttributeAccessor` 的接口方法，会发现它不只是简单的 getter 和 setter ，它还能移除属性信息（此处的属性就是 bean 的成员属性）。

```java
public interface AttributeAccessor {
    // 设置bean中属性的值
    void setAttribute(String name, @Nullable Object value);

    // 获取bean中指定属性的值
    Object getAttribute(String name);

    // 移除bean中的属性
    Object removeAttribute(String name);

    // 判断bean中是否存在指定的属性
    boolean hasAttribute(String name);

    // 获取bean的所有属性
    String[] attributeNames();
}
```

> 看这个设计，有木有联想到 `Map` 呢？（都有 `get` `set` `remove` `contains` `getAll` 之类的操作）

由此，我们就可以总结出第一个 `BeanDefinition` 的特征：**`BeanDefinition` 继承了 `AttributeAccessor` 接口，具有配置 bean 属性的功能。**（注意此处的措辞，配置 bean 就包含了访问、修改、移除在内的操作）

### 2.2 BeanMetadataElement

看到 **metadata** ，是不是立马就回想起元信息的概念了？其实这个类名已经把它的功能都告诉我们了：它**存放了 bean 的元信息**。这个接口只有一个方法，是获取 bean 的资源来源：

```java
public interface BeanMetadataElement {
    default Object getSource() {
        return null;
    }
}
```

资源来源，说白了，就是 bean 的文件 / url 路径。咱们前面写的所有示例，都是在本地磁盘上的 .class 文件加载进来的，所以对应的也就应该是 `FileSystemResource` （回想前面 20 章资源管理的 3.2 节），这个过会咱们到演示部分看一下就知道了。

### 2.3 AbstractBeanDefinition

到了 `BeanDefinition` 的第一个实现类了，作为 `BeanDefinition` 的抽象实现，它里面已经定义好了一些属性和功能（大部分都有了），大体包含以下内容：（只挑选部分重要属性）

```java
    // bean的全限定类名
    private volatile Object beanClass;

    // 默认的作用域为单实例
    private String scope = SCOPE_DEFAULT;

    // 默认bean都不是抽象的
    private boolean abstractFlag = false;

    // 是否延迟初始化
    private Boolean lazyInit;
    
    // 自动注入模式(默认不自动注入)
    private int autowireMode = AUTOWIRE_NO;

    // 是否参与IOC容器的自动注入(设置为false则它不会注入到其他bean，但其他bean可以注入到它本身)
    // 可以这样理解：设置为false后，你们不要来找我，但我可以去找你们
    private boolean autowireCandidate = true;

    // 同类型的首选bean
    private boolean primary = false;

    // bean的构造器参数和参数值列表
    private ConstructorArgumentValues constructorArgumentValues;

    // bean的属性和属性值集合
    private MutablePropertyValues propertyValues;

    // bean的初始化方法
    private String initMethodName;

    // bean的销毁方法
    private String destroyMethodName;

    // bean的资源来源
    private Resource resource;
```

可以发现，基本上前面提到的，这里都有了！那它干嘛还要抽象出来呢？看看文档注释怎么说：

> Base class for concrete, full-fledged BeanDefinition classes, factoring out common properties of GenericBeanDefinition, RootBeanDefinition, and ChildBeanDefinition. The autowire constants match the ones defined in the AutowireCapableBeanFactory interface.
>
> 它是 `BeanDefinition` 接口的抽象实现类，其中排除了 `GenericBeanDefinition` ，`RootBeanDefinition` 和 `ChildBeanDefinition` 的常用属性。 自动装配常量与 `AutowireCapableBeanFactory` 接口中定义的常量匹配。

哦，看样子它还不是最全的咯？针对不同的 `BeanDefinition` 落地实现，还有一些特殊的属性咯，所以还是需要抽象出一个父类才行哈。

在继续往下走之前，这里有必要插入一点东西，就是这个 `autowireMode` 属性，我们之前在 bean 的依赖注入中没有讲到，这里补充一下。

#### 2.3.1 补充 : 自动注入模式

其实这个自动注入模式，在前面第 22 章就已经有提过一嘴了（ `default-autowire` ），不过它的作用小册没有提及，这里咱讲解一下。

正常来讲，bean 中的组件依赖注入，是需要在 xml 配置文件，或者在属性 / 构造器 / setter 方法上标注注入的注解（ `@Autowired` / `@Resource` / `@Inject` 的。不过，SpringFramework 为我们提供了另外一种方式，**如果组件中的类型 / 属性名与需要注入的 bean 的类型 / name 完全一致，可以不标注依赖注入的注解，也能实现依赖注入**。

一般情况下，自动注入只会在 xml 配置文件中出现，注解配置中 `@Bean` 注解的 `autowire` 属性在 SpringFramework 5.1 之后被标记为已过时，替代方案是使用 `@Autowired` 等注解。

使用方式很简单，譬如前面的依赖注入章节中，`basic_di/inject-set.xml` 配置文件里面，cat 注入的 `Person` 完全可以不写，只需要在 `<bean>` 标签上声明自动注入模式为按名称注入即可，运行效果是完全一样的。

```xml
<bean id="cat" class="com.linkedbear.spring.basic_di.a_quickstart_set.bean.Cat" autowire="byName">
    <property name="name" value="test-cat"/>
    <!-- <property name="master" ref="person"/> 可以不写 -->
</bean>
```

自动注入的模式有 5 种选择：`AUTOWIRE_NO`（不自动注入）、`AUTOWIRE_BY_NAME`（根据 bean 的名称注入）、`AUTOWIRE_BY_TYPE`（根据 bean 的类型注入）、`AUTOWIRE_CONSTRUCTOR`（根据 bean 的构造器注入）、`AUTOWIRE_AUTODETECT`（借助内省决定如何注入，3.0 即弃用），**默认是不开启的**（所以才需要我们开发者对需要注入的属性标注注解，或者在 xml 配置文件中配置）。

（不过讲道理这个配置真的很少用，我们知道一下就可以了）

------

下面咱看几个具体的落地实现，看它们里面有什么特殊的设计。

### 2.4 GenericBeanDefinition

又看到 `Generic` 了，它代表着通用、一般的，所以这种 `BeanDefinition` 也具有一般性。`GenericBeanDefinition` 的源码实现非常简单，仅仅是比 `AbstractBeanDefinition` 多了一个 `parentName` 属性而已。

由这个设计，可以得出以下几个结论：

- `AbstractBeanDefinition` 已经完全可以构成 `BeanDefinition` 的实现了
- `GenericBeanDefinition` 就是 `AbstractBeanDefinition` 的非抽象扩展而已
- `GenericBeanDefinition` 具有层次性（可从父 `BeanDefinition` 处继承一些属性信息）

不过，相比较下面的而言，它的层次性体现的不是那么强烈，下面的这两种 `BeanDefinition` 就有非常强的层次性关系了。

### 2.5 RootBeanDefinition与ChildBeanDefinition

**root** 和 **child** ，很明显这是父子关系的意思了呀。对于 `ChildBeanDefinition` ，它的设计实现与 `GenericBeanDefinition` 如出一辙，都是集成一个 `parentName` 来作为父 `BeanDefinition` 的 “指向引用” 。不过有一点要注意， `ChildBeanDefinition` 没有默认的无参构造器，必须要传入 `parentName` 才可以，但 `GenericBeanDefinition` 则有两种不同的构造器。

`RootBeanDefinition` 有着 “根” 的概念在里面，它只能作为单体独立的 `BeanDefinition` ，或者父 `BeanDefinition` 出现（不能继承其他 `BeanDefinition` ）。它里面的设计也复杂得多，从源码的篇幅上就能看得出来（接近 500 行，而 `GenericBeanDefinition` 只有 100 行多一点）。不过这里我们不去挨个属性研究它的作用，只了解重要的组成部分就好啦。

下面是 `RootBeanDefinition` 的一些重要的成员属性：

```java
    // BeanDefinition的引用持有，存放了Bean的别名
    private BeanDefinitionHolder decoratedDefinition;

    // Bean上面的注解信息
    private AnnotatedElement qualifiedElement;

    // Bean中的泛型
    volatile ResolvableType targetType;

    // BeanDefinition对应的真实的Bean
    volatile Class<?> resolvedTargetType;

    // 是否是FactoryBean
    volatile Boolean isFactoryBean;
    // 工厂Bean方法返回的类型
    volatile ResolvableType factoryMethodReturnType;
    // 工厂Bean对应的方法引用
    volatile Method factoryMethodToIntrospect;
```

可以发现，`RootBeanDefinition` 在 `AbstractBeanDefinition` 的基础上，又扩展了这么些 Bean 的信息：

- Bean 的 id 和别名
- Bean 的注解信息
- Bean 的工厂相关信息（是否为工厂 Bean 、工厂类、工厂方法等）

而且这里面直接把一些反射相关的元素都包含进来了，可见 `BeanDefinition` 在底层可是要在反射上 “大动干戈”了。

### 2.6 AnnotatedBeanDefinition

最后，提一下这个家伙。它并不是 `BeanDefinition` 的实现类，而是一个子接口：

```java
public interface AnnotatedBeanDefinition extends BeanDefinition {
    
	AnnotationMetadata getMetadata();
    
	MethodMetadata getFactoryMethodMetadata();
}
```

由这个接口定义的方法，大概就可以猜测到，它可以把 Bean 上的注解信息提供出来。借助 IDEA ，发现它的子类里，有一个 `AnnotatedGenericBeanDefinition` ，还有一个 `ScannedGenericBeanDefinition` ，它们都是基于注解驱动下的 Bean 的注册，封装的 `BeanDefinition` 。现在我们没有必要对这些 `BeanDefinition` 深入研究，到后面 IOC 原理中，遇到咱们会解释的。

## 3. 体会BeanDefinition【熟悉】

下面，咱们使用一些简单的 Demo ，帮助小伙伴们体会 `BeanDefinition` 中的设计，以及封装的内容。本章只会了解 `BeanDefinition` 的设计部分，至于如何利用它们，咱们统一放到下一章讲解。

> 本章源码均在 `com.linkedbear.spring.definition.a_quickstart`

### 3.1 基于xml的BeanDefinition

使用 xml 配置文件的方式，每定义一个 `<bean>` 标签，就相当于构建了一个 `BeanDefinition` ，下面咱来演示基于 xml 的 `BeanDefinition` 。

#### 3.1.1 编写Bean与xml

还是拿最最简单的 `Person` 举例吧，按照依赖注入的最简单示例编写 `Person` 与 xml 配置文件就好：

```java
public class Person {
    
    private String name;
    
    public String getName() {
        return name;
    }
    
    public void setName(String name) {
        this.name = name;
    }
}
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="person" class="com.linkedbear.spring.definition.a_quickstart.bean.Person">
        <property name="name" value="zhangsan"/>
    </bean>
</beans>
```

#### 3.1.2 测试获取BeanDefinition

使用 xml 驱动 IOC 容器，并尝试获取 `BeanDefinition` ：

```java
public class BeanDefinitionQuickstartXmlApplication {
    
    public static void main(String[] args) throws Exception {
        ClassPathXmlApplicationContext ctx = new ClassPathXmlApplicationContext("definition/definition-beans.xml");
        // ？？？
    }
}
```

到了这里，要写下一步的代码，发现 `ClassPathXmlApplicationContext` 里没有 `getBeanDefinition` 方法：

![img](《从0开始深入学习Spring》/b9f51b142352461e9c8c17b6244e163c~tplv-k3u1fbpfcp-zoom-1.image)

woc ？这可咋整？难不成我还要取出所有的 `BeanDefinition` ，再筛选出 person 吗？这显然不合理吧！既然能获取多个，那就肯定能获取一个！那这里到底是出了什么问题呢？

别慌，回想前面学习的知识，`ApplicationContext` 中最终是组合了一个 `BeanFactory` 来存放 Bean 的，那 `ApplicationContext` 没有，`BeanFactory` 里有没有呢？

打开 `DefaultListableBeanFactory` ，搜索 `getBeanDefintion` ，发现真的能找到了：

![img](《从0开始深入学习Spring》/d51bb08cccdc4c62a13f3081ccc9ca5f~tplv-k3u1fbpfcp-zoom-1.image)

往上看这个方法的定义，发现它定义在 `ConfigurableListableBeanFactory` 中。虽说前面 14 章中没有介绍过 `ConfigurableListableBeanFactory` ，但它的特性应该也能猜得到吧：同时具备 **“可配置”** 和 **“可列举”** 的特性（当然人家也在此基础上又扩充了其他方法），更多的方法定义和用法，小伙伴们可以自行查看源码，小册不在此展开。

回到正题，既然 `ClassPathXmlApplicationContext` 没有这个方法，那就由它获取到 `BeanFactory` 再调用吧：

```java
public class BeanDefinitionQuickstartXmlApplication {
    
    public static void main(String[] args) throws Exception {
        ClassPathXmlApplicationContext ctx = new ClassPathXmlApplicationContext("definition/definition-beans.xml");
        BeanDefinition personBeanDefinition = ctx.getBeanFactory().getBeanDefinition("person");
        System.out.println(personBeanDefinition);
    }
}
```

运行 `main` 方法，控制台可以打印出 person 的 `BeanDefinition` 信息：

```
Generic bean: class [com.linkedbear.spring.definition.a_quickstart.bean.Person]; scope=; abstract=false; lazyInit=false; autowireMode=0; dependencyCheck=0; autowireCandidate=true; primary=false; factoryBeanName=null; factoryMethodName=null; initMethodName=null; destroyMethodName=null; defined in class path resource [definition/definition-beans.xml]
```

由这个打印信息，可以获取到一个 bean 的所有基本信息了。

值得注意的是，它是一个 **Generic bean** （打印 `personBeanDefinition` 的类型可得 `org.springframework.beans.factory.support.GenericBeanDefinition` ），这个信息比较重要哦。

### 3.2 基于@Component的BeanDefinition

给 `Person` 上打一个 `@Component` 注解，然后使用 `AnnotationConfigApplicationContext` 来驱动扫描 `Person` 类，其余的代码不变：

（注意 `AnnotationConfigApplicationContext` 可以直接调用 `getBeanDefinition` 方法哦）

```java
public class BeanDefinitionQuickstartComponentApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                "com.linkedbear.spring.definition.a_quickstart.bean");
        BeanDefinition personBeanDefinition = ctx.getBeanDefinition("person");
        System.out.println(personBeanDefinition);
        System.out.println(personBeanDefinition.getClass().getName());
    }
}
```

运行 `main` 方法，控制台打印出来的依然是一个 **Generic bean** ，但类型与上面的 xml `BeanDefinition` 不太一致：

```java
Generic bean: class [com.linkedbear.spring.definition.a_quickstart.bean.Person]; scope=singleton; abstract=false; lazyInit=null; autowireMode=0; dependencyCheck=0; autowireCandidate=true; primary=false; factoryBeanName=null; factoryMethodName=null; initMethodName=null; destroyMethodName=null; defined in file [E:\IDEA\spring-framework-projects\spring-01-ioc\target\classes\com\linkedbear\spring\definition\a_quickstart\bean\Person.class]
org.springframework.context.annotation.ScannedGenericBeanDefinition
```

可以发现，`BeanDefinition` 的打印信息里，最大的不同是加载来源：**基于 xml 解析出来的 bean ，定义来源是 xml 配置文件；基于 `@Component` 注解解析出来的 bean ，定义来源是类的 .class 文件中。**

### 3.3 基于@Bean的BeanDefinition

编写一个配置类 `BeanDefinitionQuickstartConfiguration` ，使用 `@Bean` 注册一个 Person ：

```java
@Configuration
public class BeanDefinitionQuickstartConfiguration {
    
    @Bean
    public Person person() {
        return new Person();
    }
}
```

之后，使用这个配置类驱动 IOC 容器，并直接获取 `BeanDefinition` ：

```java
public class BeanDefinitionQuickstartBeanApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                BeanDefinitionQuickstartConfiguration.class);
        BeanDefinition personBeanDefinition = ctx.getBeanDefinition("person");
        System.out.println(personBeanDefinition);
        System.out.println(personBeanDefinition.getClass().getName());
    }
}
```

运行 `main` 方法，发现控制台打印的内容与前面相比有很大的区别：

```
Root bean: class [null]; scope=; abstract=false; lazyInit=null; autowireMode=3; dependencyCheck=0; autowireCandidate=true; primary=false; factoryBeanName=beanDefinitionQuickstartConfiguration; factoryMethodName=person; initMethodName=null; destroyMethodName=(inferred); defined in com.linkedbear.spring.definition.a_quickstart.config.BeanDefinitionQuickstartConfiguration
org.springframework.context.annotation.ConfigurationClassBeanDefinitionReader$ConfigurationClassBeanDefinition
```

具体区别可以发现有这么几个：

- Bean 的类型是 Root bean （ `ConfigurationClassBeanDefinition` 继承自 `RootBeanDefinition` ）
- Bean 的 className 不见了
- 自动注入模式为 `AUTOWIRE_CONSTRUCTOR` （构造器自动注入）
- 有 factoryBean 了：person 由 `beanDefinitionQuickstartConfiguration` 的 `person` 方法创建

这一切的一切都是怎么搞得呢？下面咱解释这种现象与设计。

### 3.4 【原理】BeanDefinition是如何生成的（简易理解）

这个问题说实话如果想完全彻底的解释清楚，有点费劲，我们放到后面的 IOC 原理篇，`BeanDefinition` 的解析阶段解释，这里只是让小伙伴们有一个认识和印象即可。

1. 通过 xml 加载的 `BeanDefinition` ，它的读取工具是 `XmlBeanDefinitionReader` ，它会解析 xml 配置文件，最终来到 `DefaultBeanDefinitionDocumentReader` 的 `doRegisterBeanDefinitions` 方法，根据 xml 配置文件中的 bean 定义构造 `BeanDefinition` ，最底层创建 `BeanDefinition` 的位置在 `org.springframework.beans.factory.support.BeanDefinitionReaderUtils#createBeanDefinition` 。
2. 通过模式注解 + 组件扫描的方式构造的 `BeanDefinition` ，它的扫描工具是 `ClassPathBeanDefinitionScanner` ，它会扫描指定包路径下包含特定模式注解的类，核心工作方法是 `doScan` 方法，它会调用到父类 `ClassPathScanningCandidateComponentProvider` 的 `findCandidateComponents` 方法，创建 `ScannedGenericBeanDefinition` 并返回。
3. 通过配置类 + `@Bean` 注解的方式构造的 `BeanDefinition` 最复杂，它涉及到配置类的解析。配置类的解析要追踪到 `ConfigurationClassPostProcessor` 的 `processConfigBeanDefinitions` 方法，它会处理配置类，并交给 `ConfigurationClassParser` 来解析配置类，取出所有标注了 `@Bean` 的方法。随后，这些方法又被 `ConfigurationClassBeanDefinitionReader` 解析，最终在底层创建 `ConfigurationClassBeanDefinition` 并返回。

再啰嗦一边哈，小伙伴只需要对这些内容有一个最简单的了解就好了，至于里面的原理是什么样子，我们现在不要关心！不要关心！不要关心！

好了，先对 `BeanDefinition` 了解这么多就好，主要是对 `BeanDefinition` 有一个总体的认识，能认识到这里面的设计，就已经 OK 了。

## 小结与思考

1. 如何理解 `BeanDefinition` ？
2. `BeanDefinition` 中主要包含哪些信息？
3. `BeanDefinition` 有哪些类型？分别都有什么特征？

【了解了 `BeanDefinition` 的设计，下一章我们就要去研究与 `BeanDefinition` 配合的一个重要的 API 了：**`BeanDefinitionRegistry`** ，以及 `BeanDefinition` 的另一个特征：**合并**】

# 25. IOC高级-BeanDefinition与BeanDefinitionRegistry

上一章，咱们对 `BeanDefinition` 的整体设计，以及几种常见的类型有了一个认识。不过 `BeanDefinition` 不是凭空出现的，是要配合一个 API 才能完成注册的，IOC 容器中也才能有的，它就是前面留下的一个很重要的坑：**`BeanDefinitionRegistry`**。

## 1. BeanDefinitionRegistry概述【理解】

还是那个老套路，先对 `BeanDefinitionRegistry` 有个整体的认识。

【以下内容可能比较啰里八嗦，想直接拿来面试的小伙伴请直接移步 1.5 节】

由于官方文档中并没有提及 `BeanDefinitionRegistry` 的设计，故我们只尝试从 javadoc 中获取一些信息。

> Interface for registries that hold bean definitions, for example RootBeanDefinition and ChildBeanDefinition instances. Typically implemented by BeanFactories that internally work with the AbstractBeanDefinition hierarchy. This is the only interface in Spring's bean factory packages that encapsulates registration of bean definitions. The standard BeanFactory interfaces only cover access to a fully configured factory instance. Spring's bean definition readers expect to work on an implementation of this interface. Known implementors within the Spring core are DefaultListableBeanFactory and GenericApplicationContext.
>
> 包含 bean 定义的注册表的接口（例如 `RootBeanDefinition` 和 `ChildBeanDefinition` 实例）。通常由内部与 `AbstractBeanDefinition` 层次结构一起工作的 `BeanFactorty` 实现。 这是 SpringFramework 的 bean 工厂包中唯一封装了 bean 的定义注册的接口。标准 `BeanFactory` 接口仅涵盖对完全配置的工厂实例的访问。 `BeanDefinition` 的解析器希望可以使用此接口的实现类来支撑逻辑处理。SpringFramework 中的已知实现者是 `DefaultListableBeanFactory` 和 `GenericApplicationContext` 。

其实 javadoc 已经把 `BeanDefinitionRegistry` 的设计都讲得七七八八了，小册重新解读一下，帮助小伙伴们理解。

### 1.1 BeanDefinitionRegistry中存放了所有BeanDefinition

Registry 有注册表的意思，联想下 Windows 的注册表，它存放了 Windows 系统中的应用和设置信息。如果按照这个设计理解，那 `BeanDefinitionRegistry` 中存放的就应该是 `BeanDefinition` 的设置信息。其实 SpringFramework 中的底层，对于 `BeanDefinition` 的注册表的设计，就是一个 **`Map`** ：

```java
// 源自DefaultListableBeanFactory
private final Map<String, BeanDefinition> beanDefinitionMap = new ConcurrentHashMap<>(256);
```

### 1.2 BeanDefinitionRegistry中维护了BeanDefinition

另外，Registry 还有注册器的意思，既然 Map 有增删改查，那作为 `BeanDefinition` 的注册器，自然也会有 `BeanDefinition` 的注册功能咯。`BeanDefinitionRegistry` 中有 3 个方法，刚好对应了 `BeanDefinition` 的增、删、查：

```java
void registerBeanDefinition(String beanName, BeanDefinition beanDefinition)
            throws BeanDefinitionStoreException;

void removeBeanDefinition(String beanName) throws NoSuchBeanDefinitionException;

BeanDefinition getBeanDefinition(String beanName) throws NoSuchBeanDefinitionException;
```

### 1.3 BeanDefinitionRegistry支撑其它组件运行

javadoc 的最后一段，说起来有点有趣：

> Spring's bean definition readers expect to work on an implementation of this interface.
>
> `BeanDefinition` 的加载器希望可以使用此接口的实现类来支撑逻辑处理。

这句话似乎不是那么好理解，小册尝试用一个例子来引导小伙伴理解 `BeanDefinitionRegistry` 的支撑作用。

javadoc 中的 Reader 可以参照上一章提到了 `XmlBeanDefinitionReader` ，它是用来读取和加载 xml 配置文件的组件。加载 xml 配置文件的目的就是读取里面的配置，和定义好要注册到 IOC 容器的 bean 。`XmlBeanDefinitionReader` 要在加载完 xml 配置文件后，将配置文件的流对象也好，文档对象也好，交给解析器来解析 xml 文件，解析器拿到 xml 文件后要解析其中定义的 bean ，并且封装为 `BeanDefinition` 注册到 IOC 容器，这个时候就需要 `BeanDefinitionRegistry` 了。所以在这个过程中，**`BeanDefinitionRegistry` 会支撑 `XmlBeanDefinitionReader` 完成它的工作**。

当然，`BeanDefinitionRegistry` 不止支撑了这一个哈，还记得之前小册 17 章，学习模块装配时用到的 `ImportBeanDefinitionRegistrar` 吗？它的 `registerBeanDefinitions` 方法是不是也传入了一个 `BeanDefinitionRegistry` 呀？所以说这个 `BeanDefinitionRegistry` 用到的位置还是不少的，小伙伴们要予以重视哦。

### 1.4 BeanDefinitionRegistry的主要实现是DefaultListableBeanFactory

注意这个地方我没说是唯一实现哦，是因为 `BeanDefinitionRegistry` 除了有最最常用的 `DefaultListableBeanFactory` 之外，还有一个不常用的 `SimpleBeanDefinitionRegistry` ，但这个 `SimpleBeanDefinitionRegistry` 基本不会去提它，是因为这个设计连内部的 IOC 容器都没有，仅仅是一个 `BeanDefinitionRegistry` 的表面实现而已，所以我们当然不会用它咯。

可能有的小伙伴借助 IDE 发现很多 `ApplicationContext` 也实现了它，但我想请这部分小伙伴回想一下，`ApplicationContext` 本身管理 Bean 吗？不吧，`ApplicationContext` 不都是内部组合了一个 `DefaultListableBeanFactory` 来实现的嘛，所以我们说，唯一真正落地实现的是 `DefaultListableBeanFactory` 这话是正确合理的。

### 1.5 【面试题】面试中如何概述BeanDefinitionRegistry

以下答案仅供参考，可根据自己的理解调整回答内容：

**`BeanDefinitionRegistry` 是维护 `BeanDefinition` 的注册中心，它内部存放了 IOC 容器中 bean 的定义信息，同时 `BeanDefinitionRegistry` 也是支撑其它组件和动态注册 Bean 的重要组件。在 SpringFramework 中，`BeanDefinitionRegistry` 的实现是 `DefaultListableBeanFactory` 。**

## 2. BeanDefinitionRegistry维护BeanDefinition的使用【熟悉】

对于 `BeanDefinitionRegistry` 内部的设计，倒是没什么好说的，主要还是研究它如何去维护 `BeanDefinition` 。

> 本小节源码位置：`com.linkedbear.spring.definition.b_registry`

### 2.1 BeanDefinition的注册

对于 `BeanDefinition` 的注册，目前我们接触到的方式是在 17 章模块装配中使用的 `ImportBeanDefinitionRegistrar` ：

```java
public class WaiterRegistrar implements ImportBeanDefinitionRegistrar {
    
    @Override
    public void registerBeanDefinitions(AnnotationMetadata metadata, BeanDefinitionRegistry registry) {
        registry.registerBeanDefinition("waiter", new RootBeanDefinition(Waiter.class));
    }
}
```

之前的这个例子中是直接 **new** 了一个 `RootBeanDefinition` ，其实 `BeanDefinition` 的构造可以借助**建造器**生成，下面我们再演示一个例子。

#### 2.1.1 声明Person类

像往常一样，搞一个比较简单的 `Person` 就好啦，记得声明几个属性和 `toString` 方法：

```java
public class Person {
    
    private String name;
    
    public String getName() {
        return name;
    }
    
    public void setName(String name) {
        this.name = name;
    }
    
    @Override
    public String toString() {
        return "Person{" + "name='" + name + '\'' + '}';
    }
}
```

#### 2.1.2 编写ImportBeanDefinitionRegistrar的实现类

编写一个 `PersonRegister` ，让它实现 `ImportBeanDefinitionRegistrar` ，这样就可以拿到 `BeanDefinitionRegistry` 了：

```java
public class PersonRegister implements ImportBeanDefinitionRegistrar {
    
    @Override
    public void registerBeanDefinitions(AnnotationMetadata importingClassMetadata, BeanDefinitionRegistry registry) {
        registry.registerBeanDefinition("person",
                BeanDefinitionBuilder.genericBeanDefinition(Person.class).addPropertyValue("name", "zhangsan")
                        .getBeanDefinition());
    }
}
```

注意这里面的写法，使用 `BeanDefinitionBuilder` ，是可以创建 `GenericBeanDefinition` 、`RootBeanDefinition` 和 `ChildBeanDefinition` 三种类型的，此处小册使用 `GenericBeanDefinition` ，后续直接向 `BeanDefinition` 中添加 bean 中属性的值就好，整个构造过程一气呵成，非常的简单。

#### 2.1.3 编写配置类导入PersonRegister

编写一个配置类，把上面刚写好的 `PersonRegister` 导入进去（这一步不要忘了哦）：

```java
@Configuration
@Import(PersonRegister.class)
public class BeanDefinitionRegistryConfiguration {
    
}
```

#### 2.1.4 测试获取Person

万事俱备，下面编写测试启动类，使用 `BeanDefinitionRegistryConfiguration` 驱动 IOC 容器，并从容器中取出 `Person` 并打印：

```java
public class BeanDefinitionRegistryApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                BeanDefinitionRegistryConfiguration.class);
        Person person = ctx.getBean(Person.class);
        System.out.println(person);
    }
}
```

运行 `main` 方法，控制台中打印了 `Person` 的 name 属性是有值的，说明 SpringFramework 已经按照我们预先定义好的 `BeanDefinition` ，注册到 IOC 容器，并且生成了对应的 Bean 。

```
Person{name='zhangsan'}
```

### 2.2 BeanDefinition的移除

`BeanDefinitionRegistry` 除了能给 IOC 容器中添加 `BeanDefinition` ，还可以移除掉一些特定的 `BeanDefinition` 。这种操作可以在 Bean 的实例化之前去除，以阻止 IOC 容器创建。

要演示 `BeanDefinition` 的移除，需要一个现阶段没见过的 API ，咱们先学着用一下，到后面我们会系统的学习它的用法。

> 本小节源码位置：`com.linkedbear.spring.definition.c_removedefinition`

#### 2.2.1 声明Person

这次声明的 `Person` 类要加一个特殊的属性：**sex** ，性别，它在后面会起到判断作用。

声明好 getter 、setter 和 `toString` 方法即可。

```java
public class Person {
    
    private String name;
    private String sex;
    
    // getter 、setter 、 toString
}
```

#### 2.2.2 声明配置类

接下来要注册两个 `Person` ，分别注册一男一女。

由上一章 `BeanDefinition` 的注册方式与实现类型，可知如果此处使用注解配置类的方式注册 Bean ( `@Bean` ) ，生成的 `BeanDefinition` 将无法取到 `beanClassName` （也无法取到 PropertyValues ），故此处选用 xml 方式注册 Bean 。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd http://www.springframework.org/schema/context https://www.springframework.org/schema/context/spring-context.xsd">

    <bean id="aqiang" class="com.linkedbear.spring.definition.c_removedefinition.bean.Person">
        <property name="name" value="阿强"/>
        <property name="sex" value="male"/>
    </bean>

    <bean id="azhen" class="com.linkedbear.spring.definition.c_removedefinition.bean.Person">
        <property name="name" value="阿珍"/>
        <property name="sex" value="female"/>
    </bean>

    <!-- 注意此处要开启包扫描 -->
    <context:component-scan base-package="com.linkedbear.spring.definition.c_removedefinition.config"/>
</beans>
```

#### 2.2.3 编写剔除BeanDefinition的后置处理器

这里涉及到后置处理器的概念了，没见过没关系，不会搞没关系，先照着葫芦画瓢，后面马上就学到了。

要剔除 `BeanDefinition` ，需要实现 `BeanFactoryPostProcessor` 接口，并重写 `postProcessBeanFactory` 方法：（记得标注 `@Component` 注解哦）

```java
@Component
public class RemoveBeanDefinitionPostProcessor implements BeanFactoryPostProcessor {
    
    @Override
    public void postProcessBeanFactory(ConfigurableListableBeanFactory beanFactory) throws BeansException {
    
    }
}
```

注意方法的入参，它是一个 `ConfigurableListableBeanFactory` ，不用想，它的唯一实现一定是 `DefaultListableBeanFactory` 。又从前面了解到 `DefaultListableBeanFactory` 实现了 `BeanDefinitionRegistry` 接口，所以这里我们就可以直接将 `beanFactory` 强转为 `BeanDefinitionRegistry` 类型。

于是，我们就可以编写如下的剔除逻辑：**移除 IOC 容器中所有性别为 male 的 Person** 。

```java
@Override
public void postProcessBeanFactory(ConfigurableListableBeanFactory beanFactory) throws BeansException {
    BeanDefinitionRegistry registry = (BeanDefinitionRegistry) beanFactory;
    // 获取IOC容器中的所有BeanDefinition
    for (String beanDefinitionName : beanFactory.getBeanDefinitionNames()) {
        // 判断BeanDefinition对应的Bean是否为Person类型
        BeanDefinition beanDefinition = beanFactory.getBeanDefinition(beanDefinitionName);
        if (Person.class.getName().equals(beanDefinition.getBeanClassName())) {
            // 判断Person的性别是否为male
            // 使用xml配置文件对bean进行属性注入，最终取到的类型为TypedStringValue，这一点不需要记住
            TypedStringValue sex = (TypedStringValue) beanDefinition.getPropertyValues().get("sex");
            if ("male".equals(sex.getValue())) {
                // 移除BeanDefinition
                registry.removeBeanDefinition(beanDefinitionName);
            }
        }
    }
}
```

#### 2.2.4 测试获取“阿强”

这一次我们又要用 `ClassPathXmlApplicationContext` 来加载配置文件驱动 IOC 容器了，写法很简单，直接从 IOC 容器中取 “aqiang” 就好：

```java
public class RemoveBeanDefinitionApplication {
    
    public static void main(String[] args) throws Exception {
        ClassPathXmlApplicationContext ctx = new ClassPathXmlApplicationContext("definition/remove-definitions.xml");
        Person aqiang = (Person) ctx.getBean("aqiang");
        System.out.println(aqiang);
    }
}
```

运行 `main` 方法，控制台打印 `NoSuchBeanDefinitionException` 的异常，证明 “aqiang” 对应的 `BeanDefinition` 已经被移除了，无法创建 `Person` 实例。

好了，到这里，对 `BeanDefinitionRegistry` 有一个比较清晰的认识就好，具体操作不需要太深入了解，会用就够啦。

## 3. BeanDefinition的合并【了解】

了解完 `BeanDefinitionRegistry` ，回过头来再学习一个 `BeanDefinition` 的特性：**合并**。

关于合并这个概念，可能有些小伙伴没有概念，小册先来解释一下合并的意思。

### 3.1 如何理解BeanDefinition的合并

上一章我们知道，之前在 xml 配置文件中定义的那些 bean ，最终都转换为一个个的 `GenericBeanDefinition` ，它们都是相互独立的。比如这样：

```xml
<bean class="com.linkedbear.spring.basic_dl.b_bytype.bean.Person"></bean>
<bean class="com.linkedbear.spring.basic_dl.b_bytype.dao.impl.DemoDaoImpl"/>
```

但其实，bean 也是存在**父子关系**的。与 Class 的抽象、继承一样，`<bean>` 标签中有 **abstract** 属性，有 **parent** 属性，由此就可以形成父子关系的 `BeanDefinition` 了。

下面小册演示一个实例，讲解 `BeanDefinition` 的合并。

### 3.2 BeanDefinition合并的体现

先构建一个比较简单的场景吧：所有的**动物**都归**人**养，动物分很多种（猫啊 狗啊 猪啊 巴拉巴拉）。

下面我们基于这个场景来编码演绎。

#### 3.2.1 声明实体类

对于这几个实体类，前面已经写过很多次了，这里快速编写出来就 OK ：

```java
public class Person {
    
}
public abstract class Animal {

    private Person person;
    
    public Person getPerson() {
        return person;
    }
    
    public void setPerson(Person person) {
        this.person = person;
    }
}
```

`Cat` 要继承自 `Animal` ，并且为了方便打印出 `person` ，这里就不直接使用 IDEA 的 `toString` 方法生成了，而是在此基础上改造一下：

```java
public class Cat extends Animal {
    
    private String name;
    
    public String getName() {
        return name;
    }
    
    public void setName(String name) {
        this.name = name;
    }
    
    @Override
    public String toString() {
        return "Cat{" + "name=" + name + ", person='" + getPerson() + '\'' + "}";
    }
}
```

#### 3.2.2 编写xml配置文件

要体现 `BeanDefinition` 的合并，要使用配置文件的形式，前面也说过了。那下面咱就来造一个配置文件，先把 `Person` 注册上去。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="person" class="com.linkedbear.spring.definition.d_merge.bean.Person"/>
</beans>
```

接下来要注册 `Animal` 和 `Cat` 了。按照之前的写法，这里只需要注册 `Cat` 就可以了，像这样写就 OK ：

```xml
<bean class="com.linkedbear.spring.definition.d_merge.bean.Cat" parent="abstract-animal">
    <property name="person" ref="person"/>
    <property name="name" value="咪咪"/>
</bean>
```

但试想，如果要创建的猫猫狗狗猪猪太多的话，每个 bean 都要注入 property ，这样可不是好办法。由此，就可以使用 `BeanDefinition` 合并的特性来优化这个问题。

我们直接在 xml 中注册一个 `Animal` ：

```xml
<bean class="com.linkedbear.spring.definition.d_merge.bean.Animal"></bean>
```

但这样写完之后，IDEA 会报红，给出这样的提示：

![img](《从0开始深入学习Spring》/1811045a723f455baf9e49a8701fb0b1~tplv-k3u1fbpfcp-zoom-1.image)

很明显嘛，抽象类怎么能靠一个 `<bean>` 标签构造出对象呢？所以，`<bean>` 标签里有一个属性，就是标注这个 bean 是否是抽象类：

![img](《从0开始深入学习Spring》/8296e2db237648098d16e8411c6230a2~tplv-k3u1fbpfcp-zoom-1.image)

如此，咱就可以把这个 `Animal` 声明好了，由于是 **abstract** 类型的 bean ，那也就可以搞定注入的事了：

```xml
<bean id="abstract-animal" class="com.linkedbear.spring.definition.d_merge.bean.Animal" abstract="true">
    <property name="person" ref="person"/>
</bean>
```

接下来要声明 `Cat` 了，有 **abstract** 就有 **parent** ，想必不用我多说小伙伴们也能猜到如何写了：

```xml
<bean id="cat" class="com.linkedbear.spring.definition.d_merge.bean.Cat" parent="abstract-animal">
    <property name="name" value="咪咪"/>
</bean>
```

这里就不再需要声明 `person` 属性的注入了，因为继承了 `abstract-animal` ，相应的依赖注入也就都可以继承过来。

这样 xml 配置文件就写完了。

#### 3.2.3 测试运行

编写启动类，使用 xml 配置文件驱动 IOC 容器，并从 `BeanFactory` 中取出 cat 的 `BeanDefinition` ：

```java
public class MergeBeanDefinitionApplication {
    
    public static void main(String[] args) throws Exception {
        ClassPathXmlApplicationContext ctx = new ClassPathXmlApplicationContext("definition/definition-merge.xml");
        Cat cat = (Cat) ctx.getBean("cat");
        System.out.println(cat);
        
        BeanDefinition catDefinition = ctx.getBeanFactory().getBeanDefinition("cat");
        System.out.println(catDefinition);
    }
}
```

运行 `main` 方法，发现 `Cat` 里确实注入了 `person` 对象，可是获取出来的 `BeanDefinition` ，除了有了一个 `parentName` 之外，跟普通的 bean 没有任何不一样的地方。

```
Cat{name=咪咪, person='com.linkedbear.spring.definition.d_merge.bean.Person@31dc339b'}
Generic bean with parent 'abstract-animal': class [com.linkedbear.spring.definition.d_merge.bean.Cat]; scope=;   ......(太长省略)
```

可能会有小伙伴产生疑惑了：这就算是 `BeanDefinition` 的合并了吗？哪里有体现呢？要么我 Debug 看下结构？

以 Debug 的形式重新运行 `main` 方法，发现获取到的 `catDefinition` 里并没有把 `person` 的依赖带进来：

![img](《从0开始深入学习Spring》/173fbedcb5674458a6f6a21a33ff8357~tplv-k3u1fbpfcp-zoom-1.image)

哦，合着并没有合并 `BeanDefinition` 呗？那这一套花里胡哨的搞蛇皮呢？

等一下，先冷静冷静，会不会是我们的方法不对呢？既然是 `BeanDefinition` 的合并，那不加个 **merge** 的关键字，好意思说是合并吗？

试着重新调一下方法，发现 `ConfigurableListableBeanFactory` 里竟然也有一个 `getMergedBeanDefinition` 方法！它来自 `ConfigurableBeanFactory` ，它就是用来**将本身定义的 bean 定义信息，与继承的 bean 定义信息进行合并后返回**的。

#### 3.2.4 换用getMergedBeanDefinition

修改下测试运行，将 `getBeanDefinition` 换为 `getMergedBeanDefinition` ，重新运行 `main` 方法，发现控制台打印的 `BeanDefinition` 的类型变为了 `RootBeanDefinition` ，而且也没有 `parentName` 相关的信息了：

```java
Root bean: class [com.linkedbear.spring.definition.d_merge.bean.Cat]; scope=singleton; abstract=false; lazyInit=false; autowireMode=0; dependencyCheck=0; autowireCandidate=true; primary=false; factoryBeanName=null; factoryMethodName=null; initMethodName=null; destroyMethodName=null; defined in class path resource [definition/definition-merge.xml]
```

以 Debug 方式运行，此时的 `propertyvalues` 中已经有两个属性键值对了：

![img](《从0开始深入学习Spring》/be105a8a0d7f4c7c906783887d990d90~tplv-k3u1fbpfcp-zoom-1.image)

到这里，`BeanDefinition` 的合并就算了解的差不多了。至于里面的原理，我们会到后面的 IOC 原理部分解析，这里就先不搞那么难的内容了。

## 4. 设计BeanDefinition的意义【理解】

看到这里，小伙伴们可能会有一个大大的问号，也有可能是大大的感叹号，那就是：**SpringFramework 为什么会设计 `BeanDefinition` 呢？直接注册 Bean 不好吗？**这个问题的回答，在不同的阶段学习中，这个答案可能会不太一样。在刚学习完 `BeanDefinition` 的设计后，小册想先让小伙伴们理解这样的一个设计：**定义信息 → 实例**。

其实这个设计，在前面的元定义章节就已经反复解释过了，这里小册想再解释一下，因为它真的太太太重要了！

像我们平时编写 **Class** 再 **new** 出对象一样，**SpringFramework 面对一个应用程序，它也需要对其中的 bean 进行定义抽取，只有抽取成可以统一类型 / 格式的模型，才能在后续的 bean 对象管理时，进行统一管理，也或者是对特定的 bean 进行特殊化的处理。而这一切的一切，最终落地到统一类型上，就是 `BeanDefinition` 这个抽象化的模型。**

这段解释中可能现在小伙伴们只能体会到部分的解释（如 SpringFramework 对 Bean 的作用域控制），没有关系不要慌，接下来的两章，学习完后置处理器，到时候小册再拿出这段话来，或许小伙伴们就更能理解这段话想表达的意思了。

## 小结与练习

1. 什么是 `BeanDefinitionRegistry` ？
2. `BeanDefinitionRegistry` 的作用是什么？它的最终形态是什么？
3. `BeanDefinition` 与 `BeanDefinitionRegistry` 的关系是什么？
4. 尝试动手实现借助 `BeanDefinitionRegistry` 注册和修改、移除 `BeanDefinition` ，加深印象。

【很重要的 `BeanDefinition` 部分先告一段落，下面又到了一个非常重要的高级知识点了：**后置处理器**】

# 26. IOC高级-后置处理器入门与使用

其实关于后置处理器的这部分，早在 Bean 的生命周期部分就可以讲解了，为什么非要放在这里呢？因为后置处理器这部分的难度实在是有点高，而且属于比较高阶的用法，所以就放在 IOC 高级部分讲解了。另外，后置处理器可以影响的并不只是 bean ，`BeanFactory` 、`BeanDefinition` 也都可以影响，需要这些前置知识都搞定，小伙伴们再学后置处理器的时候才不至于磕绊。

好了，进入正题吧。

## 1. 后置处理器概述【理解】

还是老套路，先对后置处理器有一个整体的认识。

【以下内容可能比较啰里八嗦，想直接拿来面试的小伙伴请直接移步 1.4 节】

### 1.1 官方文档

官方文档的 `1.8 Container Extension Points (容器扩展点)` 章节中，专门拿出了一个小节讲解 `BeanPostProcessor` 的使用。由于这段内容比较长，小册将其拆解开解释。

[docs.spring.io/spring/docs…](https://docs.spring.io/spring/docs/5.2.x/spring-framework-reference/core.html#beans-factory-extension-bpp)

#### 1.1.1 BeanPostProcessor是一个容器扩展点

> The BeanPostProcessor interface defines callback methods that you can implement to provide your own (or override the container’s default) instantiation logic, dependency resolution logic, and so forth. If you want to implement some custom logic after the Spring container finishes instantiating, configuring, and initializing a bean, you can plug in one or more custom BeanPostProcessor implementations.
>
> `BeanPostProcessor` 接口定义了回调方法，您可以实现这些回调方法以提供自己的（或覆盖容器默认的）实例化逻辑、依赖处理 / 解析逻辑等。如果您想在 IOC 容器完成实例化、配置、初始化 bean 之后实现一些自定义逻辑，则可以注册一个或多个自定义的 `BeanPostProcessor` 实现。

这段话已经解释的非常清楚了，`BeanPostProcessor` 是一个回调机制的扩展点，它的核心工作点是在 **bean 的初始化前后**做一些额外的处理（预初始化 bean 的属性值、注入特定的依赖，甚至扩展生成代理对象等）。

#### 1.1.2 BeanPostProcessor的执行可以指定先后顺序

> You can configure multiple BeanPostProcessor instances, and you can control the order in which these BeanPostProcessor instances run by setting the order property. You can set this property only if the BeanPostProcessor implements the Ordered interface. If you write your own BeanPostProcessor, you should consider implementing the Ordered interface, too.
>
> 您可以配置多个 `BeanPostProcessor` 实例，并且可以通过设置 order 属性来控制这些 `BeanPostProcessor` 实例的运行顺序。仅当 `BeanPostProcessor` 实现 `Ordered` 接口时，才可以设置此属性。如果您编写自己的 `BeanPostProcessor` ，则也应该考虑实现 `Ordered` 接口。

与监听器一样，后置处理器也可以指定多个，并且可以通过实现 `Ordered` 接口，指定后置处理器工作的先后顺序。这看上去似乎不是特别有必要，小册举一个比较简单的例子：

如果有两个后置处理器，分别处理 IOC 容器中的 Service 层实现类，一个负责注入 Dao 层的接口，一个负责统一控制事务，那这个时候就需要先让注入 Dao 接口的后置处理器先工作，让控制事务的后置处理器往后稍稍。

> 多提一嘴，控制事务的底层原理是使用了 **AOP** ，生成了**代理对象**，后面 AOP 篇和 Dao 编程篇会讲解事务控制及其原理。

#### 1.1.3 BeanPostProcessor在IOC容器间互不影响

> BeanPostProcessor instances operate on bean (or object) instances. That is, the Spring IoC container instantiates a bean instance and then BeanPostProcessor instances do their work. BeanPostProcessor instances are scoped per-container. This is relevant only if you use container hierarchies. If you define a BeanPostProcessor in one container, it post-processes only the beans in that container. In other words, beans that are defined in one container are not post-processed by a BeanPostProcessor defined in another container, even if both containers are part of the same hierarchy. To change the actual bean definition (that is, the blueprint that defines the bean), you instead need to use a BeanFactoryPostProcessor, as described in Customizing Configuration Metadata with a BeanFactoryPostProcessor.
>
> `BeanPostProcessor` 在 bean（或对象）实例上运行。也就是说，Spring 的 IOC 容器会实例化出一个 bean 的对象实例，然后 `BeanPostProcessor` 完成它的工作。 `BeanPostProcessor` 是按容器划分作用域的（仅在使用容器层次结构时，这种设定才有意义）。如果在一个容器中定义 `BeanPostProcessor` ，它将仅对该容器中的 bean 进行后置处理。换句话说，一个容器中定义的 bean 不会由另一个容器中定义的 `BeanPostProcessor` 进行后处理，即使这两个容器是同一层次结构的一部分。 要更改实际的 `BeanDefinition` 信息，您需要使用 `BeanFactoryPostProcessor` ，如使用 `BeanFactoryPostProcessor` 自定义配置元数据中的信息。

从这一长串文档中，提取出几个关键信息：**`BeanPostProcessor` 作用于 bean 对象的创建后**；**不同 IOC 容器中的 `BeanPostProcessor` 不会互相起作用**。这些特性，在下面的演示中都会有体现，小伙伴们无需着急。

另外，最后一句话它提到了，如果要处理 `BeanDefinition` ，要使用 `BeanFactoryPostProcessor` ，这也是上一章我们用的那个陌生的 API 了，它的使用，小册放到下一章来讲解，本章只讲解 `BeanPostProcessor` 的使用。

### 1.2 javadoc

翻看 `BeanPostProcessor` 的 javadoc ，发现它的篇幅也很长，小册只摘取总体描述的部分来阅读。

> Factory hook that allows for custom modification of new bean instances — for example, checking for marker interfaces or wrapping beans with proxies. Typically, post-processors that populate beans via marker interfaces or the like will implement postProcessBeforeInitialization, while post-processors that wrap beans with proxies will normally implement postProcessAfterInitialization.
>
> `BeanPostProcessor` 是一种工厂的回调钩子，它允许对 bean 实例进行自定义修改（例如检查 bean 实现的标记接口，或使用代理包装 bean ）。 通常，通过标记接口等填充 bean 的后置处理器将实现 `postProcessBeforeInitialization` 方法，而使用代理包装 bean 的后置处理器通常将实现 `postProcessAfterInitialization` 方法。

javadoc 更倾向于教我们怎么用，它也说了，`BeanPostProcessor` 提供了两个回调时机：**bean 的初始化之前**和 **bean 的初始化之后**，它们分别适合做**填充**和**代理**的工作。下面咱结合 `BeanPostProcessor` 的接口设计来看看。

### 1.3 BeanPostProcessor的设计

`BeanPostProcessor` 是一个接口，它只定义了两个方法，也就是上面 javadoc 中提到的两个方法：

```java
public interface BeanPostProcessor {
    
    default Object postProcessBeforeInitialization(Object bean, String beanName) throws BeansException {
        return bean;
    }

    default Object postProcessAfterInitialization(Object bean, String beanName) throws BeansException {
        return bean;
    }
}
```

> SpringFramework 5.x 之前由于最低支持 Java6 ，此处并没有默认的方法实现。

这两个方法的文档注释也写的非常完善：`postProcessBeforeInitialization` 方法会在任何 bean 的初始化回调（例如 `InitializingBean` 的 `afterPropertiesSet` 或自定义 `init-method` ）之前执行，而 `postProcessAfterInitialization` 方法会在任何 bean 的初始化回调（例如 `InitializingBean` 的 `afterPropertiesSet` 或自定义 `init-method` ）之后。

此外，对于 `postProcessAfterInitialization` 方法，还可以对那些 `FactoryBean` 创建出来的真实对象进行后置处理，这个我们下面也会有演示。

最后，还是老样子，咱试着总结一下面试中如何概述 `BeanPostProcessor` 。

### 1.4 【面试题】面试中如何概述BeanPostProcessor

以下答案仅供参考，可根据自己的理解调整回答内容：

**`BeanPostProcessor` 是一个容器的扩展点，它可以在 bean 的生命周期过程中，初始化阶段前后添加自定义处理逻辑，并且不同 IOC 容器间的 `BeanPostProcessor` 不会相互干预。**

## 2. BeanPostProcessor的使用【掌握】

下面，咱们就来搞几个例子，体会一下 `BeanPostProcessor` 的作用。

### 2.1 快速体会使用

先从最简单的开始，我们不编写任何逻辑，只是注册进去，看看能不能拦截到 bean 的初始化就好。

> 本小节源码位置：`com.linkedbear.spring.postprocessor.a_quickstart`

#### 2.1.1 声明几个bean

最初的案例不需要太花里胡哨的 bean ，就简单整两个吧：

```java
@Component
public class Cat {
    
}

@Component
public class Dog {
    
}
```

#### 2.1.2 编写后置处理器

声明一个 `AnimalBeanPostProcessor` ，让它实现 `BeanPostProcessor` ，然后啥也不干，只打印语句就好：

```java
@Component
public class AnimalBeanPostProcessor implements BeanPostProcessor {
    
    @Override
    public Object postProcessBeforeInitialization(Object bean, String beanName) throws BeansException {
        System.out.println("拦截到Bean的初始化之前：" + beanName);
        return bean;
    }
    
    @Override
    public Object postProcessAfterInitialization(Object bean, String beanName) throws BeansException {
        System.out.println("拦截到Bean的初始化之后：" + beanName);
        return bean;
    }
}
```

这里注意一个非常重要的设计：它的入参有一个 **bean** ，类型是 **`Object`** ，返回值也是 **`Object`** ，似乎有暗示返回的 bean 可以任意替换的意思了，是不是这样呢，我们过会可以试一试。

#### 2.1.3 测试运行

使用注解驱动 IOC 容器，直接扫描包即可。由于我们只是测试后置处理器的功能，所以在初始化 IOC 容器后不需要做任何操作，那就顺手关掉吧：

```java
public class BeanPostProcessorQuickstartApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                "com.linkedbear.spring.postprocessor.a_quickstart");
        ctx.close();
    }
}
```

运行 `main` 方法，控制台的打印也说明，cat 和 dog 的初始化被 `AnimalBeanPostProcessor` 监测到了。

```
拦截到Bean的初始化之前：cat
拦截到Bean的初始化之后：cat
拦截到Bean的初始化之前：dog
拦截到Bean的初始化之后：dog
```

#### 2.1.4 修改后置处理器的返回值为任意

既然 `BeanPostProcessor` 的两个后置处理方法都可以返回任意 `Object` ，那我们就搞几个特殊的情况试一试。

##### 2.1.4.1 返回null

修改 `AnimalBeanPostProcessor` 的 `postProcessBeforeInitialization` 方法，让返回值改为 null ，并在 `postProcessAfterInitialization` 中打印 bean 的引用：

```java
@Override
public Object postProcessBeforeInitialization(Object bean, String beanName) throws BeansException {
    System.out.println("拦截到Bean的初始化之前：" + bean);
    return null;
}

@Override
public Object postProcessAfterInitialization(Object bean, String beanName) throws BeansException {
    System.out.println("拦截到Bean的初始化之后：" + bean);
    return bean;
}
```

重新运行 `main` 方法，发现 `postProcessAfterInitialization` 中并没有打印 null ，而是打印了与 `postProcessBeforeInitialization` 方法中一样的对象：

```
拦截到Bean的初始化之前：com.linkedbear.spring.postprocessor.a_quickstart.bean.Cat@60285225
拦截到Bean的初始化之后：com.linkedbear.spring.postprocessor.a_quickstart.bean.Cat@60285225
拦截到Bean的初始化之前：com.linkedbear.spring.postprocessor.a_quickstart.bean.Dog@7113b13f
拦截到Bean的初始化之后：com.linkedbear.spring.postprocessor.a_quickstart.bean.Dog@7113b13f
```

为什么会是这样呢？我都返回了 null 了，你咋又给我找回来了呢？

这里面的原理，可以向上追溯一层方法调用。借助 IDEA ，发现 SpringFramework 调用 `BeanPostProcessor` 的 `postProcessBeforeInitialization` 方法，是在 `AbstractAutowireCapableBeanFactory` 中的，这里面有一个兜底保护：

```java
@Override
public Object applyBeanPostProcessorsBeforeInitialization(Object existingBean, String beanName)
        throws BeansException {

    Object result = existingBean;
    for (BeanPostProcessor processor : getBeanPostProcessors()) {
        Object current = processor.postProcessBeforeInitialization(result, beanName);
        // 兜底保护
        if (current == null) {
            return result;
        }
        result = current;
    }
    return result;
}
```

可见框架都帮我们做好了，如果真的返回了 null ，那框架就会认为：**你这是一个误操作，我当你没发生过**，于是就把原来的 bean 又找回来了。

##### 2.1.4.2 返回其它类型的对象

既然不能返回 null ，那你传 `Cat` 的时候我换个 `Dog` 行不？哎，有点意思了哈，我们也来试试。

```java
@Override
public Object postProcessBeforeInitialization(Object bean, String beanName) throws BeansException {
    System.out.println("拦截到Bean的初始化之前：" + bean);
    if (bean instanceof Cat) {
        return new Dog();
    }
    return bean;
}
```

重新运行 `main` 方法，发现 `Cat` 真的变成了 `Dog` ！

```
拦截到Bean的初始化之前：com.linkedbear.spring.postprocessor.a_quickstart.bean.Cat@60285225
拦截到Bean的初始化之后：com.linkedbear.spring.postprocessor.a_quickstart.bean.Dog@7113b13f
```

所以由这个设计，是不是有一点慌呢？万一真返回错了类型，那岂不是出大问题？

但是话又说回来，谁会搞这种操作呢。。。所以这个担心是多余的，如果真的要限制住 `BeanPostProcessor` 的类型控制，我们可以在后面尝试搞一个简单的扩展，小伙伴可以到时候一起写一写，体会一下简单的框架再封装。

### 2.2 修改bean的属性

既然能拿到 bean 的本体了，那获取 、修改属性这种操作也就很简单啦，咱们也来简单的写一下。

> 本小节源码位置：`com.linkedbear.spring.postprocessor.b_getproperty`

#### 2.2.1 修改bean

给 `Cat` 添加一个 `name` 属性，并添加上 getter 、setter 、`toString` 方法：

```java
@Component
public class Cat {
    
    private String name;
    
    public String getName() {
        return name;
    }
    
    public void setName(String name) {
        this.name = name;
    }
    
    @Override
    public String toString() {
        return "Cat{" + "name='" + name + '\'' + '}';
    }
}
```

#### 2.2.2 编写后置处理器

这次我们在后置处理器中添加对属性的操作，可以在后置处理之前修改一下属性，看修改之后是否生效：

```java
@Component
public class CatBeanPostProcessor implements BeanPostProcessor {
    
    @Override
    public Object postProcessBeforeInitialization(Object bean, String beanName) throws BeansException {
        if (bean instanceof Cat) {
            Cat cat = (Cat) bean;
            System.out.println("初始化之前，cat的name为：" + cat.getName());
            cat.setName("zhangsan");
        }
        return bean;
    }
    
    @Override
    public Object postProcessAfterInitialization(Object bean, String beanName) throws BeansException {
        if (bean instanceof Cat) {
            Cat cat = (Cat) bean;
            System.out.println("初始化之后，cat的name为：" + cat.getName());
        }
        return bean;
    }
}
```

#### 2.2.3 测试运行

测试运行类的写法与上面完全一致，不多解释啦：

```java
public class PostProcessorGetPropertyApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                "com.linkedbear.spring.postprocessor.b_getproperty");
        ctx.close();
    }
}
```

运行 `main` 方法，控制台打印出修改前后的属性，说明后置处理器确实在 bean 的初始化阶段修改属性。

### 2.3 执行时机探究

既然文档和 javadoc 中说了，它分别在 bean 的初始化阶段前后执行，具体又是什么样呢？咱也来探究一下。

> 现有的知识中，我们知道的 bean 的生命周期应该是这样的：
>
> ![img](《从0开始深入学习Spring》/919de3d6b79b4bde92902392ea2a0c81~tplv-k3u1fbpfcp-zoom-1.image)
>
> 本小节源码位置：`com.linkedbear.spring.postprocessor.c_executetime`

#### 2.3.1 声明bean

像之前研究 bean 的生命周期那样，搞一个三种初始化方法都带的 `Dog` 出来：

```java
public class Dog implements InitializingBean {
    
    public void initMethod() {
        System.out.println("initMethod ...");
    }
    
    @PostConstruct
    public void postConstruct() {
        System.out.println("PostConstruct ...");
    }
    
    @Override
    public void afterPropertiesSet() throws Exception {
        System.out.println("InitializingBean ...");
    }
}
```

#### 2.3.2 编写后置处理器

后置处理器里就不搞花里胡哨了，只打印一下执行时机就好：

```java
public class ExecuteTimeBeanPostProcessor implements BeanPostProcessor {
    
    @Override
    public Object postProcessBeforeInitialization(Object bean, String beanName) throws BeansException {
        if (bean instanceof Dog) {
            System.out.println("postProcessBeforeInitialization ...");
        }
        return bean;
    }
    
    @Override
    public Object postProcessAfterInitialization(Object bean, String beanName) throws BeansException {
        if (bean instanceof Dog) {
            System.out.println("postProcessAfterInitialization ...");
        }
        return bean;
    }
}
```

#### 2.3.3 编写xml配置文件

在三种初始化方式都需要的时候，就不能直接声明 `@Component` 来注册 bean 了，只能通过配置类 / 配置文件的方式来实现。之前在 13 章我们使用了注解配置类的方式注册，这次我们换用 xml 配置文件：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd http://www.springframework.org/schema/context https://www.springframework.org/schema/context/spring-context.xsd">

    <bean id="dog" class="com.linkedbear.spring.postprocessor.c_executetime.bean.Dog" init-method="initMethod"/>

    <bean class="com.linkedbear.spring.postprocessor.c_executetime.config.ExecuteTimeBeanPostProcessor"/>

    <!-- 记得开注解配置，否则@PostConstruct不生效 -->
    <context:annotation-config/>
</beans>
```

#### 2.3.4 测试运行

既然用了 xml 配置文件，那就不要再用注解驱动的 IOC 容器啦，要换用 `ClassPathXmlApplicationContext` 了：

```java
public class BeanPostProcessorExecuteTimeApplication {
    
    public static void main(String[] args) throws Exception {
        ClassPathXmlApplicationContext ctx = new ClassPathXmlApplicationContext(
                "postprocessor/processor-executetime.xml");
        ctx.close();
    }
}
```

操作是一样的，初始化好就不用管了，直接关闭就好。

运行 `main` 方法，控制台打印如下信息：

```
postProcessBeforeInitialization ...
PostConstruct ...
InitializingBean ...
initMethod ...
postProcessAfterInitialization ...
```

由此可以总结出 bean 的初始化阶段的全流程：**`BeanPostProcessor#postProcessBeforeInitialization` → `@PostConstruct` → `InitializingBean` → `init-method` → `BeanPostProcessor#postProcessAfterInitialization`**

也就是下图所示：

![img](《从0开始深入学习Spring》/1d6cafe27f6441c793a82dbfa5d32308~tplv-k3u1fbpfcp-zoom-1.image)

### 2.4 FactoryBean的影响

对于那些 `FactoryBean` ，我们都是只拿它里面创建的真实对象，不要 `FactoryBean` 本身的，这种情况 `BeanPostProcessor` 能一起考虑进去吗？我们也来试一下。

> 本小节源码位置：`com.linkedbear.spring.postprocessor.d_factorybean`

#### 2.4.1 声明Bean+FactoryBean

这次我们搞一个比较符合场景的写法：母鸡下蛋，让 **Hen** 去生产 **Egg** 。

```java
public class Egg {
    
}

@Component
public class Hen implements FactoryBean<Egg> {
    
    @Override
    public Egg getObject() throws Exception {
        return new Egg();
    }
    
    @Override
    public Class<Egg> getObjectType() {
        return Egg.class;
    }
}
```

这样只把母鸡塞进 IOC 容器，我们就可以得到鸡蛋了。

#### 2.4.2 编写后置处理器

后置处理器里面不打算搞花里胡哨的操作了，只打印 bean 的初始化拦截触发就好啦：（与 2.1.2 节一致）

```java
@Component
public class FactoryBeanPostProcessor implements BeanPostProcessor {
    
    @Override
    public Object postProcessBeforeInitialization(Object bean, String beanName) throws BeansException {
        System.out.println("拦截到Bean的初始化之前：" + bean);
        return bean;
    }
    
    @Override
    public Object postProcessAfterInitialization(Object bean, String beanName) throws BeansException {
        System.out.println("拦截到Bean的初始化之后：" + bean);
        return bean;
    }
}
```

#### 2.4.3 测试运行

与前面一样，只初始化 IOC 容器，不干别的事：

```java
public class FactoryBeanPostProcessorApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                "com.linkedbear.spring.postprocessor.d_factorybean");
        ctx.close();
    }
}
```

运行 `main` 方法，发现控制台只打印了 `Hen` 的拦截：

```java
拦截到Bean的初始化之前：com.linkedbear.spring.postprocessor.d_factorybean.bean.Hen@12cdcf4
拦截到Bean的初始化之后：com.linkedbear.spring.postprocessor.d_factorybean.bean.Hen@12cdcf4
```

咦？为什么没有 Egg 的初始化触发呢？（短暂的思考一下~）

有想起来吗？如果没有，那就翻回 11 章 1.2.4.2 节看看吧。**`FactoryBean` 的生命周期与 IOC 容器一致，而 `FactoryBean` 生产 bean 的时机是延迟创建的**。

#### 2.4.4 修改测试

既然没产出来，那我们就手动 get 一下吧：

```java
public static void main(String[] args) throws Exception {
    AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
        "com.linkedbear.spring.postprocessor.d_factorybean");
    Egg egg = ctx.getBean(Egg.class);
    System.out.println(egg);
}
```

重新运行 `main` 方法，这次控制台打印出来了：

```java
拦截到Bean的初始化之前：com.linkedbear.spring.postprocessor.d_factorybean.bean.Hen@12cdcf4
拦截到Bean的初始化之后：com.linkedbear.spring.postprocessor.d_factorybean.bean.Hen@12cdcf4
拦截到Bean的初始化之后：com.linkedbear.spring.postprocessor.d_factorybean.bean.Egg@a74868d
com.linkedbear.spring.postprocessor.d_factorybean.bean.Egg@a74868d
```

注意哦，这里**只打印了初始化之后，并没有初始化之前**的动作，这也就回应了上面 `BeanPostProcessor` 的 javadoc 内容。

## 小结与练习

1. 什么是 `BeanPostProcessor` ？
2. `BeanPostProcessor` 发挥作用的时间点是什么？它与 bean 的生命周期有什么关系？
3. 练习本节中涉及到的案例，体会 `BeanPostProcessor` 的用法。

【对于 `BeanPostProcessor` 的入门与基本使用，差不多先了解这么多。下一章，我们会介绍更多的 `BeanPostProcessor` 类型】

# 27. IOC高级-BeanPostProcessor的扩展及作用时机

上一章，咱对 `BeanPostProcessor` 有一个大体的认识，也做了几个练习和探究。这一章我们来研究 `BeanPostProcessor` 的扩展，内容难度会更高，小伙伴们一定要认真记笔记、做练习，多思考多总结呀。

借助 IDEA ，发现 `BeanPostProcessor` 有如下的接口扩展：

![img](《从0开始深入学习Spring》/f32dca851d1a41ffab629bb141fb97b7~tplv-k3u1fbpfcp-zoom-1.image)

这些接口，各自扩展出来的功能也都不同，下面我们逐个来研究。

## 1. InstantiationAwareBeanPostProcessor【熟悉】

从类名上看，它与**实例化**有关系，而且它又带着一个 **aware** ，难道是在暗示我们又跟回调注入什么的相关吗？还是先看下文档注释吧。

### 1.1 javadoc理解

> Subinterface of BeanPostProcessor that adds a before-instantiation callback, and a callback after instantiation but before explicit properties are set or autowiring occurs. Typically used to suppress default instantiation for specific target beans, for example to create proxies with special TargetSources (pooling targets, lazily initializing targets, etc), or to implement additional injection strategies such as field injection. NOTE: This interface is a special purpose interface, mainly for internal use within the framework. It is recommended to implement the plain BeanPostProcessor interface as far as possible, or to derive from InstantiationAwareBeanPostProcessorAdapter in order to be shielded from extensions to this interface.
>
> `BeanPostProcessor` 的子接口，它添加了实例化之前的回调，以及在实例化之后但在设置显式属性或自动装配发生之前的回调。 通常用于抑制特定目标 bean 的默认实例化，例如创建具有特殊 `TargetSource` 的代理（池目标，延迟初始化目标等），或实现其他注入策略，例如字段注入。 注意：此接口是专用接口，主要供框架内部使用。建议尽可能实现普通的 `BeanPostProcessor` 接口，或从 `InstantiationAwareBeanPostProcessorAdapter` 派生，以免对该接口进行扩展。

文档注释已经写得很明白了，它的作用有两个：

- 拦截并替换 Bean 的默认实例化动作
- 拦截 Bean 的属性注入和自动装配，并在此之前扩展

所以，我们是不是可以先试着猜想一波，它对 bean 的生命周期的干预应该是在这两个时机：

![img](《从0开始深入学习Spring》/519413e68253488a85c01fdc9c3a75d2~tplv-k3u1fbpfcp-zoom-1.image)

是不是真的这样，咱来看看 `InstantiationAwareBeanPostProcessor` 中定义了什么方法，从中获取信息来检验猜想是否正确。

### 1.2 接口方法定义

`InstantialtionAwareBeanPostProcessor` 中定义了 4 个方法（ 5.1 之前是 3 个）：

```java
default Object postProcessBeforeInstantiation(Class<?> beanClass, String beanName) throws BeansException {
    return null;
}

default boolean postProcessAfterInstantiation(Object bean, String beanName) throws BeansException {
    return true;
}

default PropertyValues postProcessProperties(PropertyValues pvs, Object bean, String beanName)
        throws BeansException {
    return null;
}

// 已过时，被上面的方法代替
@Deprecated
default PropertyValues postProcessPropertyValues(
        PropertyValues pvs, PropertyDescriptor[] pds, Object bean, String beanName) throws BeansException {
    return pvs;
}
```

分别看这三个方法，它们的作用分别是：

- ```
  postProcessBeforeInstantiation
  ```

   

  ：在 bean 的实例化之前处理

  - 非常容易理解，它可以拦截 bean 原本的实例化方法，转为用这里的实例化

- ```
  postProcessAfterInstantiation
  ```

   

  ：在 bean 的实例化之后处理

  - 这个方法比较奇怪，返回值是 boolean ，它有代表什么意思吗？
  - 其实，它与下面的 `postProcessProperties` 方法有关，如果返回 false ，则 `postProcessProperties` 方法不会执行

- ```
  postProcessProperties
  ```

   

  ：在设置属性时处理 ？？？（好像不大对劲）

  - 根据 javadoc 得知，这个方法是在属性赋值之前触发的，而 `PropertyValues` 又是一组 `field - value` 的键值对
  - 由此可以断定，`postProcessProperties` 方法最终会返回一组属性和值的 `PropertyValues` ，让它参与 bean 的属性赋值环节

看来与上面一开始的猜想大差不离，那加入 `InstantiationAwareBeanPostProcessor` 后的 bean 的生命周期就是这样子咯：

![img](《从0开始深入学习Spring》/8a7337c1733e4d10b78e4758eb8d2770~tplv-k3u1fbpfcp-zoom-1.image)

具体的操作，我们可以写几个 Demo 来验证一下，顺便体会一下 `InstantiationAwareBeanPostProcessor` 对 bean 的扩展。

### 1.3 InstantiationAwareBeanPostProcessor拦截bean创建

先来试一下第一个 `postProcessBeforeInstantiation` 方法吧，既然它能直接拦截 bean 的创建，那正常的 bean 里头的东西，或许被它一拦截，就没了吧。

#### 1.3.1 声明bean

这次我们来玩个球，给球声明一个 id 的属性就够了：（不要忘记写 `toString` 方法，方便打印查看）

```java
public class Ball {
    
    private String id;
    
    public String getId() {
        return id;
    }
    
    public void setId(String id) {
        this.id = id;
    }
    
    @Override
    public String toString() {
        return "Ball{" + "id='" + id + '\'' + '}';
    }
}
```

#### 1.3.2 编写后置处理器

既然是拦截创建，那我就希望，能在后置处理器中单独创建一个球，不要配置声明的。于是后置处理器就可以这样编写：

```java
public class BallFactoryInstantiationProcessor implements InstantiationAwareBeanPostProcessor {
    
    @Override
    public Object postProcessBeforeInstantiation(Class<?> beanClass, String beanName) throws BeansException {
        if ("ball".equals(beanName)) {
            // 返回非null，代表拦截创建
            Ball ball = new Ball();
            ball.setId("工厂球~");
            return ball;
        }
        // 默认直接返回null，代表不拦截
        return null;
    }
}
```

这里我在 `postProcessBeforeInstantiation` 中显式的 new 了一个球，这样回头如果真的走了这个分支，那将返回后置处理器创建的球。

#### 1.3.3 编写xml配置文件

xml 配置文件中，要声明一个 `Ball` 的 bean ，同时把后置处理器也注册进去：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="ball" class="com.linkedbear.spring.postprocessor.e_instantiation.bean.Ball">
        <property name="id" value="123456"/>
    </bean>
    
    <bean class="com.linkedbear.spring.postprocessor.e_instantiation.config.BallFactoryInstantiationProcessor"/>
</beans>
```

#### 1.3.4 测试运行

好了，可以编写测试类来检验效果了，使用 xml 配置文件来驱动 IOC 容器：

```java
public class InstantiationAwareApplication {
    
    public static void main(String[] args) throws Exception {
        ClassPathXmlApplicationContext ctx = new ClassPathXmlApplicationContext(
                "postprocessor/processor-instantiation.xml");
        Ball ball = (Ball) ctx.getBean("ball");
        System.out.println(ball);
    }
}
```

运行 `main` 方法，控制台打印的是 “工厂球” ，证明 `BallFactoryInstantiationProcessor` 已经成功拦截了 xml 配置文件中声明的 `Ball` 的创建，转而使用后置处理器的逻辑创建了。

```
Ball{id='工厂球~'}
```

### 1.4 InstantiationAwareBeanPostProcessor给bean做属性赋值

继续顺延上面的 Demo ，我们来试试如果不给 bean 的属性赋值，交由 `InstantiationAwareBeanPostProcessor` 来做，它真的能做到吗？

#### 1.4.1 扩展xml配置文件

再声明一个 `Ball` ，这次只创建对象，不给 id 赋值：

```xml
<bean id="ball2" class="com.linkedbear.spring.postprocessor.e_instantiation.bean.Ball"/>
```

#### 1.4.2 扩展BallFactoryInstantiationProcessor

这次要做属性赋值了，对应的接口方法是 `postProcessProperties` ，我们来重写它：

```java
    @Override
    public PropertyValues postProcessProperties(PropertyValues pvs, Object bean, String beanName)
            throws BeansException {
        if ("ball2".equals(beanName)) {
            MutablePropertyValues values = new MutablePropertyValues(pvs);
            values.addPropertyValue("id", "拦截球~");
            return values;
        }
        return null;
    }
```

> 由于 `PropertyValues` 设计为接口且只暴露可读方法，此处选用实现类重新包装并添加 id 属性（强转也可以，但此种写法更稳妥）

#### 1.4.3 测试运行

修改测试代码，添加 ball2 的获取，并打印出来：

```java
    public static void main(String[] args) throws Exception {
        ClassPathXmlApplicationContext ctx = new ClassPathXmlApplicationContext(
                "postprocessor/processor-instantiation.xml");
        Ball ball = (Ball) ctx.getBean("ball");
        System.out.println(ball);
        
        Ball ball2 = (Ball) ctx.getBean("ball2");
        System.out.println(ball2);
    }
```

重新运行 `main` 方法，控制台打印出了 “拦截球” ，证明 `postProcessProperties` 方法的确能给 bean 注入属性。

```
Ball{id='工厂球~'}
Ball{id='拦截球~'}
```

#### 1.4.4 postProcessProperties不会影响postProcessBeforeInstantiation

突然意识到一个伏笔是吧，前面编写后置处理器的时候，一直都是拿 bean 的 name 做匹配。如果在 `postProcessBeforeInstantiation` 方法中，我们把判断条件改为所有 Ball 都拦截，那效果会怎么样呢？

```java
    @Override
    public Object postProcessBeforeInstantiation(Class<?> beanClass, String beanName) throws BeansException {
        if (Ball.class.equals(beanClass)) {
            Ball ball = new Ball();
            ball.setId("工厂球~");
            return ball;
        }
        return null;
    }
```

修改为上述代码后，重新运行 `main` 方法，控制台打印了两个工厂球：

```
Ball{id='工厂球~'}
Ball{id='工厂球~'}
```

说明 `postProcessBeforeInstantiation` 方法执行完毕后，并不会再执行 `postProcessProperties` （换句话说，`postProcessProperties` 方法没有机会能再影响 `postProcessBeforeInstantiation` 方法创建出来的对象）

### 1.5 postProcessAfterInstantiation的作用

上面的分析中我们也说了，`postProcessAfterInstantiation` 方法如果返回 false ，则 `postProcessProperties` 方法就不会执行，下面简单验证一下。

在 `BallFactoryInstantiationProcessor` 中加入 `postProcessAfterInstantiation` 方法的重写：

```java
@Override
public boolean postProcessAfterInstantiation(Object bean, String beanName) throws BeansException {
    return false;
}
```

重新运行 `main` 方法，发现 ball2 已经没有 id 了：

```java
Ball{id='工厂球~'}
Ball{id='null'}
```

## 2. SmartInstantiationAwareBeanPostProcessor【了解】

相较于 `InstantiationAwareBeanPostProcessor` 只多了一个 **smart** ，意思是它更聪明咯？还真是，这个接口扩展了 3 个额外的方法，而且每个方法还都挺有用的，我们可以来简单的看看。

```java
default Class<?> predictBeanType(Class<?> beanClass, String beanName) throws BeansException {
    return null;
}

default Constructor<?>[] determineCandidateConstructors(Class<?> beanClass, String beanName) throws BeansException {
    return null;
}

default Object getEarlyBeanReference(Object bean, String beanName) throws BeansException {
    return bean;
}
```

- `predictBeanType` ：预测 bean 的类型（不能预测时返回 null ）

- ```
  determineCandidateConstructors
  ```

   

  ：根据 bean 对应 Class 中的构造器定义，决定使用哪个构造器进行对象实例化

  - 这个方法很重要，如果 bean 没有声明任何构造器，则此处会拿到默认的无参构造器；如果声明了多个构造器，则该处会根据 IOC 容器中的 bean 和指定的策略，选择最适合的构造器

- `getEarlyBeanReference` ：提早暴露出 bean 的对象引用（该方法与 bean 的循环依赖解决有关，在 SpringBoot 的小册 15 章有讲）

看着这么高大上，但是讲真，这个接口在现阶段不是很好演示，而且它本身属于 SpringFramework 内部的接口，通常我们根本用不到，所以这个小伙伴们知道下就可以了，不要在这上面耗费太多的时间和精力。

到后面 IOC 原理中，bean 的完整生命周期会涉及 `SmartInstantiationAwareBeanPostProcessor` 的，小伙伴们可以到时候留意一下。

## 3. DestructionAwareBeanPostProcessor【了解】

顾名思义，它可以在 bean 的**销毁**前拦截处理。这个接口的方法定义也很简单：

```java
void postProcessBeforeDestruction(Object bean, String beanName) throws BeansException;

default boolean requiresDestruction(Object bean) {
    return true;
}
```

很明显它就是一个回调的处理而已，没什么花里胡哨的。

下面我们还是来简单的演示一下它的使用。

### 3.1 DestructionAwareBeanPostProcessor的使用

前面在 bean 的生命周期中，我们有写过一个全生命周期的 Pen （源码位置：`com.linkedbear.spring.lifecycle.c_initializingbean.bean.Pen3` ），我们可以拿来利用一下。

> 本小节源码位置：`com.linkedbear.spring.postprocessor.f_destruction`

#### 3.1.1 声明Bean

虽说是用那个 `Pen` ，不过在这个 Demo 中我们只需要它的销毁方法：（此处只声明了 `@PreDestroy` 与 `DisposableBean` ）

```java
public class Pen implements DisposableBean {
    
    private Integer ink = 100;
    
    @PreDestroy
    public void outwellInk() {
        System.out.println("Pen @PreDestroy 钢笔中的墨水都放干净了。。。");
    }
    
    @Override
    public void destroy() throws Exception {
        System.out.println("Pen DisposableBean 写完字了。。。");
    }
    
    // getter setter
}
```

#### 3.1.2 编写后置处理器

既然是在 bean 的销毁阶段回调，那我们可以在这里针对 Pen 给它放干墨水（模拟操作）：

```java
@Component
public class DestructionPenPostProcessor implements DestructionAwareBeanPostProcessor {
    
    @Override
    public void postProcessBeforeDestruction(Object bean, String beanName) throws BeansException {
        if (bean instanceof Pen) {
            System.out.println("DestructionPenPostProcessor postProcessBeforeDestruction run ......");
            Pen pen = (Pen) bean;
            pen.setInk(0);
        }
    }
}
```

#### 3.1.3 测试运行

编写测试代码，直接包扫描，驱动 IOC 容器。驱动完成后啥也不用干，直接销毁 IOC 容器就可以：

```java
public class DestructionPostProcessorApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                "com.linkedbear.spring.postprocessor.f_destruction");
        ctx.close();
    }
}
```

运行 `main` 方法，控制台打印如下信息：

```
DestructionPenPostProcessor postProcessBeforeDestruction run ......
@PreDestroy - 钢笔中的墨水都放干净了。。。
Pen DisposableBean 写完字了。。。
```

由此可以体会到 `DestructionAwareBeanPostProcessor` 的使用。

### 3.2 Spring中的DestructionAwareBeanPostProcessor

关于这个接口的使用，在 SpringFramework 中有个蛮经典的：**监听器的引用释放回调**。由于 `ApplicationContext` 中会注册一些 `ApplicationListener` ，而这些 `ApplicationListener` 与 `ApplicationContext` **互相引用**，所以在 IOC 容器销毁之前，就需要将这些引用断开，这样才可以进行对象的销毁和回收。

## 4. MergedBeanDefinitionPostProcessor【了解】

在前面的 25 章第 3 节，咱有学习 `BeanDefinition` 的合并，这个 `BeanDefinition` 合并的过程，在后置处理器中也有对应的拦截处理。

### 4.1 回顾BeanDefinition的合并

回想一下，`BeanDefinition` 合并的意义是啥来着？是为了将父 bean 继承或者已经定义好的注入属性一块拿过来，这样就不用子 bean 再定义一次了吧！这种合并是一种情况，不过还有一种情况，它发生在基于注解的类继承上：

```java
public abstract class Animal {

    @Autowired
    private Person person;
}
public class Cat extends Animal {
    
    private String name;
}
```

这种情况下，向 IOC 容器注册 `Cat` 时，Spring 在底层也会把 person 需要注入的定义信息合并进去，并标注它需要自动注入处理。

### 4.2 接口方法定义

再来看 `MergedBeanDefinitionPostProcessor` 的接口，它只定义了一个方法：

```java
void postProcessMergedBeanDefinition(RootBeanDefinition beanDefinition, Class<?> beanType, String beanName);
```

（ 5.1 后又定义了一个 `resetBeanDefinition` 方法，仅用于清除 `BeanFactory` 内部缓存，此处不对此展开）

这个方法的 javadoc 出奇的少，甚至都没给什么有用的信息，那这咋研究呢？得了，我们写个 Demo 测一下吧。

### 4.3 MergedBeanDefinitionPostProcessor的使用

为了还原出 `BeanDefinition` 的合并，这里把上面举的例拿过来测试用吧。

> 本小节源码位置：`com.linkedbear.spring.postprocessor.g_mergedefinition`

#### 4.3.1 声明bean

声明的 bean 就是上面的一个 `Animal` ，一个 `Cat` ，当然还得有 `Person` ：

```java
public abstract class Animal {
    
    @Autowired
    private Person person;
    
    public Person getPerson() {
        return person;
    }
    
    public void setPerson(Person person) {
        this.person = person;
    }
}
@Component
public class Cat extends Animal {
    
    @Value("咪咪")
    private String name;
    
    @Override
    public String toString() {
        return "Cat {person: " + this.getPerson() + ", name: " + name + "}";
    }
}
@Component
public class Person {
    
}
```

#### 4.3.2 编写后置处理器

后置处理器里面不用写什么花里胡哨的结构，先拦截一下就好：

```java
@Component
public class MergeDefinitionPostProcessor implements MergedBeanDefinitionPostProcessor {
    
    @Override
    public void postProcessMergedBeanDefinition(RootBeanDefinition beanDefinition, Class<?> beanType, String beanName) {
        if (Cat.class.equals(beanType)) {
            System.out.println("MergeDefinitionPostProcessor postProcessMergedBeanDefinition run......");
            System.out.println(beanDefinition);
        }
    }
}
```

> 此处稍微停一下，思考一下此处 `postProcessMergedBeanDefinition` 的参数列表中为什么只有 beanDefinition 和 beanType ？难道 bean 还没有创建吗？

#### 4.3.3 测试运行

测试的代码也很简单，还是直接使用注解 IOC 容器扫描包即可：

```java
public class MergeDefinitionPostProcessorApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                "com.linkedbear.spring.postprocessor.g_mergedefinition");
        ctx.close();
    }
}
```

运行 `main` 方法，控制台有打印 `Cat` 的 `BeanDefinition` 信息，说明确实拦截到 Cat 的定义信息合并了。

可是上面的问题呢？此时 bean 被创建了吗？

#### 4.3.4 给Cat添加无参构造器

重写 Cat 的无参构造器，让它在控制台打印一句话：

```java
@Component
public class Cat extends Animal {
    
    public Cat() {
        System.out.println("Cat constructor run ......");
    }
```

重新运行 `main` 方法，发现是先创建的 `Cat` 后打印的后置处理器执行：

```
Cat constructor run ......
MergeDefinitionPostProcessor postProcessMergedBeanDefinition run......
```

这个设计是为什么呢？既然创建出了 bean ，为什么后置处理器的回调中没有把 bean 传给我们呢？

#### 4.3.5 调整Animal的自动注入位置

问题思考不出来没关系，我们来调整一点代码，让 `Animal` 中的 `person` 使用 setter 的自动注入，并在控制台打印一句话：

```java
    @Autowired
    public void setPerson(Person person) {
        System.out.println("Animal setPerson run ......");
        this.person = person;
    }
```

再次运行 `main` 方法，发现 setter 方法的自动注入在最后才打印：

```
Cat constructor run ......
MergeDefinitionPostProcessor postProcessMergedBeanDefinition run......
Animal setPerson run ......
```

由此可以得出结论了吧：`postProcessMergedBeanDefinition` 方法发生在 **bean 的实例化之后，自动注入之前**。而这个设计，就是为了**在属性赋值和自动注入之前，把要注入的属性都收集好**，这样才能顺利的向下执行注入的逻辑。

而实例化好的 bean 没有传入接口中的原因，其实也很好解释：**人家是合并 `BeanDefinition` 的，跟 bean 的实例有什么关系呢**（**最少知道原则**）？

### 4.4 Spring中的MergeDefinitionPostProcessor

在 SpringFramework 中，一个非常重要的 `MergeDefinitionPostProcessor` 的实现，就是 `AutowiredAnnotationBeanPostProcessor` ，它负责给 bean 实现注解的自动注入，而注入的依据就是 `postProcessMergedBeanDefinition` 后整理的标记（这个标记会在 IOC 原理的 bean 完整生命周期中提及）。

> 当然，通常 `MergedBeanDefinitionPostProcessor` 这个后置处理器也不会在开发中使用，仅仅用于 SpringFramework 的内部，小伙伴们知道下就好，不要在这上面耗费太长时间和精力。

## 小结与练习

1. `BeanPostProcessor` 的扩展都有哪些？
2. `InstantiationAwareBeanPostProcessor` 扩展了哪些回调时机？
3. 整理现有已经学过的 bean 的生命周期中的各种回调时机，并编写一个综合小练习，加深对生命周期的理解和印象。

【 SpringFramework 中关于 bean 的后置处理器就差不多这些，下面还有另外一种后置处理器，它是针对 `BeanDefinition` 的：**`BeanFactoryPostProcessor`**】

# 28. IOC高级-BeanFactoryPostProcessor的使用

前面两章，咱把 `BeanPostProcessor` 以及它的扩展都学习了一遍，这一章要学习的，是给 `BeanDefinition` 用的后置处理器了：`BeanFactoryPostProcessor` 。或许小伙伴会很懵逼：名是 `BeanFactoryPostProcessor` ，但是给 `BeanDefinition` 用的，是不是有搞错呢？不要方，跟着小册学习就完事啦！

## 1. BeanFactoryPostProcessor概述【理解】

老套路了，先看官方文档的描述吧。

【以下内容可能比较啰里八嗦，想直接拿来面试的小伙伴请直接移步 1.4 节】

### 1.1 官方文档

> The next extension point that we look at is the org.springframework.beans.factory.config.BeanFactoryPostProcessor. The semantics of this interface are similar to those of the BeanPostProcessor, with one major difference: BeanFactoryPostProcessor operates on the bean configuration metadata. That is, the Spring IoC container lets a BeanFactoryPostProcessor read the configuration metadata and potentially change it before the container instantiates any beans other than BeanFactoryPostProcessor instances.
>
> 该接口的语义与 `BeanPostProcessor` 的语义相似，但有一个主要区别：`BeanFactoryPostProcessor` 对 Bean 的配置元数据进行操作。也就是说，IOC 容器允许 `BeanFactoryPostProcessor` 读取配置元数据，并有可能在容器实例化除 `BeanFactoryPostProcessor` 实例以外的任何 bean 之前更改它。

果然，官方文档也说了，它操作的是 **Bean 的配置元信息**。而且这里面还有一个非常关键的点：**它可以在 bean 实例的初始化之前修改定义信息**，换句话说，它可以对原有的 `BeanDefinition` 进行修改。由于 SpringFramework 中设计的**所有 bean 在没有实例化之前都是以 `BeanDefinition` 的形式存在**，如果提前修改了 `BeanDefinition` ，那么在 bean 的实例化时，最终创建出的 bean 就会受到影响。这个设计，我们在下面会有演示，小伙伴们先记住 `BeanFactoryPostProcessor` 的这个功能就好。

### 1.2 javadoc

同样的，看看 javadoc 中怎么描述 `BeanFactoryPostProcessor` ：

> Allows for custom modification of an application context's bean definitions, adapting the bean property values of the context's underlying bean factory. Application contexts can auto-detect BeanFactoryPostProcessor beans in their bean definitions and apply them before any other beans get created. ... A BeanFactoryPostProcessor may interact with and modify bean definitions, but never bean instances. Doing so may cause premature bean instantiation, violating the container and causing unintended side-effects. If bean instance interaction is required, consider implementing BeanPostProcessor instead.
>
> 允许自定义修改 `ApplicationContext` 中的 `BeanDefinition` ，以适应上下文基础 `BeanFactory` 的 Bean 属性值。 `ApplicationContext` 可以在其 Bean 的定义信息中自动检测 `BeanFactoryPostProcessor` 的 Bean，并在创建任何其他 Bean 之前应用它们。 `BeanFactoryPostProcessor` 可以与 `BeanDefinition` 进行交互并进行修改，但不能与 bean 的实例进行交互。这样做可能会导致 bean 实例化过早，从而违反了容器的规矩并造成了意外的副作用。如果需要与 bean 实例交互，请考虑实现 `BeanPostProcessor` 。

讲真，这个文档注释和翻译都挺难理解的，小册试着重新解释一下。

`BeanFactoryPostProcessor` 本身也属于 `BeanFactory` 中的 bean ，但是由于它的特殊性，所以 `ApplicationContext` 可以检查、获取它们，并且将其应用到 `BeanFactory` 中。

`BeanFactoryPostProcessor` 的作用是在 `BeanDefinition` 已经注册到 `BeanFactory` 后，对 `BeanDefinition` 进行修改 / 配置。除此之外，`BeanFactoryPostProcessor` 与 `BeanPostProcessor` **没有任何关联**，一个是影响 `BeanDefinition` 的，一个是影响 bean 实例的。

`BeanFactoryPostProcessor` 中原则上不允许访问、创建任何 bean 实例（此时 IOC 容器还没初始化好，`BeanPostProcessor` 都没有准备好，会导致创建的 bean 实例产生残缺）。

用这样三段话，配合官方文档，基本上就可以把 `BeanFactoryPostProcessor` 的作用都解释到位了，小伙伴们如果还是觉得不好理解，也没有关系，马上下面就会通过实例来研究 `BeanFactoryPostProcessor` 的使用。

### 1.3 接口方法定义

`BeanFactoryPostProcessor` 中只定义了一个方法，就是对 `BeanFactory` 的后置处理：

```java
void postProcessBeanFactory(ConfigurableListableBeanFactory beanFactory) throws BeansException;
```

> 注意看这里的设计，即便 `ConfigurableListableBeanFactory` 的最终实现类只有 `DefaultListableBeanFactory` ，这里的入参也是接口，可见**依赖倒转**的设计在 SpringFramework 中体现得淋漓尽致呀！

这个方法上的 javadoc 可谓是把 `BeanFactoryPostProcessor` 的作用时机和使用方法都说明白了：

> Modify the application context's internal bean factory after its standard initialization. All bean definitions will have been loaded, but no beans will have been instantiated yet. This allows for overriding or adding properties even to eager-initializing beans.
>
> 在标准初始化之后，修改 `ApplicationContext` 内部的 `BeanFactory` 。此时所有 `BeanDefinition` 都将被加载，但尚未实例化任何 bean 。在此可以给 bean 覆盖或添加属性，甚至可以用于初始化 bean 。

是不是已经开始感觉有点啰嗦了？如果感觉到啰嗦，那就说明小伙伴已经慢慢有感觉了，小册配个图帮小伙伴检验一下自己想的对不对吧。

![img](《从0开始深入学习Spring》/12f1bc8be6a548d9be035e0770a44e49~tplv-k3u1fbpfcp-zoom-1.image)

### 1.4 【面试题】面试中如何概述BeanFactoryPostProcessor

以下答案仅供参考，可根据自己的理解调整回答内容：

**`BeanFactoryPostProcessor` 是容器的扩展点，它用于 IOC 容器的生命周期中，所有 `BeanDefinition` 都注册到 `BeanFactory` 后回调触发，用于访问 / 修改已经存在的 `BeanDefinition` 。与 `BeanPostProcessor` 相同，它们都是容器隔离的，不同容器中的 `BeanFactoryPostProcessor` 不会相互起作用。**

关键回答点：**改变 Bean 的定义信息**

## 2. BeanFactoryPostProcessor的使用【熟悉】

下面我们来实际使用一下 `BeanFactoryPostProcessor` ，来体会它对 `BeanDefinition` 的访问和修改。

先说下需求吧：构造几个 `Color` 的类对象，并在 bean 还没有创建之前，把 bean 的名称设置到 bean 的属性上。

> 本小节源码位置：`com.linkedbear.spring.postprocessor.h_factoryprocessor`

### 2.1 声明bean

咱不搞那么复杂的模型，一个 `Color` 的抽象类加两个子类就好：（注意两个子类要标注 `@Component` 注解注册到 IOC 容器）

```java
public abstract class Color {

    protected String name;
    
    public String getName() {
        return name;
    }
    
    public void setName(String name) {
        this.name = name;
    }
}
@Component
public class Red extends Color {
    
    @Override
    public String toString() {
        return "Red{" + "name='" + name + '\'' + "}";
    }
}
@Component
public class Green extends Color {
    
    @Override
    public String toString() {
        return "Green{" + "name='" + name + '\'' + "}";
    }
}
```

### 2.2 编写后置处理器

先理一下思路：后置处理器中，既然拿到的参数是 `BeanFactory` ，那就可以取出里面的 `BeanDefinition` ，并给它们添加属性值了。

先把架子写出来，由于 `ConfigurableListableBeanFactory` 无法通过类型取出指定的 bean ，所以只能取出全部，挨个判断了：

```java
@Component
public class ColorNameSetterFactoryPostProcessor implements BeanFactoryPostProcessor {
    
    @Override
    public void postProcessBeanFactory(ConfigurableListableBeanFactory beanFactory) throws BeansException {
        Stream.of(beanFactory.getBeanDefinitionNames()).forEach(beanName -> {
            BeanDefinition beanDefinition = beanFactory.getBeanDefinition(beanName);
            
        });
    }
}
```

之后就是判断 `BeanDefinition` 内部生成 bean 的类型了，由于只能获取到 `beanClassName` ，没有办法取父类，所以只能借助反射来搞定了：

```java
public void postProcessBeanFactory(ConfigurableListableBeanFactory beanFactory) throws BeansException {
    Stream.of(beanFactory.getBeanDefinitionNames()).forEach(beanName -> {
        BeanDefinition beanDefinition = beanFactory.getBeanDefinition(beanName);
        if (StringUtils.hasText(beanDefinition.getBeanClassName())) {
            if (Class.forName(beanDefinition.getBeanClassName()).getSuperclass().equals(Color.class)) {

            }
        }
    });
}
```

不过这样写，`Class.forName()` 方法会提示需要捕捉 `ClassNotFoundException` 。最简单的方法是在整个 foreach 外层套一个 `try-catch` ，不过我们可以利用 SpringFramework 中的工具类 `ClassUtils` 来避免异常捕捉：

```java
ClassUtils.resolveClassName(beanDefinition.getBeanClassName(), this.getClass().getClassLoader())
```

> `ClassUtils.resolveClassName()` 方法内部已经帮我们搞定了 try-catch ，所以不会再出现异常类型检查和捕捉的提示。

如果这样判断后，bean 的父类确实是 `Color` ，那就可以添加属性值了：（以下是完整写法）

```java
public void postProcessBeanFactory(ConfigurableListableBeanFactory beanFactory) throws BeansException {
    Stream.of(beanFactory.getBeanDefinitionNames()).forEach(beanName -> {
        BeanDefinition beanDefinition = beanFactory.getBeanDefinition(beanName);
        if (StringUtils.hasText(beanDefinition.getBeanClassName())) {
            if (ClassUtils.resolveClassName(beanDefinition.getBeanClassName(), this.getClass().getClassLoader())
                .getSuperclass().equals(Color.class)) {
                beanDefinition.getPropertyValues().add("name", beanName);
            }
        }
    });
}
```

### 2.3 测试运行

与前面的套路一样，直接使用注解 IOC 容器，包扫描驱动：

```java
public class FactoryProcessorApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                "com.linkedbear.spring.postprocessor.h_factoryprocessor");
        Red red = ctx.getBean(Red.class);
        System.out.println(red);
    }
}
```

运行 `main` 方法，控制台打印出 red 的 `name` 属性，证明 `ColorNameSetterFactoryPostProcessor` 已经起到了作用。

### 2.4 替代方案

可能会有小伙伴察觉到哪里不对劲了：哎，这个策略如果用 `BeanPostProcessor` 实现，岂不是更简单？

```java
public class ColorNameSetterPostProcessor implements BeanPostProcessor {
    
    @Override
    public Object postProcessAfterInitialization(Object bean, String beanName) throws BeansException {
        if (bean instanceof Color) {
            Color color = (Color) bean;
            color.setName(beanName);
        }
        return bean;
    }
}
```

显然，这种写法更简单是吧。对于这种需求来讲，固然是使用 `BeanPostProcessor` 更好。小伙伴辩证的根据需求确定解决方案，这个非常好！赞赏之余，小册想多说一句：既然 SpringFramework 中有这个设计，自然也有它的使用场景，而且我们最好对比着来看这两种不同的后置处理器。

### 2.5 【面试题】对比BeanPostProcessor与BeanFactoryPostProcessor

以下答案仅供参考，可根据自己的理解调整、组织回答：

|              | BeanPostProcessor                           | BeanFactoryPostProcessor                                     |
| ------------ | ------------------------------------------- | ------------------------------------------------------------ |
| 处理目标     | bean 实例                                   | `BeanDefinition`                                             |
| 执行时机     | bean 的初始化阶段前后（已创建出 bean 对象） | `BeanDefinition` 解析完毕，注册进 `BeanFactory` 的阶段（ bean 未实例化） |
| 可操作的空间 | 给 bean 的属性赋值、创建代理对象等          | 给 `BeanDefinition` 中增删属性、移除 `BeanDefinition` 等     |



### 2.6 BeanDefinition剔除的案例回顾

还记得 25 章 2.2.3 节我们演示的 `BeanDefinition` 剔除吗？当时那个案例是把所有的性别为 male 的 `Person` 都剔除掉，这样容器初始化的时候不会创建这些 `Person` 对象。不过那里面用的是强转到 `BeanDefinitionRegistry` 了，这个操作虽然没什么危险，但编程原则上还是不太合适的。so ，有没有针对 `BeanDefinitionRegistry` 的后置处理器呢？哎，还真有，接下来我们继续往下学习。

## 3. BeanDefinitionRegistryPostProcessor概述【理解】

关于 `BeanDefinitionRegistryPostProcessor` ，在官方文档上没有任何的信息可以供我们参考，so 只能靠 javadoc 了。

### 3.1 javadoc

> Extension to the standard BeanFactoryPostProcessor SPI, allowing for the registration of further bean definitions before regular BeanFactoryPostProcessor detection kicks in. In particular, BeanDefinitionRegistryPostProcessor may register further bean definitions which in turn define BeanFactoryPostProcessor instances.
>
> 对标准 `BeanFactoryPostProcessor` 的 SPI 的扩展，允许在进行常规 `BeanFactoryPostProcessor` 检测之前注册其他 Bean 的定义信息。特别是， `BeanDefinitionRegistryPostProcessor` 可以注册其他 Bean 的定义，这些定义又定义了 `BeanFactoryPostProcessor` 实例。

文档注释中又提到这个陌生的概念了：**SPI** ，不要方，后面 30 章的模块装配综合案例中会详细介绍 SPI 的。

抓住注释中最关键的一句话：**允许在 `BeanFactoryPostProcessor` 之前注册其他的 `BeanDefinition`** ，这个才是重中之重！这句话想表达的 **`BeanDefinitionRegistryPostProcessor` 的执行时机比 `BeanFactoryPostProcessor` 更早**，`BeanFactoryPostProcessor` 一般只用来修改、扩展 `BeanDefinition` 中的信息，而 `BeanDefinitionRegistryPostProcessor` 则可以在 `BeanFactoryPostProcessor` 处理 `BeanDefinition` 之前，向 `BeanFactory` 注册新的 `BeanDefinition` ，甚至注册新的 `BeanFactoryPostProcessor` 用于下一个阶段的回调。

这段话干说可能很难理解，我们来借助一张图理解：

![img](《从0开始深入学习Spring》/9b370e8939e145a49f39bba93525977a~tplv-k3u1fbpfcp-zoom-1.image)

这样就好理解多了吧！不过实际执行的机制跟上面的图还有一点点小差别：由于实现了 `BeanDefinitionRegistryPostProcessor` 的类同时也实现了 `BeanFactoryPostProcessor` 的 `postProcessBeanFactory` 方法，所以在执行完所有 `BeanDefinitionRegistryPostProcessor` 的接口方法后，会**立即执行**这些类的 `postProcessBeanFactory` 方法，之后才是执行那些普通的只实现了 `BeanFactoryPostProcessor` 的 `postProcessBeanFactory` 方法。

> （简单概括：扩展接口的优先执行机制）

### 3.2 【面试题】面试中如何概述BeanDefinitionRegistryPostProcessor

以下答案仅供参考，可根据自己的理解调整回答内容：

**`BeanDefinitionRegistryPostProcessor` 是容器的扩展点，它用于 IOC 容器的生命周期中，所有 `BeanDefinition` 都准备好，即将加载到 `BeanFactory` 时回调触发，用于给 `BeanFactory` 中添加新的 `BeanDefinition` 。`BeanDefinitionRegistryPostProcessor` 也是容器隔离的，不同容器中的 `BeanDefinitionRegistryPostProcessor` 不会相互起作用。**

关键回答点：**注册新的 Bean 的定义信息**

## 4. BeanDefinitionRegistryPostProcessor的使用【熟悉】

下面咱也来实际使用一下 `BeanDefinitionRegistryPostProcessor` ，来体会它是如何向 `BeanFactory` 中注册新的 `BeanDefinition` 。

同样也是先说下需求：有一个 `Animal` 的抽象动物类，两个具体的动物类 `Cat` 和 `Dog` 。一开始 IOC 容器中只注册 `Cat` ，没有 `Dog` ，使用 `BeanDefinitionRegistryPostProcessor` 注册一个 `Dog` 的对象，然后利用 `BeanFactoryPostProcessor` 给所有的 `Animal` 对象的属性赋值。

> 本小节源码位置：`com.linkedbear.spring.postprocessor.i_registryprocessor`

### 4.1 声明bean

先把抽象类 `Animal` 搞出来吧，这次不需要再搞 `Person` 的依赖了，只定义 name 属性就好啦：

```java
public abstract class Animal {
    
    protected String name;
    
    public String getName() {
        return name;
    }
    
    public void setName(String name) {
        this.name = name;
    }
}
```

然后是 `Cat` 和 `Dog` ，只需要继承 `Animal` 就完事了：（记得给 `Cat` 上标注 `@Component` ，`Dog` 不标）

```java
@Component
public class Cat extends Animal {
    
    @Override
    public String toString() {
        return "Cat{" + "name='" + name + '\'' + "}";
    }
}
public class Dog extends Animal {
    
    @Override
    public String toString() {
        return "Dog{" + "name='" + name + '\'' + '}';
    }
}
```

### 4.2 编写后置处理器

上面的需求中，我们说的是注册 `Dog` ，以及给所有的 `Animal` 赋属性值，咱把这两个职责分开：

注册 `Dog` 的后置处理器：

```java
@Component
public class DogRegisterPostProcessor implements BeanDefinitionRegistryPostProcessor {
    
    @Override
    public void postProcessBeanDefinitionRegistry(BeanDefinitionRegistry registry) throws BeansException {
        if (!registry.containsBeanDefinition("dog")) {
            // 构造BeanDefinition，并注册进BeanFactory
            BeanDefinition dogDefinition = BeanDefinitionBuilder.genericBeanDefinition(Dog.class).getBeanDefinition();
            registry.registerBeanDefinition("dog", dogDefinition);
        }
    }
    
    @Override
    public void postProcessBeanFactory(ConfigurableListableBeanFactory beanFactory) throws BeansException {
    }
}
```

给 `Animal` 赋属性值的后置处理器：

```java
@Component
public class AnimalNameSetterPostProcessor implements BeanFactoryPostProcessor {
    
    @Override
    public void postProcessBeanFactory(ConfigurableListableBeanFactory beanFactory) throws BeansException {
        String[] animalNames = beanFactory.getBeanNamesForType(Animal.class);
        Stream.of(animalNames).forEach(name -> {
            BeanDefinition beanDefinition = beanFactory.getBeanDefinition(name);
            beanDefinition.getPropertyValues().add("name", name);
        });
    }
}
```

### 4.3 测试运行

编写测试类，使用包扫描驱动 IOC 容器，并从 IOC 容器中取出 Cat 和 Dog ：

```java
public class RegistryPostProcessorApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
                "com.linkedbear.spring.postprocessor.i_registryprocessor");
        Cat cat = ctx.getBean(Cat.class);
        System.out.println(cat);
        Dog dog = ctx.getBean(Dog.class);
        System.out.println(dog);
    }
}
```

运行 `main` 方法，控制台可以打印出 cat 和 dog 的信息：

```
Cat{name='cat'}
Dog{name='dog'}
```

### 4.4 运行时机分析

两个后置处理器都成功运行了，但是 `DogRegisterPostProcessor` 和 `AnimalNameSetterPostProcessor` 两个后置处理器的 `postProcessBeanFactory` 方法是谁先执行的呢？是有指定的顺序吗，还是 SpringFramework 底层已经确定好了顺序呢？

给两个后置处理器的所有方法都打上控制台输出，就像这样：

```java
    @Override
    public void postProcessBeanDefinitionRegistry(BeanDefinitionRegistry registry) throws BeansException {
        System.out.println("DogRegisterPostProcessor postProcessBeanDefinitionRegistry run ......");
        // ......
    }
    
    @Override
    public void postProcessBeanFactory(ConfigurableListableBeanFactory beanFactory) throws BeansException {
        System.out.println("DogRegisterPostProcessor postProcessBeanFactory run ......");
    }
```

重新运行 `main` 方法，控制台打印出来的顺序如下：

```
DogRegisterPostProcessor postProcessBeanDefinitionRegistry run ......
DogRegisterPostProcessor postProcessBeanFactory run ......
AnimalNameSetterPostProcessor postProcessBeanFactory run ......
Cat{name='cat'}
Dog{name='dog'}
```

由此可得出结论（就是前面在 3.1 章节说到的）：**`BeanDefinitionRegistryPostProcessor` 的 `postProcessBeanDefinitionRegistry` 执行完毕后，会先执行它们的 `postProcessBeanFactory` ，然后才能轮到普通的 `BeanFactoryPostProcessor` 执行**。

### 4.5 注册BeanFactoryPostProcessor

像前面概述中说的那样，`BeanDefinitionRegistryPostProcessor` 还可以在 `postProcessBeanDefinitionRegistry` 方法中，动态的注册 `BeanFactoryPostProcessor` 以支持下面马上要触发的 `postProcessBeanFactory` 阶段回调，我们也可以来试着搞一下。

把 `AnimalNameSetterPostProcessor` 的 `@Component` 注解去掉，并编写一个新的后置处理器：

```java
@Component
public class AnimalProcessorRegisterPostProcessor implements BeanDefinitionRegistryPostProcessor {
    
    @Override
    public void postProcessBeanDefinitionRegistry(BeanDefinitionRegistry registry) throws BeansException {
        registry.registerBeanDefinition("animalNameSetterPostProcessor", 
                new RootBeanDefinition(AnimalNameSetterPostProcessor.class));
    }
    
    @Override
    public void postProcessBeanFactory(ConfigurableListableBeanFactory beanFactory) throws BeansException {
    
    }
}
```

重新运行 `main` 方法，发现运行效果与前面一致，特性得以验证。

## 5. 【面试题】三种后置处理器的对比

|              | BeanPostProcessor                           | BeanFactoryPostProcessor                                     | BeanDefinitionRegistryPostProcessor                          |
| ------------ | ------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 处理目标     | bean 实例                                   | `BeanDefinition`                                             | `BeanDefinition` 、`.class` 文件等                           |
| 执行时机     | bean 的初始化阶段前后（已创建出 bean 对象） | `BeanDefinition` 解析完毕并注册进 `BeanFactory` 之后（此时 bean 未实例化） | 配置文件、配置类已解析完毕并注册进 `BeanFactory` ，但还没有被 `BeanFactoryPostProcessor` 处理 |
| 可操作的空间 | 给 bean 的属性赋值、创建代理对象等          | 给 `BeanDefinition` 中增删属性、移除 `BeanDefinition` 等     | 向 `BeanFactory` 中注册新的 `BeanDefinition`                 |

## 小结与练习

1. 什么是 `BeanFactoryPostProcessor` ？它与 `BeanPostProcessor` 有什么不同？
2. `BeanFactoryPostProcessor` 与 `BeanDefinitionRegistryPostProcessor` 又有什么不同？
3. 在上一章的自编案例之上，加入 `BeanFactoryPostProcessor` 与 `BeanDefinitionRegistryPostProcessor` ，进一步体会后置处理器之间的配合和协作。

【到此为止，后置处理器的部分结束，小伙伴是不是有一种感觉：这一层一层的演进，越来越像**编程式**注册 Bean 了。的确如此，我们平时开发时用的声明式配置，底层的支持就是编程式配置，我们现在深入了底层，也就应该学习一点编程式配置和驱动的知识。下一章，我们就来大概的学习如何编程式驱动 IOC 】

# 29. IOC高级-Java编程式驱动IOC

前面几章，我们把后置处理器的类型都学习了，小伙伴们应该对这种编程式的写法有一种比较强的感觉了。这一章，咱来学习如何使用纯编程式的写法，驱动 IOC 容器，来实现前面的配置式 / 声明式的功能。

可能有一些已经在实际工作或项目开发中用过 SpringFramework 的小伙伴会提出一个疑惑：**既然声明式 / 配置式的 Spring 已经这么好用了，为什么还要搞编程式驱动的 IOC 呢？**对于这个问题，见仁见智，作者目前能给出这样几个回答，看小伙伴是否能理解或者接受：

- 亲身接触编程式的 IOC 有助于理解 Spring 在底层对声明式 / 配置式的处理
- SpringBoot 的底层原理，就是利用了原生 SpringFramework 的编程式驱动的 IOC
- 项目开发组如果要基于 Spring 等框架二次封装，可能会利用到编程式驱动的 IOC

so ，作者表达的意思是，编程式驱动的 IOC 一般不会在日常开发中出现，而是在你深入了解 Spring 或者想深度挖掘 Spring 时起到比较大的作用。既然小册是带小伙伴深入学习，那这个深入是必须要入的 ~

本章的内容不会涉及理论，全部都是代码实操，小伙伴可以跟着小册的示例代码写一遍，有一个整体的印象就好。

> 本章源码均在 `com.linkedbear.spring.programmatic`

## 1. 快速上手编程式驱动IOC【熟悉】

先来一个最简单的需求吧：**不使用任何配置类 / 配置文件，向 IOC 容器注册一个 Person 对象，并注入属性值。**

下面我们开始写。

### 1.1 声明bean

先把 `Person` 类声明出来：

```java
public class Person {
    
    private String name;
    
    // getter  setter  toString
}
```

接下来本章后面的几个需求，也会利用到这个 Person ，后面就不再重复声明了。

### 1.2 编写启动类

这次没有配置类，没有配置文件，全靠启动类一把梭。

先把骨架写出来：

```java
public class ProgrammaticQuickstartApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext();
        
        Person person = ctx.getBean(Person.class);
        System.out.println(person);
    }
}
```

由于没有配置类、没有配置文件，所以这里只需要创建一个空的 `ApplicationContext` 即可。

然后，向 IOC 容器中注册一个 `Person` ，参照之前学过的内容，应该可以想到是加载 `BeanDefinition` 吧！所以，我们可以在这里用 `BeanDefinitionBuilder` 构建一个最简单的 `Person` 类型的定义信息，然后注册进 `ApplicationContext` 中：

```java
public static void main(String[] args) throws Exception {
    AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext();
    BeanDefinition personDefinition = BeanDefinitionBuilder.rootBeanDefinition(Person.class).getBeanDefinition();
    ctx.registerBeanDefinition("person", personDefinition);
    
    Person person = ctx.getBean(Person.class);
    System.out.println(person);
}
```

> 注意此处的 `registerBeanDefinition` 方法来自于 `BeanDefinitionRegistry` ，所以用 `ApplicationContext` 或者 `ConfigurableApplicationContext` 接口是拿不到的，只有用实现类，或者强转才可以。

### 1.3 运行失败及原因分析

运行 `main` 方法，控制台会抛出异常：

```
Exception in thread "main" java.lang.IllegalStateException: org.springframework.context.annotation.AnnotationConfigApplicationContext@728938a9 has not been refreshed yet
```

划重点：**has not been refreshed yet**，代表 `ApplicationContext` 还没有被 **refresh** ，无法使用。

早在 15 章中，我们就接触了 `refresh` 方法的重要，而这些 `ApplicationContext` 的落地实现中，如果没有预先传入配置文件 / 配置类 / 包扫描路径，则必须**手动调用 `refresh()` 方法来初始化 `ApplicationContext`** ，这里面的玄机我们可以简单的看一下源码中，`AnnotationConfigApplicationContext` 的构造方法：

```java
public AnnotationConfigApplicationContext() {
    this.reader = new AnnotatedBeanDefinitionReader(this);
    this.scanner = new ClassPathBeanDefinitionScanner(this);
}

public AnnotationConfigApplicationContext(Class<?>... componentClasses) {
    this();
    register(componentClasses);
    refresh();
}
```

看到了吧，只要传入了配置类，这里会帮我们 `refresh` ，所以我们就可以直接拿来用。

### 1.4 手动refresh后测试

在注册 `BeanDefinition` 之后，调用 `ApplicationContext` 的 `refresh` 方法：

```java
public static void main(String[] args) throws Exception {
    AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext();

    BeanDefinition personDefinition = BeanDefinitionBuilder.rootBeanDefinition(Person.class).getBeanDefinition();
    ctx.registerBeanDefinition("person", personDefinition);
    ctx.refresh();

    Person person = ctx.getBean(Person.class);
    System.out.println(person);
}
```

重新运行 `main` 方法，控制台可以打印出 `Person` 的信息，说明这次 `ApplicationContext` 已经能加载出手动构造的 `BeanDefinition` 了：

```
Person{name='null'}
```

### 1.5 给Person的属性赋值

前面第 24 章 1.3 节，介绍 `BeanDefinition` 的结构时，我们就知道属性变量值的封装是在一组 `PropertyValues` 中，so 在这里，我们构造 BeanDefinition 时，就可以顺便把属性值也设置好：

```java
    BeanDefinition personDefinition = BeanDefinitionBuilder.rootBeanDefinition(Person.class)
            .addPropertyValue("name", "zhangsan").getBeanDefinition();
    ctx.registerBeanDefinition("person", personDefinition);
```

重新运行 `main` 方法，可以发现 name 属性已经被成功设置了：

```
Person{name='zhangsan'}
```

## 2. 编程式依赖注入与bean的初始化【熟悉】

编程式的依赖注入，需求也相对比较简单：**同时在 IOC 容器中注册 `Person` 和两个 `Animal` 的子类对象 `Cat` 和 `Dog` ，并且 `Cat` 和 `Dog` 都依赖 `Person` 。**

下面开始演示。

### 2.1 声明bean

`Person` 我们就不重复声明了，只把 `Person` 和它的子类造出来就好：

```java
public abstract class Animal {
    
    protected String name;
    
    protected Person person;
    
    // getter setter toString
}
public class Cat extends Animal {
    
    @Override
    public String toString() {
        return "Cat{" + "name='" + name + '\'' + ", person=" + person + '}';
    }
}
public class Dog extends Animal {
    
    @Override
    public String toString() {
        return "Dog{" + "name='" + name + '\'' + ", person=" + person + '}';
    }
}
```

也是很简单的写法了吧，前面我们也写过不少次了。

### 2.2 编写启动类

来吧，直接起一个新的主启动类，把骨架写好：

```java
public class ProgrammaticInjectApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext();
        
        ctx.refresh();
        Cat cat = ctx.getBean(Cat.class);
        System.out.println(cat);
    }
}
```

这次长记性了，先把 `refresh` 方法调用了再说，其余的编程式代码都写到 `refresh` 上面。

这次要构造依赖注入的效果，根据之前在 xml 配置文件中的定义，转换过来就应该是构造两个 `BeanDefinition` 才是，于是就可以这样来写：

```java
    BeanDefinition personDefinition = BeanDefinitionBuilder.rootBeanDefinition(Person.class)
            .addPropertyValue("name", "老王").getBeanDefinition();
    ctx.registerBeanDefinition("laowang", personDefinition);
    
    BeanDefinition catDefinition = BeanDefinitionBuilder.rootBeanDefinition(Cat.class)
            .addPropertyValue("name", "咪咪").addPropertyReference("person", "laowang")
            .getBeanDefinition();
    ctx.registerBeanDefinition("mimi", catDefinition);
```

注意，依赖注入的对象引用，在 xml 配置文件中用 **ref** 属性，此处也是用对应的 property reference 来设置（有木有发现操作的套路完全一致呢）。这样写完之后，我们来运行 `main` 方法，控制台能打印 `Cat` 中注入了 `Person` 的对象：

```
Cat{name='咪咪', person=Person{name='老王'}}
```

### 2.3 bean的初始化时机探究

如果这一小节仅仅是玩这么点东西，那也太没意思了。我们来看看这些通过编程式驱动的 bean 都是什么时候初始化出来的呢？

#### 2.3.1 refresh触发bean的实例化

在 `Animal` 中声明默认的无参构造方法，并添加控制台的打印：

```java
public abstract class Animal {
    
    public Animal() {
        System.out.println("Animal constructor run ......");
    }
```

然后，在测试启动类的 `main` 方法，`refresh()` 方法调用之后也添加控制台打印：

```java
    // ......
    ctx.refresh();
    System.out.println("ApplicationContext refreshed ......");
    // ......
```

重新运行 `main` 方法，发现 `Animal` 的实例化动作发生在 `main` 方法控制台打印之前：

```
Animal constructor run ......
ApplicationContext refreshed ......
Cat{name='咪咪', person=Person{name='老王'}}
```

由此可以得出：**`refresh` 方法会触发 bean 的实例化。**

#### 2.3.2 原型bean呢

上面的结论是否是准确的呢？刚才可只是测了单实例 bean 而已吧，我们可以把 `Dog` 也声明出来看一看：（此处声明 `Dog` 为**原型 bean** ）

```java
    BeanDefinition dogDefinition = BeanDefinitionBuilder.rootBeanDefinition(Dog.class)
            .addPropertyValue("name", "汪汪").addPropertyReference("person", "laowang")
            .setScope(ConfigurableBeanFactory.SCOPE_PROTOTYPE).getBeanDefinition();
    ctx.registerBeanDefinition("wangwang", dogDefinition);
```

之后同样的，在下面获取一下 `Dog` ：

```java
    Dog dog = ctx.getBean(Dog.class);
    System.out.println(dog);
```

重新运行 `main` 方法，发现原型 bean 并没有在 `refresh` 之前创建对象，所以刚才的结论要改一下了：**`refresh` 方法会触发单实例 bean 的实例化。**

```
Animal constructor run ......
ApplicationContext refreshed ......
Cat{name='咪咪', person=Person{name='老王'}}
Animal constructor run ......
Dog{name='汪汪', person=Person{name='老王'}}
```

#### 2.3.3 延迟加载的bean呢

除了这两者，还有一种特殊情况是 bean 被设置为 `lazy-init` 的延迟加载 bean ，它又会是什么情况呢？

我们把上面 `Dog` 的 `BeanDefinition` 构造中，`scope` 还原回单实例，并设置它是 `lazy-init` 的：

```java
    BeanDefinition dogDefinition = BeanDefinitionBuilder.rootBeanDefinition(Dog.class)
            .addPropertyValue("name", "汪汪").addPropertyReference("person", "laowang")
            // .setScope(ConfigurableBeanFactory.SCOPE_PROTOTYPE)
            .setLazyInit(true)
            .getBeanDefinition();
```

重新运行 `main` 方法，发现 `Dog` 的初始化仍然发生在 `refresh` 之后，so 结论又要改了，当然这次总结出来的可就对了：

**`refresh` 方法的执行，会触发非延迟加载的单实例 bean 的实例化和初始化。**

## 3. 内置组件的使用【熟悉】

内置组件，主要包含 `ApplicationContext` 中组合的一些关键的 API （包括扫描器、加载器、解析器等），这一小节我们把它们都拿出来用一用。

### 3.1 借助包扫描

这一小节的需求：**不主动声明 `BeanDefinition` ，把上一小节的 Cat 和 Dog注册进 IOC 容器。**

既然不能主动声明 `BeanDefinition` 了，那就没有办法直接取到 `Cat` 和 `Dog` 了，只能通过其他的手段来实现了。这里比较好的办法是通过包扫描器来辅助我们拿到 `Cat` 和 `Dog` 。

在 SpringFramework 中，有专门的类路径下的包扫描器叫 `ClassPathBeanDefinitionScanner` ，它可以指定一个根包，来扫描路径下的所有指定匹配规则的类。这个话说的很干，小伙伴跟着小册实战一下就会用啦。

#### 3.1.1 包扫描器的创建与规则设置

`ClassPathBeanDefinitionScanner` 在创建时，需要传入 `BeanDefinitionRegistry` ，而 `ApplicationContext` 的落地实现类都实现了 `BeanDefinitionRegistry` 接口，所以可以直接传入 `ApplicationContext` 本身：

```java
public static void main(String[] args) throws Exception {
    AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext();

    ClassPathBeanDefinitionScanner scanner = new ClassPathBeanDefinitionScanner(ctx);
```

然后，要给包扫描器设置过滤规则，既然要把 `Cat` 和 `Dog` 都扫进来，而它们的父类都是 `Animal` ，所以此处就可以添加这样的一个包含的过滤规则：

```java
    scanner.addIncludeFilter((metadataReader, metadataReaderFactory) -> {
        // getClassMetadata可以获取到扫描类的相关元信息，此处把Animal的子类都拿出来
        return metadataReader.getClassMetadata().getSuperClassName().equals(Animal.class.getName());
    });
```

这个 `TypeFilter` 还眼熟吗？第 19 章我们已经学习过了，现在再写起来是不是会轻松一些呢？

然后，要让包扫描器工作了吧，那扫描的动作不用猜也知道是 `scan()` 吧，刚好这个扫描器就有个 `scan()` 方法：

```java
    int count = scanner.scan("com.linkedbear.spring.programmatic.b_di.bean");
```

哎？等一下，它的返回值怎么是 **int** 类型的呢？是不是哪里出了问题？这个地方需要来解释一下了。

#### 3.1.2 包扫描的扫描动作对比

`ClassPathBeanDefinitionScanner` 的 `scan` 方法，在文档注释中有标注，它的返回值是 “number of beans registered” —— **注册进 IOC 容器的 bean 的数量**。所以我们可以得知，**使用 `scan` 方法后，匹配的类会直接被封装为 `BeanDefinition` ，注册进 IOC 容器**。

那有没有一个能返回 `BeanDefinition` 的方法，让我们自行注册呢？当然可以，`ClassPathBeanDefinitionScanner` 还提供了一个 `findCandidateComponents` 方法，该方法就会返回扫描匹配的 `BeanDefinition` 集合：

```java
public Set<BeanDefinition> findCandidateComponents(String basePackage);
```

那太好了啊，用这个方法，我们会拿到包扫描之后封装的 `BeanDefinition` 信息，但不会注册进 IOC 容器，这样就可以任我们处置了（我们还得给这些 bean 属性赋值和注入呢）。

给 bean 的注入，其实就是拿 `BeanDefinition` 进行一番操作罢了，不算麻烦，小伙伴们跟着写一遍就好啦：

```java
    Set<BeanDefinition> animalDefinitions = scanner
            .findCandidateComponents("com.linkedbear.spring.programmatic.b_di.bean");
    animalDefinitions.forEach(definition -> {
        MutablePropertyValues propertyValues = definition.getPropertyValues();
        String beanClassName = definition.getBeanClassName();
        propertyValues.addPropertyValue("name", beanClassName);
        // 设置依赖注入的引用，需要借助RuntimeBeanReference实现
        propertyValues.addPropertyValue("person", new RuntimeBeanReference("laowang"));
        ctx.registerBeanDefinition(Introspector.decapitalize(beanClassName.substring(beanClassName.lastIndexOf("."))), definition);
    });
```

最后，整个 IOC 容器刷新，获取。

#### 3.1.3 测试运行

整体的代码编写如下：

```java
public static void main(String[] args) throws Exception {
    AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext();

    BeanDefinition personDefinition = BeanDefinitionBuilder.rootBeanDefinition(Person.class)
            .addPropertyValue("name", "老王").getBeanDefinition();
    ctx.registerBeanDefinition("laowang", personDefinition);

    ClassPathBeanDefinitionScanner scanner = new ClassPathBeanDefinitionScanner(ctx);
    scanner.addIncludeFilter((metadataReader, metadataReaderFactory) -> {
        return metadataReader.getClassMetadata().getSuperClassName().equals(Animal.class.getName());
    });
    
    // int count = scanner.scan("com.linkedbear.spring.programmatic.b_di.bean");
    Set<BeanDefinition> animalDefinitions = scanner
            .findCandidateComponents("com.linkedbear.spring.programmatic.b_di.bean");
    animalDefinitions.forEach(definition -> {
        MutablePropertyValues propertyValues = definition.getPropertyValues();
        String beanClassName = definition.getBeanClassName();
        propertyValues.addPropertyValue("name", beanClassName);
        propertyValues.addPropertyValue("person", new RuntimeBeanReference("laowang"));
        ctx.registerBeanDefinition(Introspector.decapitalize(beanClassName.substring(beanClassName.lastIndexOf("."))), definition);
    });
    
    ctx.refresh();

    Cat cat = ctx.getBean(Cat.class);
    System.out.println(cat);
}
```

运行 `main` 方法，控制台可以打印出 `Cat` 的内容，说明借助包扫描已经可以实现这个需求了：

```
Animal constructor run ......
Animal constructor run ......
Cat{name='com.linkedbear.spring.programmatic.b_di.bean.Cat', person=Person{name='老王'}}
```

### 3.2 借助xml配置文件解析器

上面的 `Person` 还是自己声明的 `BeanDefinition` 构造，这次的需求要继续变更：**`Person` 声明在 xml 配置文件中，并编程式加载进 IOC 容器中**。

#### 3.2.1 编写xml配置文件

既然换用 xml 配置文件，那咱就先把配置文件搞出来：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="laowang" class="com.linkedbear.spring.programmatic.a_quickstart.bean.Person">
        <property name="name" value="老李"/>
    </bean>
</beans>
```

#### 3.2.2 xml配置文件解析器的使用

在 SpringFramework 中，负责 xml 配置文件解析的组件是 `XmlBeanDefinitionReader` ，它的构造也需要把 `BeanDefinitionRegistry` 传进去：

```java
    XmlBeanDefinitionReader reader = new XmlBeanDefinitionReader(ctx);
```

然后，只需要让它加载 xml 配置文件就好了：

```java
    reader.loadBeanDefinitions(new ClassPathResource("programmatic/programmatic-components.xml"));
```

注意，`XmlBeanDefinitionReader` 里面可没有加载 xml 配置文件后返回 `BeanDefinition` 的操作了，想一下为什么呢？

很简单，因为 xml 配置文件本身就属于完善了的配置式写法，里面定义 bean 的内容已经很全了，当然不需要再进行编程式干预咯。

#### 3.2.3 测试运行

把上面的这两行，替换掉 3.1.3 节中的 `personDefinition` 注册，并重新运行 `main` 方法，控制台仍然可以打印出 `Cat` 和组合的 `Person` ：

```java
Animal constructor run ......
Animal constructor run ......
Cat{name='com.linkedbear.spring.programmatic.b_di.bean.Cat', person=Person{name='老李'}}
```

差不多啦，编程式驱动的 IOC 就讲解这些吧，这些内容并不是全部的编程式驱动，只是想通过这些例子来告诉小伙伴们，一切通过声明式 / 配置式等快速简单的方式实现的工作，底层都是由编程式来支撑实现的，所以我们也可以直接使用编程式驱动来完成同样的功能。只不过，平时的开发中我们真的用不到它，但如果你的等级升得比较高，或者你参与了项目组的底层封装 / 二开，那这些技能可能会给你不小的帮助。

## 小结与练习

1. 编程式驱动 IOC 有什么特点？
2. 编程式驱动与声明式 / 配置式的关联是什么？
3. 自行设计一个场景和例子，体会和加深编程式驱动的效果吧。

【IOC 部分的高级知识也快差不多了，下一章我们来综合前面学过的进阶和高级知识，来做一个接近于实际的特殊功能：**模块装配 jdbc 驱动**】

# 30. IOC高级-模块装配&条件装配综合使用

上一章的最后，我们说本章要搞一个模块装配的 jdbc ，其实这个内容可以放到 Dao 编程篇再讲，不过趁热打铁吧，既然学了前面不少的知识，正好综合的使用一下。

本章内容倾向于编码实战，当然也有新的知识点讲解，小伙伴要跟着小册好好练习哦。

## 1. 需求与分析

先说一下需求吧：**使用模块装配，通过标注一个 `@EnableJdbc` 的注解，能够根据当前工程中导入的数据库连接驱动，注册对应的数据源到 IOC 容器。**

咱把这个需求分解一下，可以提取出来的点应该有这么几个：

- 自定义注解与模块装配
- 条件装配注册特定数据库驱动的数据库连接池（数据源）
- 外部化配置数据源的连接信息

还好，基本都是之前在进阶部分学过的内容了，那咱就开始写吧。

## 2. 第一版写法

> 本小节源码位置：`com.linkedbear.spring.configuration.d_enablejdbc`

需求中提到了 jdbc 、数据源等有关数据库的依赖，所以首先我们要把缺少的依赖导入工程中。

### 2.1 添加pom依赖

我们先用 MySQL 来测试效果，此处导入 MySQL 的驱动、Druid 的数据库连接池、DBUtils 简化数据库访问的依赖。

```xml
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <version>5.1.47</version>
</dependency>

<dependency>
    <groupId>com.alibaba</groupId>
    <artifactId>druid</artifactId>
    <version>1.1.23</version>
</dependency>

<dependency>
    <groupId>commons-dbutils</groupId>
    <artifactId>commons-dbutils</artifactId>
    <version>1.7</version>
</dependency>
```

### 2.2 声明模块装配的注解

既然是模块装配打头，那注解是必然要有的，接下来我们把注解声明出来：

```java
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.TYPE)
@Import(JdbcConfiguration.class)
public @interface EnableJdbc {
    
}
```

模块装配要配合 `@Import` 注解一起使用，此处我们可以使用 `@Import` 导入一个注册数据源的配置类，在配置类中完成注册数据源、加载连接池配置等工作。

### 2.3 编写配置类

配置类中，需要构造一个 `DataSource` 和 `QueryRunner` ，就像这样：

```java
@Configuration
public class JdbcConfiguration {
    
    @Bean
    public DataSource dataSource() {
        DruidDataSource dataSource = new DruidDataSource();
        dataSource.setDriverClassName("com.mysql.jdbc.Driver");
        dataSource.setUrl("jdbc:mysql://localhost:3306/test?characterEncoding=utf8");
        dataSource.setUsername("root");
        dataSource.setPassword("123456");
        return dataSource;
    }
    
    @Bean
    public QueryRunner queryRunner(DataSource dataSource) {
        return new QueryRunner(dataSource);
    }
}
```

这个写法有够简单了吧，不过这样写仅仅是装配了 MySQL 的，如果要支持 Oracle 、H2 的数据库，就还需要创建另外两个 `DataSource` 。（另外两个 `DataSource` 的声明几乎完全一致，小册不在此列出）

### 2.4 加入条件装配

如果是一次性把这三个 `DataSource` 都写到 `JdbcConfiguration` 中，那每次 IOC 容器初始化时，都会创建三个 `DataSource` ，这很明显不符合要求，我们要的是工程的 classpath 下有哪个数据库连接驱动，就装配哪个 `DataSource` ，很明显这里要用到条件装配了。又因为获取数据库连接驱动的方式无法通过 Profiles 决定，所以只能选用 Conditional 的方式。

可问题是：怎么知道 classpath 下是不是有指定的数据库连接驱动呢？

哎，很简单嘛，用类加载器加载一下，如果成功了，那就是有；如果报 `ClassNotFoundException` 了，那就代表没有。所以我们可以写一个类似于这样的简单判断：（忘记的小伙伴要回过头去看第 18 章哦）

```java
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target({ElementType.TYPE, ElementType.METHOD})
@Conditional(OnClassNameConditional.class)
public @interface ConditionalOnClassName {
    
    String value();
}
public class OnClassNameConditional implements Condition {
    
    @Override
    public boolean matches(ConditionContext context, AnnotatedTypeMetadata metadata) {
        String className = (String) metadata.getAnnotationAttributes(ConditionalOnClassName.class.getName()).get("value");
        try {
            Class.forName(className);
            return true;
        } catch (ClassNotFoundException e) {
        	return false;
        }
    }
}
```

一个自定义 Conditional 的注解，一个支撑注解的条件逻辑类，这样就可以搞定了。

然后，在 `JdbcConfiguration` 中，给每个 `DataSource` 的注册上都标注上 `@ConditionalOnClassName` 注解，这样就可以搞定条件装配了：

```java
@Bean
@ConditionalOnClassName("com.mysql.jdbc.Driver")
public DataSource mysqlDataSource() {
    DruidDataSource dataSource = new DruidDataSource();
    dataSource.setDriverClassName("com.mysql.jdbc.Driver");
    dataSource.setUrl("jdbc:mysql://localhost:3306/test?characterEncoding=utf8");
    dataSource.setUsername("root");
    dataSource.setPassword("123456");
    return dataSource;
}
```

### 2.5 测试运行

这次的测试启动类，我也拿它当配置类用了，其实这完全没问题的，只是之前的示例代码中我都没这么干而已：

```java
@Configuration
@EnableJdbc
public class EnableJdbcApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(EnableJdbcApplication.class);
        DruidDataSource dataSource = ctx.getBean(DruidDataSource.class);
        System.out.println(dataSource.getUrl());
    }
}
```

这里的操作很简单，在测试启动类上标注 `@EnableJdbc` ，并用它自己驱动 IOC 容器，然后从容器中取出 `DataSource` ，打印它的 url 。

运行 `main` 方法，控制台可以打印出 MySQL 的数据库连接地址：

```
jdbc:mysql://localhost:3306/test?characterEncoding=utf8
```

将 `pom.xml` 中的数据库连接驱动换为 h2 的依赖：

```xml
<dependency>
    <groupId>com.h2database</groupId>
    <artifactId>h2</artifactId>
    <version>1.4.199</version>
</dependency>
```

不改动任何程序代码，直接重新运行 `main` 方法，控制台也能立马切换为 h2 的数据库连接地址，至此第一版代码编写完成。

```
jdbc:h2:~/test
```

### 2.6 第一版代码的问题

回过头来看一看，第一版代码有什么问题呢？

- **外部化配置**呢？所有的配置都是写死在配置类的呀，这不大合理吧
- 虽说把多个 `DataSource` 放在一个配置类中注册，但如果随后一些其它的组件也多起来，那这个 `JdbcConfiguration` 只会越来越庞大，最好能够**把不同数据库的组件都分散到不同的配置类中**

基于这两个问题，我们要对现在的代码改进。

## 3. 第二版写法

先从外部化配置改起吧，要实现外部化配置的效果，我们也知道，是要把外置的配置文件引入到 IOC 容器的 `Environment` 中。下面咱就来搞定这个。

> 本小节源码位置：`com.linkedbear.spring.configuration.e_enablejdbc`

### 3.1 声明jdbc配置文件

在工程的 `resources` 下新建一个 `enablejdbc` 包，随后创建一个 `jdbc.properties` 文件：

```properties
jdbc.url=jdbc:mysql://localhost:3306/test?characterEncoding=utf8
jdbc.username=root
jdbc.password=123456
```

哎，这里为啥没有 `jdbc.driverClassName` 呢？小伙伴们思考一下原因？

看一眼上面的配置类，针对不同的条件装配中，`driverClassName` 已经被固定住了，所以我们也没必要再在配置文件中写了（突然感觉省了点事哈）。

### 3.2 配置类注入Environment

用 `EnvironmentAware` 给 `JdbcConfiguration` 注入 `Environment` ，然后每个 `DataSource` 的创建就可以使用 `Environment` 的取值了：

```java
@Bean
@ConditionalOnClassName("com.mysql.jdbc.Driver")
public DataSource mysqlDataSource() {
    DruidDataSource dataSource = new DruidDataSource();
    dataSource.setDriverClassName("com.mysql.jdbc.Driver");
    dataSource.setUrl(environment.getProperty("jdbc.url"));
    dataSource.setUsername(environment.getProperty("jdbc.username"));
    dataSource.setPassword(environment.getProperty("jdbc.password"));
    return dataSource;
}
```

如果小伙伴是跟着小册一起写的话，有木有突然感觉到很奇怪很难受：MySQL 的数据源这么写，Oracle 和 H2 的也是一模一样的写法啊，这也太奇怪了吧，有木有更好地办法呢？这个问题先放一下，我们后面马上改进。

### 3.3 拆分配置类

三个 `DataSource` 放在一起虽说可以，但终究还是拆开合适，于是我们就可以这样拆成三个配置类：

```java
@Configuration
@ConditionalOnClassName("com.mysql.jdbc.Driver")
public class MySQLJdbcConfiguration extends AbstractJdbcConfiguration {
    
    @Bean
    public DataSource dataSource() {
        DruidDataSource dataSource = new DruidDataSource();
        dataSource.setDriverClassName("com.mysql.jdbc.Driver");
        dataSource.setUrl(environment.getProperty("jdbc.url"));
        dataSource.setUsername(environment.getProperty("jdbc.username"));
        dataSource.setPassword(environment.getProperty("jdbc.password"));
        return dataSource;
    }
}
```

> 注意：这里我把 `JdbcConfiguration` 类改名为 `AbstractJdbcConfiguration` 了，这样我只需要写一次 `Environment` 的注入就可以。

拆开三个配置类后，下一步要考虑的是咋把这些配置类注册进 IOC 容器。最简单的办法是包扫描，但包扫描不见得是最好的办法：如果恰巧 Oracle 库出了点问题，这个类暂时不想装配进去了，使用包扫描的话只能把 `OracleJdbcConfiguration` 删掉或者改源码去掉 `@Configuration` 注解，才能停用 Oracle 的配置类装配。so ，**有没有一种更好的方案，能针对某个模块的装配，利用外部化配置指定需要加载的配置类呢？** 当然有（没有那我故弄玄虚干嘛），这个知识点非常重要，它就是 **SPI** 。

## 4. SPI【掌握】

说到 SPI ，其实最早它的用法是来源于 jdk ，下面先介绍关于 SPI 的一些基础。

### 4.1 SPI概述与由来

关于 SPI 的来源，得从面向对象的接口编程说起。依赖倒转原则中提到，**应该依赖接口而不是实现类**，但接口最终要有实现类落地。如果程序因为业务调整，需要替换某个接口的实现类，那就不得不改动实现类的创建，也就是得改源码了。SPI 的出现解决了这个问题，它通过一种“**服务寻找**”的机制，**动态的加载接口 / 抽象类对应的具体实现类**。

是不是突然产生了一种 IOC 的感觉？对的，SPI 还真有点 IOC 的味，**它把接口具体实现类的定义和声明权交给了外部化的配置文件中**。

可能有些小伙伴到这里还是有点迷，没有关系，表情包助你理解 SPI ：

![img](《从0开始深入学习Spring》/ea52816334e24114b362e16609b31352~tplv-k3u1fbpfcp-zoom-1.image)

是不是好理解多了？一个接口可以有多个实现类，通过 SPI 机制，可以将一个接口需要创建的实现类的对象都罗列在一个特殊的文件中，SPI 机制会将这些实现类都实例化出对象并返回。

好了，下面解释下 SPI 的概念吧。SPI 全程叫 **Service Provider Interface** 服务提供接口，它可以通过一个指定的接口 / 抽象类，寻找到预先配置好的实现类（并创建实现类对象）。jdk1.6 中有 SPI 的具体实现，SpringFramework 3.2 也引入了 SPI 的实现，而且比 jdk 的实现更加强大，下面我们分别来讲解这两种 SPI 的实现。

### 4.2 jdk1.6中的SPI

对于原生 jdk 的 SPI ，我们只是了解下就好，因为它的使用范围实在是有点有限，只能通过**接口 / 抽象类**来加载具体的实现类，所以很多框架都没有直接用 jdk 的 SPI ，基本都是自己造了一套更强大的（ Spring 算一个，Dubbo 算一个，等等吧）。下面来一个最简单的示例来讲解 jdk 原生的 SPI 。

> 本小节源码位置：`com.linkedbear.spring.configuration.z_spi`

#### 4.2.1 声明接口和实现类

不整那么复杂的，一个接口两个实现类就好吧！这样，我们直接拿 IOC 一开始的 DemoDao 用吧：

```java
public interface DemoDao {
    
}
public class DemoMySQLDaoImpl implements DemoDao {
    
}
public class DemoOracleDaoImpl implements DemoDao {
    
}
```

> 方法都懒得定义了咯，只通过类名也能看出来区别就好吧。

#### 4.2.2 声明SPI文件

jdk 的 SPI 是需要遵循规范的：**所有定义的 SPI 文件都必须放在工程的 `META-INF/services` 目录下**，且**文件名必须命名为接口 / 抽象类的全限定名**，**文件内容为接口 / 抽象类的具体实现类的全限定名，如果出现多个具体实现类，则每行声明一个类的全限定名，没有分隔符**。

以下是针对上面 `DemoDao` 的定义：

> 文件名：**com.linkedbear.spring.configuration.z_spi.bean.DemoDao**

```
com.linkedbear.spring.configuration.z_spi.bean.DemoMySQLDaoImpl
com.linkedbear.spring.configuration.z_spi.bean.DemoOracleDaoImpl
```

是不是还挺简单的，没有想象中的那么难。（有些技术点就是这样，听着挺费劲，实际一写才知道原来简单的很，小伙伴们不要怂，冲就完事了）

#### 4.2.3 测试获取

编写测试启动类，使用 jdk 提供的一个 `ServiceLoader` 类来加载 SPI 文件中定义的实现类，并直接打印到控制台：

```java
public class JdkSpiApplication {
    
    public static void main(String[] args) throws Exception {
        ServiceLoader<DemoDao> serviceLoader = ServiceLoader.load(DemoDao.class);
        serviceLoader.iterator().forEachRemaining(dao -> {
            System.out.println(dao);
        });
    }
}
```

运行 `main` 方法，控制台可以打印出 `DemoDao` 的两个实现类的对象：

```
com.linkedbear.spring.configuration.z_spi.bean.DemoMySQLDaoImpl@6f496d9f
com.linkedbear.spring.configuration.z_spi.bean.DemoOracleDaoImpl@723279cf
```

这样就算搞定 jdk 原生的 SPI 了。

### 4.3 SpringFramework3.2中的SPI

SpringFramework 中的 SPI 相比较于 jdk 原生的，那可就高级多了，因为它不仅仅局限于接口 / 抽象类，它可以是**任何一个类、接口、注解**。也正是因为可以支持注解的 SPI ，这个特性在 SpringBoot 中被疯狂利用（大名鼎鼎的 **`@EnableAutoConfiguration`** ）。so 这个 Spring 的 SPI 我们更有必要来学习啦。

接口和实现类我们就不重复声明了，用上面的就 OK 。

#### 4.3.1 声明SPI文件

SpringFramework 的 SPI 文件也是有规矩的，它需要放在工程的 **`META-INF`** 下，且文件名必须为 **`spring.factories`** 。而文件的内容，其实就是一个 `properties` ：

```properties
com.linkedbear.spring.configuration.z_spi.bean.DemoDao=\
  com.linkedbear.spring.configuration.z_spi.bean.DemoMySQLDaoImpl,\
  com.linkedbear.spring.configuration.z_spi.bean.DemoOracleDaoImpl
```

#### 4.3.2 测试获取

使用 SpringFramework 的 SPI ，加载 `spring.factories` 文件的 API 是 **`SpringFactoriesLoader`** ，它不仅可以加载声明的类的对象，而且可以直接把预先定义好的全限定名都取出来：

```java
public class SpringSpiApplication {
    
    public static void main(String[] args) throws Exception {
        // 加载并实例化
        List<DemoDao> demoDaos = SpringFactoriesLoader
                .loadFactories(DemoDao.class, SpringSpiApplication.class.getClassLoader());
        demoDaos.forEach(dao -> {
            System.out.println(dao);
        });
    
        System.out.println("------------------------------------------------");
    
        // 只加载全限定类名
        List<String> daoClassNames = SpringFactoriesLoader
                .loadFactoryNames(DemoDao.class, SpringSpiApplication.class.getClassLoader());
        daoClassNames.forEach(className -> {
            System.out.println(className);
        });
    }
}
```

运行 `main` 方法，控制台也可以正常打印对象与全限定名：

```
com.linkedbear.spring.configuration.z_spi.bean.DemoMySQLDaoImpl@7506e922
com.linkedbear.spring.configuration.z_spi.bean.DemoOracleDaoImpl@4ee285c6
------------------------------------------------
com.linkedbear.spring.configuration.z_spi.bean.DemoMySQLDaoImpl
com.linkedbear.spring.configuration.z_spi.bean.DemoOracleDaoImpl
```

由于 SpringFramework 的 SPI 更为灵活，所以我们在这里就使用 SpringFramework 的 SPI 来加载配置类。

------

回到刚才的第二版写法中，我们使用 SPI 来搞定配置类的加载。

### 3.4 SPI加载配置类

先把几个配置类都声明到 `spring.factories` 中吧：

```properties
com.linkedbear.spring.configuration.e_enablejdbc.config.EnableJdbc=\
  com.linkedbear.spring.configuration.e_enablejdbc.config.MySQLJdbcConfiguration,\
  com.linkedbear.spring.configuration.e_enablejdbc.config.OracleJdbcConfiguration,\
  com.linkedbear.spring.configuration.e_enablejdbc.config.H2JdbcConfiguration
```

注意这里我使用了注解作为 key ，这是完全可以的哦。

然后就是加载它们了。由于**配置类需要 SpringFramework 解析其中的 Bean 的定义，以及其他的配置**，所以**不适合直接创建对象**，这里**获取全限定名**是合理的方式。

再回想一下，如果是加载一组类的全限定名，并且都要注册到 IOC 容器中，那么用谁会比较合适呢？哎，是不是有个东西叫 **`ImportSelector`** 来着？它刚好就是要一组类的全限定名！那我们快点来写吧：

```java
public class JdbcConfigSelector implements ImportSelector {
    
    @Override
    public String[] selectImports(AnnotationMetadata importingClassMetadata) {
        List<String> configClassNames = SpringFactoriesLoader
                .loadFactoryNames(EnableJdbc.class, this.getClass().getClassLoader());
        return configClassNames.toArray(new String[0]);
    }
}
```

之后，在 `@EnableJdbc` 注解上，把这个 `JdbcConfigSelector` 导入进去：

```java
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.TYPE)
@Import(JdbcConfigSelector.class)
public @interface EnableJdbc {
    
}
```

### 3.5 测试运行

第二版的测试运行类与前面几乎完全一致，只是不要忘记加载 `jdbc.properties` 的配置哦：

```java
@Configuration
@EnableJdbc
@PropertySource("enablejdbc/jdbc.properties")
public class EnableJdbcApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(EnableJdbcApplication.class);
        DruidDataSource dataSource = ctx.getBean(DruidDataSource.class);
        System.out.println(dataSource.getUrl());
    }
}
```

运行 `main` 方法，可以发现 MySQL 的驱动已经注册进去了：

```
jdbc:mysql://localhost:3306/test?characterEncoding=utf8
com.mysql.jdbc.Driver
```

切换 `pom.xml` 中的数据库驱动依赖，也能正常运行出来，说明编写一切都正确。

### 3.6 模块装配&条件装配的使用总结

到这里，小伙伴会不会对整体的模块装配+条件装配有一个更清晰的认识呢？通过一个注解，把一个功能所需要的组件都装配进 IOC 容器中，并且合理利用 SPI 配合条件装配，可以满足不同环境、不同外部配置的需求。

之所以讲这部分，是因为后续小伙伴在学习 SpringBoot 时，**SpringBoot 就完全利用了这个套路来实现自动装配**的。小伙伴可以先记住这个套路，到后面学习 SpringBoot 时，自然会 会心一笑 的。

------

到这里，模块装配&条件装配的内容就已经讲完了，不过小册要在这里加一个餐，把这个综合案例继续推演下去。

## 5. 回归理性的第三版写法

其实小伙伴在拆分配置类的时候，那种强烈的不适感有没有冲出头顶：

```java
@Bean
public DataSource dataSource() {
    DruidDataSource dataSource = new DruidDataSource();
    dataSource.setDriverClassName("com.mysql.jdbc.Driver");
    dataSource.setUrl(environment.getProperty("jdbc.url"));
    dataSource.setUsername(environment.getProperty("jdbc.username"));
    dataSource.setPassword(environment.getProperty("jdbc.password"));
    return dataSource;
}
@Bean
public DataSource dataSource() {
    DruidDataSource dataSource = new DruidDataSource();
    dataSource.setDriverClassName("oracle.jdbc.driver.OracleDriver");
    dataSource.setUrl(environment.getProperty("jdbc.url"));
    dataSource.setUsername(environment.getProperty("jdbc.username"));
    dataSource.setPassword(environment.getProperty("jdbc.password"));
    return dataSource;
}
```

试问，这两段代码，除了 `driverClassName` 不同，还有啥是不一样的吗？？？这很明显没必要这么写吧，**徒增功耗！！**

而且，根据之前学过的 `BeanDefinition` 与编程式驱动 IOC ，**这几个配置是不是完全可以转换为构造一个 `BeanDefinition` 啊**！好，有了这个思路，下面我们回归理性，用 `BeanDefinition` 的思维来重构这个案例。

> 本小节源码位置：`com.linkedbear.spring.configuration.f_enablejdbc`

### 5.1 编写BeanDefinitionRegistryPostProcessor

既然可以通过编程式注入 `BeanDefinition` ，那我们完全可以借助 `BeanDefinitionRegistryPostProcessor` ，或者 `ImportBeanDefinitionRegistrar` ，向 `BeanFactory` 中注入 `BeanDefinition` ，此处我们选用 `BeanDefinitionRegistryPostProcessor` 吧。

跟之前的 `@Bean` 声明一样的，是都需要 **`Environment`** ；不一样的，是构造 `BeanDefinition` 的方式，这里要用编程式了。还是老套路，要用 `EnvironmentAware` 的回调注入哦（**直接 `@Autowired` 是不可行的，小伙伴们可以自行测试一下**）：

```java
public class DataSourceRegisterPostProcessor implements BeanDefinitionRegistryPostProcessor, EnvironmentAware {
    
    private Environment environment;
    
    @Override
    public void postProcessBeanDefinitionRegistry(BeanDefinitionRegistry registry) throws BeansException {
        BeanDefinitionBuilder builder = BeanDefinitionBuilder.rootBeanDefinition(DruidDataSource.class)
                .addPropertyValue("url", environment.getProperty("jdbc.url"))
                .addPropertyValue("username", environment.getProperty("jdbc.username"))
                .addPropertyValue("password", environment.getProperty("jdbc.password"));
        // 完善driverClassName，注册DataSource
    }
    
    @Override
    public void postProcessBeanFactory(ConfigurableListableBeanFactory beanFactory) throws BeansException {
    }
    
    @Override
    public void setEnvironment(Environment environment) {
        this.environment = environment;
    }
}
```

剩下的就是怎么搞定 `driverClassName` 了。既然上面的三个配置类中，已经预先拿到了 `Driver` 的实现类，那这里我们也可以把它们声明到 SPI 文件中：

```properties
java.sql.Driver=\
  com.mysql.jdbc.Driver,\
  oracle.jdbc.driver.OracleDriver,\
  org.h2.Driver
```

然后借助 `SpringFactoriesLoader` ，就可以拿到这几个类的全限定名了。

拿到之后再怎么干，这就不用我再多说了吧，小伙伴们已经大脑飞速运行了吧！那么我们赶紧趁势一口气写完吧：

```java
@Override
public void postProcessBeanDefinitionRegistry(BeanDefinitionRegistry registry) throws BeansException {
    BeanDefinitionBuilder builder = BeanDefinitionBuilder.rootBeanDefinition(DruidDataSource.class)
            .addPropertyValue("url", environment.getProperty("jdbc.url"))
            .addPropertyValue("username", environment.getProperty("jdbc.username"))
            .addPropertyValue("password", environment.getProperty("jdbc.password"));
    // 根据当前classpath下的数据库连接驱动添加driverClassName
    List<String> driverClassNames = SpringFactoriesLoader.loadFactoryNames(Driver.class, this.getClass().getClassLoader());
    String driverClassName = null;
    for (String temp : driverClassNames) {
        try {
            Class.forName(temp);
            driverClassName = temp;
            break;
        } catch (ClassNotFoundException ignored) {
            // 加载失败，classpath下无当前驱动，继续下一个
        }
    }
    // 存在驱动，注册DataSource
    if (driverClassName != null) {
        builder.addPropertyValue("driverClassName", driverClassName);
        registry.registerBeanDefinition("dataSource", builder.getBeanDefinition());
    }
}
```

### 5.2 编写配置类

配置类中，只需要定义 `QueryRunner` ，以及把刚写的 `DataSourceRegisterPostProcessor` 注册到 IOC 容器就可以了，非常的简单：

```java
@Configuration
public class JdbcConfiguration {
    
    @Bean
    public QueryRunner queryRunner(DataSource dataSource) {
        return new QueryRunner(dataSource);
    }
    
    @Bean
    public DataSourceRegisterPostProcessor dataSourceRegisterPostProcessor() {
        return new DataSourceRegisterPostProcessor();
    }
}
```

另外，不要忘记给 `@EnableJdbc` 导入这个配置类哦：

```java
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.TYPE)
@Import(JdbcConfiguration.class)
public @interface EnableJdbc {
    
}
```

### 5.3 测试运行

与上面的测试运行类一模一样：

```java
@Configuration
@EnableJdbc
@PropertySource("enablejdbc/jdbc.properties")
public class EnableJdbcApplication {
    
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(EnableJdbcApplication.class);
        DruidDataSource dataSource = ctx.getBean(DruidDataSource.class);
        System.out.println(dataSource.getUrl());
        System.out.println(dataSource.getDriverClassName());
    }
}
```

运行 `main` 方法，控制台依然能正确打印 url 和 driverClassName ，证明重构成功。

至此，本案例完结。

## 小结与练习

1. 模块装配与条件装配如何能同时兼容多种场景的需求？
2. 如何理解 SPI ？jdk 原生的 SPI 与 Spring 的 SPI 有什么区别？
3. 完整的练习本章的案例，循序渐进的体会配置的演变与 SPI 的使用。

【到这里，装配的部分就算全部完结了。IOC 高级的最后一章，小册对事件机制作一些补充和高级知识的扩展，这部分主要以扩展为主，小伙伴们无需抱有比较大的压力学习】