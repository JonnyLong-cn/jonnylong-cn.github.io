# Comparable

Comparable接口在JDK8中的源码：

```java
package java.lang;
import java.util.*;

package java.lang;
public interface Comparable<T> {
    public int compareTo(T o);
}
1234567
```

用法：

```java
public class User implements Comparable<User>{
    private Integer id;
    private Integer age;

    public User() {
    }

    public User(Integer id, Integer age) {
        this.id = id;
        this.age = age;
    }

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public Integer getAge() {
        return age;
    }

    public void setAge(Integer age) {
        this.age = age;
    }

    @Override
    public String toString() {
        return "User{" +
                "id=" + id +
                ", age=" + age +
                '}';
    }

    public int compareTo(User o) {
        if(this.age > o.getAge()) {
            return 1;
        }else if(this.age < o.getAge()) {
            return -1;
        }else{
            return 0;
        }
    }
}
12345678910111213141516171819202122232425262728293031323334353637383940414243444546
public class Test {
    public static void main(String[] args) {
        User user1 = new User(1, 14);
        User user2 = new User(2, 12);
        User user3 = new User(3, 10);
        User[] users = {user1, user2, user3};
        Arrays.sort(users);
        Arrays.stream(users).forEach(System.out::println);
    }
}
12345678910
```

`int compareTo(To)`：

比较此对象与指定对象的顺序。如果该对象小于、等于或大于指定对象，则分别返回负整数、零或正整数。

参数：要比较的对象。

返回：负整数、零或正整数，根据此对象是小于、等于还是大于指定对象。

抛出：`ClassCastException`，如果指定对象的类型不允许它与此对象进行比较

# Comparator

Comparator接口在JDK8中的源码：

```java
package java.util;

import java.io.Serializable;
import java.util.function.Function;
import java.util.function.ToIntFunction;
import java.util.function.ToLongFunction;
import java.util.function.ToDoubleFunction;
import java.util.Comparators;

public interface Comparator<T> {
	int compare(T o1, T o2);
	//还有很多其他方法...
}
12345678910111213
```

使用：

```java
public class Child {
    private Integer id;
    private Integer age;

    public Child() {
    }

    public Child(Integer id, Integer age) {
        this.id = id;
        this.age = age;
    }

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public Integer getAge() {
        return age;
    }

    public void setAge(Integer age) {
        this.age = age;
    }

    @Override
    public String toString() {
        return "Child{" +
                "id=" + id +
                ", age=" + age +
                '}';
    }
}
123456789101112131415161718192021222324252627282930313233343536
public class Test {
    public static void main(String[] args) {
        Child child1 = new Child(1, 14);
        Child child2 = new Child(2, 12);
        Child child3 = new Child(3, 10);

        List<Child> list = new ArrayList<>();
        list.add(child1);
        list.add(child2);
        list.add(child3);

        Collections.sort(list, new Comparator<Child>() {
            @Override
            public int compare(Child o1, Child o2) {
                return  o1.getAge() > o2.getAge() ? 1 : (o1.getAge() == o2.getAge() ? 0 : -1);
            }
        });

        // 或者使用JDK8中的Lambda表达式
        //Collections.sort(list, (o1, o2) -> (o1.getAge()-o2.getAge()));

        list.stream().forEach(System.out::println);
    }
}
123456789101112131415161718192021222324
```

或者也可以通过实现的方式使用Comparator接口：

```java
import java.util.Comparator;

public class Child implements Comparator<Child> {
    private Integer id;
    private Integer age;

    public Child() {
    }

    public Child(Integer id, Integer age) {
        this.id = id;
        this.age = age;
    }

    @Override
    public int compare(Child o1, Child o2) {
        return o1.getAge() > o2.getAge() ? 1 : (o1.getAge() == o2.getAge() ? 0 : -1);
    }

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public Integer getAge() {
        return age;
    }

    public void setAge(Integer age) {
        this.age = age;
    }

    @Override
    public String toString() {
        return "Child{" +
                "id=" + id +
                ", age=" + age +
                '}';
    }
}
12345678910111213141516171819202122232425262728293031323334353637383940414243
public class Test {
    public static void main(String[] args) {
        Child child1 = new Child(1, 14);
        Child child2 = new Child(2, 12);
        Child child3 = new Child(3, 10);

        List<Child> list = new ArrayList<>();
        list.add(child1);
        list.add(child2);
        list.add(child3);
        
        Collections.sort(list, new Child());
        list.stream().forEach(System.out::println);
    }
}
123456789101112131415
```

# Comparator其他默认方法

## **reversed方法**

```java
default Comparator<T> reversed() {
        return Collections.reverseOrder(this);
    }
123
```

这个方法是用来生成一个逆序器,比如我们开始需要得到一个正序的排序序列,然后又想得到一个反转的排序序列,就可以使用该方法。比如：

```java
public class Test {
    public static void main(String[] args) {
        Child child1 = new Child(1, 14);
        Child child2 = new Child(2, 12);
        Child child3 = new Child(5, 10);
        Child child4 = new Child(4, 10);

        List<Child> list = new ArrayList<>();
        list.add(child1);
        list.add(child2);
        list.add(child3);
        list.add(child4);

        Comparator<Child> comparator = Comparator.comparingInt(x -> x.getAge());
        Collections.sort(list, comparator);
        list.stream().forEach(System.out::println);
        Collections.sort(list, comparator.reversed());
        list.stream().forEach(System.out::println);
    }
}
1234567891011121314151617181920
```

## **thenComparing**

```java
default <U extends Comparable<? super U>> Comparator<T> thenComparing(
            Function<? super T, ? extends U> keyExtractor)
    {
        return thenComparing(comparing(keyExtractor));
    }
12345
```

该方法是在原有的比较器上再加入一个比较器，比如先按照年龄排序，年龄相同的在按照id排序。比如：

```java
public class Test {
    public static void main(String[] args) {
        Child child1 = new Child(1, 14);
        Child child2 = new Child(2, 12);
        Child child3 = new Child(5, 10);
        Child child4 = new Child(4, 10);

        List<Child> list = new ArrayList<>();
        list.add(child1);
        list.add(child2);
        list.add(child3);
        list.add(child4);

        Comparator<Child> comparator = Comparator.comparingInt(x -> x.getAge());
        Collections.sort(list, comparator);
        list.stream().forEach(System.out::println);
        System.out.println("-----");
        Collections.sort(list, comparator.thenComparing(x->x.getId()));
        list.stream().forEach(System.out::println);
    }
}
123456789101112131415161718192021
```

# 区别

- `Comparable`接口位于`java.lang`包下；`Comparator`位于`java.util`包下
- `Comparable`接口只提供了一个`compareTo()`方法；`Comparator`接口不仅提供了`compara()`方法，还提供了其他默认方法，如`reversed()`、`thenComparing()`，使我们可以按照更多的方式进行排序
- 如果要用`Comparable`接口，则必须实现这个接口，并重写`comparaTo()`方法；但是`Comparator`接口可以在类外部使用，通过将该接口的一个匿名类对象当做参数传递给`Collections.sort()`方法或者`Arrays.sort()`方法实现排序。`Comparator`体现了一种策略模式，即可以不用要把比较方法嵌入到类中，而是可以单独在类外部使用，这样我们就可有不用改变类本身的代码而实现对类对象进行排序。

w