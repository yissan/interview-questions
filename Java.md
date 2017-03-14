### 1.以下代码运行结果？
1.1
```java
Long l1 = 128L;
Long l2 = 128L;
System.out.print(l1 == l2);
System.out.print(l1 == 128L);
```

1.2
```java
Long l1 = 127L;
Long l2 = 127L;
System.out.print(l1 == l2);
System.out.print(l1 == 127L);
```

结果：   
1.1 false  true   
1.2 true  true

原因：   
1.1 l1和l2是两个对象，==比较的是对象的地址，所以false。Long l1== 128L中l1转值比较，所以true。   
1.2 -128 - 127之间的值，Java维护在一个常量池中，所以l1和l2引用同一个对象。

考察点：常量池、==、自动装箱拆箱


### 2、给出以后代码的运行结果
```java 
    String s1 = "abc";
    String s2 = "abc";
    String s3= new String("abc");
    System.out.println("s1 == s2 ? "+(s1==s2));
    System.out.println("s1 == s3 ? "+(s1==s3)); 
    System.out.println("s1 equals s3 ? "+(s1.equals(s3))); 
```
结果： 
```java 
    String s1 = "abc";
    String s2 = "abc";
    String s3= new String("abc");
    System.out.println("s1 == s2 ? "+(s1==s2)); //true
    System.out.println("s1 == s3 ? "+(s1==s3)); //false
    System.out.println("s1 equals s3 ? "+(s1.equals(s3))); //true
```

原因:
有两种方式判断字符串是否相等（==和equals），==除了判断字符串值相等还有比较引用地址，equals只比较值。

考察点：==和equals
