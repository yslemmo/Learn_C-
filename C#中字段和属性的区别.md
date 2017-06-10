在C#中，我们可以非常自由的、毫无限制的访问公有字段，但在一些场合中，我们可能希望限制只能给字段赋于某个范围的值、或是要求字段只能读或只能写，或是在改变字段时能改变对象的其他一些状态，这些单靠字段是无法做到的，于是就有了属性，属性中包含两个块：**set和get，set块负责属性的写入工作，get块负责属性的读取工作。**在两个块中都可以做一些其他操作，如在set中验证赋的值是否符合要求并决定是否进行赋值。当缺少其中一块时属性就只能读或只能写，set和get块中属性必需有一个，因为即不能读又不能写的属性是没有意义的。
```java
class MyClass
{
       Private  string  name
        public string Name
 {
  get {return Name;}
  set {Name=value;}
 }
}
```

1. 属性可以保证安全，当不在本类中使用时可以保证使用属性名可以避免用字段的名字。
2. 属性的set和get函数可以限制字段的一些功能，以达到某种目的。 如： private int a=0; 

```
public int A
{
     get{return this.a;}
     set
     {
         if(value >= 0 && value <= 100)
              this.a=value;
         else
              throw new Exception("值的范围不合法。");
     }
}
```
3.属性没有存储数据的功能，数据都存在字段中，所以只有修改字段的数据才能更改数据，修改属性的值没用。
