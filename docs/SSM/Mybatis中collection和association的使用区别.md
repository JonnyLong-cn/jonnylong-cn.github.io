# 关联和集合

1.关联-association
2.集合-collection

比如同时有User.java和Card.java两个类

User.java如下:

```java
public class User{
    private Card card_one;
    private List<Card> card_many;
}
```

在映射card_one属性时用association标签, 映射card_many时用collection标签.

所以association是用于一对一和多对一，而collection是用于一对多的关系

下面就用一些例子解释下吧

# association

association一对一，人和身份证的关系

下面是pojo：

```java
public class Card implements Serializable{
	private Integer id;
	private String code;
//省略set和get方法.
}
```

```java
public class Person implements Serializable{
	private Integer id;
	private String name;
	private String sex;
	private Integer age;
	//人和身份证是一对一的关系
	private Card card;
//省略set/get方法.
}
```

下面是mapper和实现的接口：

```java
package com.glj.mapper;
import com.glj.poji.Card;
public interface CardMapper {
	Card selectCardById(Integer id);
}
```

```java
package com.glj.mapper;
import com.glj.poji.Person;
public interface PersonMapper {
	Person selectPersonById(Integer id);
}
```

mapper.xml文件：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE mapper
    PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
    "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="com.glj.mapper.CardMapper">
	<select id="selectCardById" parameterType="int" resultType="com.glj.poji.Card">
		select * from tb_card where id = #{id} 
	</select>
</mapper>
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE mapper
    PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
    "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="com.glj.mapper.PersonMapper">
	<resultMap type="com.glj.poji.Person" id="personMapper">
		<id property="id" column="id"/>
		<result property="name" column="name"/>
		<result property="sex" column="sex"/>
		<result property="age" column="age"/>
		<association property="card" column="card_id" 
			select="com.glj.mapper.CardMapper.selectCardById"
			javaType="com.glj.poji.Card">
		</association>
	</resultMap>
	<select id="selectPersonById" parameterType="int" resultMap="personMapper">
		select * from tb_person where id = #{id}
	</select>
</mapper>
```

PersonMapper.xml 还使用association的分步查询。

同理多对一，也是一样

只要那个pojo出现private Card card_one;

即使用association

# collection 

collection 一对多和association的多对一关系

学生和班级的一对多的例子

pojo类

```java
package com.glj.pojo;

import java.io.Serializable;
import java.util.List;

public class Clazz implements Serializable{
	private Integer id;
	private String code;
	private String name;
        //班级与学生是一对多的关系
	private List<Student> students;
//省略set/get方法
}
```

```java
package com.glj.pojo;
import java.io.Serializable;

public class Student implements Serializable {
	private Integer id;
	private String name;
	private String sex;
	private Integer age;
        //学生与班级是多对一的关系
	private Clazz clazz;
//省略set/get方法
}
```

`selectClazzById`接口和Mapper

```java
package com.glj.mapper;

import com.glj.pojo.Clazz;

public interface ClazzMapper {
	Clazz selectClazzById(Integer id);
}
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE mapper
    PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
    "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="com.glj.mapper.ClazzMapper">
	<select id="selectClazzById" parameterType="int" resultMap="clazzResultMap">
		select * from tb_clazz where id = #{id}
	</select>
	<resultMap type="com.glj.pojo.Clazz" id="clazzResultMap">
		<id property="id" column="id"/>
		<result property="code" column="code"/>
		<result property="name" column="name"/>
		<!-- property: 指的是集合属性的值, ofType：指的是集合中元素的类型 -->
		<collection property="students" ofType="com.glj.pojo.Student"
		column="id" javaType="ArrayList"
		fetchType="lazy" select="com.glj.mapper.StudentMapper.selectStudentByClazzId">
			<id property="id" column="id"/>
			<result property="name" column="name"/>
			<result property="sex" column="sex"/>
			<result property="age" column="age"/>
		</collection>
	</resultMap>
</mapper>
```

`ClazzMapper`使用到了集合-collection 即为一对多，一个班级面对多个学生

```java
package com.glj.mapper;

import com.glj.pojo.Student;

public interface StudentMapper {
	Student selectStudentById(Integer id); 
}
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE mapper
    PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
    "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="com.glj.mapper.StudentMapper">
	<select id="selectStudentById" parameterType="int" resultMap="studentResultMap">
		select * from tb_clazz c,tb_student s where c.id = s.id and s.id = #{id}
	</select>
	<select id="selectStudentByClazzId" parameterType="int" resultMap="studentResultMap">
		select * from tb_student where clazz_id = #{id}
	</select>
	<resultMap type="com.glj.pojo.Student" id="studentResultMap">
		<id property="id" column="id"/>
		<result property="name" column="name"/>
		<result property="sex" column="sex"/>
		<result property="age" column="age"/>
		<association property="clazz" javaType="com.glj.pojo.Clazz">
			<id property="id" column="id"/>
			<result property="code" column="code"/>
			<result property="name" column="name"/>
		</association>
	</resultMap>
</mapper>
```

`StudentMapper`则是与班级为多对一关系，所以使用了关联-association