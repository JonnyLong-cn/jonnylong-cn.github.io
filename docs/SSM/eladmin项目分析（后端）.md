# 项目结构

```text
- eladmin-common 公共模块
    - annotation 为系统自定义注解
    - aspect 自定义注解的切面
    - base 提供了Entity、DTO基类和mapstruct的通用mapper
    - config 自定义权限实现、redis配置、swagger配置、Rsa配置等
    - exception 项目统一异常的处理
    - utils 系统通用工具类
- eladmin-system 系统核心模块（系统启动入口）
	- config 配置跨域与静态资源，与数据权限
	    - thread 线程池相关
	- modules 系统相关模块(登录授权、系统监控、定时任务、运维管理等)
- eladmin-logging 系统日志模块
- eladmin-tools 系统第三方工具模块
- eladmin-generator 系统代码生成模块
```

# eladmin-common

## utils（工具）

### ElAdminConstant

定义了一些常量：

+ `REGION = "内网IP|内网IP";`
+ `WIN = "win";`
+ `MAC = "mac";`
+ `IP_URL = "http://whois.pconline.com.cn/ipJson.jsp?ip=%s&json=true";`

### EncryptUtils

加密工具，包括对称加密解密，md5加盐加密

+ `desEncrypt`：对称加密
+ `desDecrypt`：对称解密

```java
// 使用方法如下
import static me.zhengjie.utils.EncryptUtils.*;
@Test
public void test() {
    try {
        String s1 = desEncrypt("123456");
        System.out.println(s1);
        String s2 = desDecrypt(s1);
        System.out.println(s2);
    } catch (Exception e) {
        e.printStackTrace();
    }
}

/*************
7772841DC6099402
123456
*************/
```

### FileUtil

+ `getExtensionName`：获取扩展名
+ `getFileNameNoEx`：获取文件名
+ `getSize`：文件大小单位制
+ `inputStreamToFile`：inputStream转File

+ `upload`：将文件名解析成文件的上传路径

+ `downloadExcel`：导出excel

+ `downloadFile`：下载文件

```java
@Test
public void test(){
    String extensionName = getExtensionName("test.java");
    System.out.println(extensionName);
    String fileNameNoEx = getFileNameNoEx("test.java");
    System.out.println(fileNameNoEx);
    String size = getSize(2048);
    System.out.println(size);
}
/************
java
test
2.00KB
*************/
```

### PageUtil

+ `toPage`：分页

### RequestHolder

随时获取 HttpServletRequest

### SecurityUtils

+ `getCurrentUser`：获取当前登录的用户
+ `getCurrentUsername`：获取系统用户名称
+ `getCurrentUserId`：获取系统用户ID
+ `getCurrentUserDataScope`：获取当前用户的数据权限
+ `getDataScopeType`：获取数据权限级别

### StringUtils

+ `toCamelCase`：转成小驼峰命名法
+ `toCapitalizeCamelCase`：转成大驼峰命名法
+ `toUnderScoreCase`：转成下划线命名法
+ `getIp`：根据HTTP请求获取IP地址
+ `getCityInfo`：根据ip获取详细地址
+ `getWeekDay`：当天是周几
+ `getLocalIp`：获取当前机器的IP

### ThrowableUtil

+ `getStackTrace`：获取堆栈信息

### ValidationUtil

+ `isNull`：验证空
+ `isEmail`：验证邮箱

### RsaUtils

+ `encryptByPublicKey`：公钥加密

+ `decryptByPublicKey`：公钥解密
+ `encryptByPrivateKey`：私钥加密
+ `decryptByPrivateKey`：私钥解密
+ `generateKeyPair`：构建RSA密钥对

## annotation（自定义注解）



# eladmin-logging

# eladmin-generator

# eladmin-tools

# eladmin-system