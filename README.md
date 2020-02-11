# interview-tips

### 包装类



#### Boolean类型的工厂方法valueOf

```java
System.out.println(Boolean.valueOf("1"));
System.out.println(Boolean.valueOf("true"));
```

输出结果是：

```java
false
true
```

因为Boolean的valueOf（String s）是判断：

```java
return (s != null) && s.equalsIgnoreCase("true");
```

并不是Python中的非空或是想象中的0与非0



#### Byte Short Integer Long的值比较

这4种对象的值比较，当值在 [-128 , 127] 时，使用的是缓存对象。因此

```
Integer i1 = Integer.valueOf("12");
Integer i2 = Integer.valueOf("12");
```

**i1和i2是指向同一个对象**

因此使用 i1 == i2 得到的是true

但是对于通过new方式创建的包装类就没有这个缓存

```
Integer i1 = new Integer("12");
Integer i2 = new Integer("12");
```

**指向2个不同的对象**

因此 i1 == i2 是false
