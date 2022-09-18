#JavaSE

## 基本语法

### 关键字与保留字



* ![Snipaste_2022-08-30_17-28-58](E:\截图\Snipaste_2022-08-30_17-28-58.png)

![Snipaste_2022-08-30_17-29-15](E:\截图\Snipaste_2022-08-30_17-29-15.png)

**java保留字:现有java版本尚未使用,但以后版本可能会作为关键字使用.自己命名标识符是要避免使用这些保留字.**

​	**goto  const**

### 标识符及命名规则

![Snipaste_2022-08-30_17-40-32](E:\截图\Snipaste_2022-08-30_17-40-32.png)


标识符的命名规范

![Snipaste_2022-08-30_17-45-41](E:\截图\Snipaste_2022-08-30_17-45-41.png)


### 变量

#### 变量的定义

![Snipaste_2022-08-30_17-50-24](E:\截图\Snipaste_2022-08-30_17-50-24.png)


#### 数据类型

- 基本数据类型

  数值型:整数类型**(byte,short,int,long)**

  ​	     浮点类型**(float,double)**	

  字符型**(char)**

  布尔型**(boolean)**

- 引用数据类型

  类**(class)**

  接口**(interface)**

  数组**([])**

  

#### 变量的使用



1. 整型  : byte(1字节=8bit) \ short(2字节) \ int(4字节) \ long(8字节)

   ①byte范围 : -128~127

   ②声明long型变量,结尾必须以"L"或"l"结尾, 例如 : long l1 = 2234L;

2. 浮点型 : float(4字节) \ double(8字节)

   ①浮点型,表示带小数点的数值

   ②float表示的数值范围比long大

   ③定义float变量时,变量要以"F"或"f"结尾,例如 : float f1 = 123F;

   ④通常,定义浮点型变量时,使用double型

3. 字符型 : char (1字符=2字节)

   ①定义char型变量,通常使用一对 '' ,内部只能写一个字符

   ②表示方式 : 1. 声明一个字符 2. 转义字符 3. 直接使用 Unicode 值来表示字符型常量

4. 布尔型 : boolean

   ①只能取两个值之一 : true , false

   ②常常在条件判断 , 循环结构中使用

   ```java
   boolean isMarried = true ;
   if(isMarried){
       
   }else{
       
   }
   ```

5. String类型

   ①String属于引用数据类型,翻译为 : 字符串

   ②声明String类型变量时,使用一对 "" 

   ```java
   String s1 = "Hello World!";
   ```

   ③String可以和8种基本数据类型变量做运算,且运算只能是连接运算 :    +

   ```java
   int number = 1001 ;
   String numberStr = "学号 : " ;
   String info = number + numberStr ;
   ```

   ④运算的结果仍然是String类型

   

	### 自动类型提升和强制类型转换	

前提 : 这里讨论的只是7种基本数据类型变量间的运算.不包含boolean型.

1. 自动类型提升

   ```java
   byte b1 = 2 ;
   int i1 = 129 ;
   //编译不通过
   //byte b2 = b1 + i1 ;
   int i2 = b1 + i1 ;//yes
   long l1 = b1 + i1 ;//yes
   
   float f1 = b1 + i1 ;//yes
   ```

   结论  : 当容量小的数据类型的变量与容量大的数据类型的变量做运算时,结果自动提升为容量大的数据类型.

   > byte , char,short --> int --> long --> float --> double
   >
   > ***特别的 :  当byte,char,short三种类型的变量做运算时,结果为int型***

   ```java
   char c1 = 'A' ;
   int i3 = 10 ;
   int i4 = c1 + i3 ; //yes
   
   short s2 = 10 ;
   //char c2 = c1 + s2 ; 编译不通过
   int i5 = c1 + s2 ;
   
   byte b2 =10 ;
   //char c3 = b2 + c1 ;编译不通过
   //short  = b2 + c1 ;编译不通过
   int i6  = b2 + c1 ;
   
   ```

   

   说明 : 此时的容量大小指的是,表示数的范围的大和小.比如 : float容量要大于long的容量.

   

2. 强制类型转换 : 自动类型提升的逆运算

   ①需要使用强转符 : ()

   ```java
   double d1 = 12.9 ;
   int i1 = (int)d1 ;
   ```

   

   ②注意点 : 强制类型转换,可能导致精度损失

   特殊情况 : 

   1.编码情况1

   ```java
   long l = 123321 ;//int型自动类型提升为long型,然后赋给long
   ```

   2.编码情况2 : 

   ​	整型常量默认为int型,浮点型常量默认为double型

   ```java
   byte b = 12 ;
   //byte b1 = b + 1 ;编译失败
   
   //float f1 = b + 12.3 ; 编译失败
   ```

   

### 运算符的使用

 算术运算符 : +  - * / % 

 赋值运算符 :  = , += ,-= , *= 

 比较运算符 :  > , < ,>= ,<=

 逻辑运算符 :  && , || , !

 位运算符     :  

 三元运算符 : (条件表达式) ? (表达式1): (表达式2)

```java
int max = (m>n) ? m : n;
```

 运算符的优先级 :

![](E:\截图\是.png)



### 流程控制

#### if-else

```java
if(ture){
    
}else{
    
}
```



#### switch

```{java
switch(n){

    case 1 :
    case 2 : break;
    default :	
        	//break;
        
}
```



#### for

```java
for(i=1 ; i<n ; i++){
    
}
```



#### while和do-while

```java
while(ture){
}

do{
    
}while(true);
```



#### break和continue



## 数组

### 一维数组

①一维数组的声明和初始化

```java
int [] ids;//声明
ids = new int[]{1001,1002,1003,1004};//静态初始化:赋值操作和初始化同时进行

String[] names = new String[5];//动态初始化:赋值操作在后续进行
```



②如何调用数组的指定位置的元素

```java
names[0] = "张合" ;
names[1] = "李达" ;
names[4] = "刘叁" ;
```



③如何获取数组的长度

```java
System.out.println(names.length);
System.out.println(lds.length);
```



④如何遍历数组

```java
for(int i=0 ; i < names.length ; i++){
    
}
```



⑤数组元素的默认初始化值

> 整型 :  0
>
> 浮点型: 0.0
>
> char型 : 0或'\u0000',而非'0'
>
> boolean型 : false
>
> 引用数据类型: null



⑥数组的内存解析



![Snipaste_2022-08-31_11-14-57](E:\截图\Snipaste_2022-08-31_11-14-57.png)

![Snipaste_2022-08-31_11-16-17](E:\截图\Snipaste_2022-08-31_11-16-17.png)



### 二维数组

①一维数组的声明和初始化

```java
int [][] arr1 = new int[][]{{1,2,3},{4,5},{6,7,8}};//静态初始化

String[][] arr2 = new String[3][2];//动态初始化1
String[][] arr3 = new String[3][] ;//动态初始化2

```



②如何调用数组的指定位置的元素

```java
System.out.println(arr1[2][1]);
```



③如何获取数组的长度

```java
System.out.println(arr1.length);//3
System.out.println(arr1[0].length);//3
System.out.println(arr1[1].length);//2
```



④如何遍历数组

```java
for(int i=0 ; i<arr1.length ; i++){
    
	for(int j=0 ; j<arr1[i].length ; j++){
	
    }
}
```



⑤数组元素的默认初始化值

>外层元素的初始化值为 : 地址值
>
>内层元素的初始化值为 : 与一维数组初始化情况相同



⑥二维数组的内存解析

![Snipaste_2022-08-31_11-45-25](E:\截图\Snipaste_2022-08-31_11-45-25.png)



## 面向对象

### 类和对象

* 类(Class)和对象(Object)是面向对象的核心概念

  >类是对一类事物的描述,是抽象的,概念上的定义
  >
  >对象是实际存在的该类事物的每个个体,因而也称为实例

#####创建类的对象

```java
Person p1 = new Person();
```

##### 调用对象的结构(属性,方法)

```java
p1.name = "Tom";
p1.age = 18;

p1.eat();
p1.sleep();
```



##### 对象的内存解析

![Snipaste_2022-08-31_17-54-10](E:\截图\Snipaste_2022-08-31_17-54-10.png)



##### 对象数组

![Snipaste_2022-08-31_18-42-52](E:\截图\Snipaste_2022-08-31_18-42-52.png)



##### 匿名对象

```java
public class Test {
    public static void main(String[] args){
        new Phone().price = 1999;
        new Phone().showPrice();//0.0  匿名对象只用一次
    }
}
class Phone {
    double price;
	public void showPrice(){
		 
    }
}
```

```java
public class Test {
    public static void main(String[] args){
        Phine mall = new Phone();
        mall.show(new Phone());//匿名对象赋给了形参
    }
}
class PhoneMall{
    public void show(Phone phone){
        phone.sendEmail();
    }
}
```





### Java类和类的成员

```java
class Person{
    
}
```



#### 属性

```java
string name;
int age;
```



##### 属性和局部变量

1. 相同点

>1.1定义变量的格式 : 数据类型  变量名 = 变量值
>
>1.2先声明,后使用
>
>1.3变量都有其对应的作用域



2. 不同点

>2.1在类中声明的位置不同
>
>属性 : 直接定义在类的一对{}内
>
>局部变量 : 声明在方法内,方法形参,代码块内,构造器形参,构造器内部的变量

```java
public void talk(String language){//language : 局部变量
    
}
public void eat(){
    String food = "烙饼";//food : 局部变量
}
```

		>2.2关于权限修饰符
		>
		>属性 : 可以在声明属性时,指明其权限,使用权限修饰符.
		>
		>局部变量 : 不可以使用权限修饰符

```java
public void eat(){
	//private String food = "烙饼";错误
    String food = "烙饼";
}
```

>2.3默认初始化值的情况
>
>属性 : 类的属性,根据其类型,都有默认初始化值
>
>​	   整型(byte,short,int,long) : 0
>
>​	   浮点型(float,double) : 0.0 
>
>​	   字符型(char) : 0 (或'\u0000') 
>
>​	   布尔型(boolean) : false
>
>​	   引用数据类型(类,接口,数组) :  null 
>
>局部变量 : 没有默认初始化值
>
>​			意味着,我们在调用局部变量之前,一定要显式赋值.
>
>​			特别的 : 形参在调用时,我们赋值即可
>
>```java
>public void food(){
>	//String food ;错误
>}
>
>u1.talk("英语");
>```

>2.4在内存中加载的位置
>
>属性 : 加载到堆空间中	(非static)
>
>局部变量 : 加载到栈空间



#### 方法

声明 : 

​	权限修饰符	返回值类型	方法名(形参列表){

​					方法体;

}

```java
public void eat(){
    
}
public void sleep(int hour){
    
}
public String talk(String language){
}
```

##### 方法重载(overload)

1. 定义 : 在同一个类中,允许存在一个以上的同名方法,只要它们的**参数个数**或者**参数类型**不同

   "两同一不同" : 同一个类,相同方法名

   ​			 参数列表不同 : 参数个数不同,参数类型不同

   ```java
   public class OverLoadTest{
       //如下的四个方法构成了重载
       public void getSum(int i,int j){
           
       }
       public void getSum(double d1,double d2){
           
       }
       public void getSum(String s,int i){
            
   	}
       public void getSum(int i,String s){
           
       }
   }
   ```

2. 判断是否是重载 : 

   ​	跟方法的权限修饰符,返回值类型,形参变量名,方法体都无关



##### 可变个数形参的方法

1. jdk 5.0 新增的内容

2. 具体使用

   2.1 可变个数形参的格式 : 数据类型 ... 变量名 

   2.2 当调用可变个数形参的方法时,传入的参数个数可以是 : 0个,1个,2个,多个......

   2.3 可变个数形参的方法与本类中 方法名相同,形参不同的方法之间构成重载

   ```java
   public class MethodTest {
       public static void main(String[] args){
           MethodTest test = new MethodTest();
           test.show("Hello");
           test.show("Hello","World");
           test.show();
       }
       
      // public void show(String s){
      //     
      // }
       public void show(String ... strs){//可变个数形参的方法
           
       }
   }
   ```

   2.4 可变个数形参的方法与本类中 方法名相同,形参类型也相同的数组不构成重载..二者不能共存

   ```java
    public void show(String ... strs){//可变个数形参的方法
           
       }
   //jdk5.0之前是用下面这种,两者任选其一
    public void show(String[] strs){//不构成重载
           
       }
   //下面这种调用有一点不同
   //test.show(new String[]{"AA","BB","CC"});//调用可变形参数组
   ```

   2.5 可变个数形参在方法的形参中,必须声明在末尾

   ```java
   public void test(int i ,String ... strs){
   	
   }
   ```

   2.6 可变个数形参在方法的形参中,最多只能声明一个可变形参

   ```java
   //public void test(String ... s ,String ... strs){ 错误 错误
   //	
   //}  
   ```

   



##### 方法参数的值传递机制

1. 理解变量的赋值 : 

   如果变量是基本数据类型,此时赋值的是变量所保存的**数据值**

   ```java
   int i = 1;
   int j;
   j = i;
   ```

   如果变量是引用数据类型,此时赋值的是变量所保存的数据的**地址值**

   ```java
   Order o1 = new Order();
   o1.orderId = 1001 ;
   Order o2 = o1 ; //地址值
   o2.orderId =  2002;
   System.out.println("o1.orderId = " + o1.orderId);//输出 o1.orderId = 2002
   ```

2. 值传递机制 : 

   如果参数是基本数据类型,此时实参赋给形参的是实参真实存储的**数据值**

   ```java
   public class Test{
   	public static void main(String[] args){
       	int m = 10;
       	int n = 20;
       
       	Test.swap(m,n);
       	System.out.println("m=" + m +",n=" + n);//m=10,n=20   没有交换
   	}
       
   	public void swap(int i , int j){
   		int temp = m;
   		m = n ;
   		n = temp ;
   	}
   }
   ```

   如果是引用数据类型,此时实参赋给形参的是实参存储数据的**地址值**

   ```java
   public class Test{
   	public static void main(String[] args){
       	Date date = new Date();
           date.m = 10;
           date.n = 20;
           
           Test test = new Test();
           test.swap(date);
           
           System.out.println("date.m=" + date.m +",date.n=" + date.n);//date.m=20,date.n=10;
          														   //交换了
   	}
       
   	public void swap(Date date){
   		int temp = date.m;
   		date.m = date.n ;
   		date.n = temp ;
   	}
   }
   
   class Date{
       int m;
       int n;
   }
   ```

   ```java
   //交换数组中指定元素的值
   public void swap(int[] arr,int i, int j){
   	int temp = arr[i];
       arr[i]=arr[j];
       arr[j]=temp;
   }
   ```

   

##### 递归方法

>一个方法体内调用它自身

```java
public int getSum(int n){//n=3
    if(n == 1){
        return 1;
    }else{
        return n + getSum(n-1);//调用自身
    }
}
```





#### 构造器

> 作用 : ①创建对象 ②给对象进行初始化

1. 如果没有显式的定义类的构造器,则系统默认提供一个空参的构造器
2. 定义构造器的格式 : 权限修饰符 类名(形参列表){  }
3. 一个类中定义的多个构造器,彼此构成重载 
4. 一旦我们定义了构造器,系统就不提供默认的空参构造器了
5. 一个类中,至少有一个构造器

``````````````````````java
class Person{
    //属性
    String name;
    int age;
    
    //构造器
    public Person(){
	
    }
    public Person(int age){
        age = 18;//当前创建对象的age
    }
}
``````````````````````

##### JavaBean

满足以下条件的类,被称为JavaBean

> 类是公共的
>
> 有一个无参的公共的构造器
>
> 有属性,且有对应的get,ste方法

```java
public void Customer {
    
    private int id;
    
    public int getId(){
        return id;
    }
    public void setId(int i){
        id=i;
	}
    
    public Customer(){
        
    }
}
```







#### 代码块

1. 代码块的作用 : 用来初始化类 , 对象

2. 代码块只能用static修饰

3. 分类 : 静态代码块  vs  非静态代码块

4. 静态代码块

   > ①内部可以有输出语句
   >
   > ②随着类的加载而执行 , 而且只执行一次

   ```java
   class Block{
   
       static{
   
           System.out.println("111111");
       }
   }
   ```

   

5. 非静态代码块

   > ①内部可以有输出语句
   >
   > ②随着对象的创建而执行,每创建一次对象,就执行一次非静态代码块
   >
   > ③作用 : 可以在创建对象时 , 对对象的属性等进行初始化

   ```java
   class Block{
   
       int age ;
       
       {
           System.out.println("22222222");
           age = 18;
       }
   }
   
   ```

   





#### 内部类

1. Java中允许将一个类A声明在另一个类B中 , 类A就是内部类

2. 内部类分为 : 成员内部类(静态 , 非静态)   vs  局部内部类(方法内,代码块内,构造器内)

3. 成员内部类 : 

   > ①类内可以定义属性 , 方法 , 构造器等
   >
   > ②可以被final修饰 , 表示此类不能被继承
   >
   > ③可以被abstract修饰 , 不能被实例化
   >
   > ④可以调用外部类的结构
   >
   > ⑤可以被static修饰
   >
   > ⑥可以被四种不同的权限修饰

   ```java
   class Person{
   
       String name;
       
       public void eat(){
   
       }
       
       //静态成员内部类
       static class Brain{
   
           //内部类定义属性
           private iq;
           
           public Brain(){  //内部类定义构造器
               
           }
           
           public int Iq(){ //内部类定义方法
               return iq;
           }
       }
       
       //非静态成员内部类
       class Eat{
   
           public void meat(){
               eat();   //调用外部类的方法
           }
       }
   }
   ```

   > 3.1 如何实例化成员内部类的对象
   >
   > 3.2如何在成员内部类中区分调用外部类的结构
   >
   > 3.3 开发中局部内部类的使用

   ```java
   //如何实例化成员内部类对象
   public void InnerClassTest{
       public static void main(String[] args){
   
           //静态成员内部类的实例化
           Person.Brain brain = new Person.Brain();
           brain.Iq();
           
           //非静态成员内部类的实例化
           Person p = new Person();
           Person.Eat eat = p.new Eat();
           eat.meat();
       }
   }
   ```

   ```java
   //区分调用内部类的接口
   class Animal(){
   
       String name;
       int age;
       
       class Cat{  //内部类
           String name;
           
           public void eat(String name){
               System.out.println(name);	//形参
               System.out.println(this.name);	//内部类的属性
               System.out.println(Person.this.name);	//外部类的属性
           }
       }
   }
   ```

4. 局部内部类

   ```java
   class Person{
       
       //很少用
       public void eat(){
           class{
               
           }
       }
       
       //返回一个实现了Comparable接口的类的对象
       public Comparable getComparable(){
           class MyComparable implements Comparable{  //实现Comparable接口的类
                 
           }
           return new MyComparable();
       }
       
   }
   ```

   





###封装

* 高内聚,低耦合

> 高内聚 : 类的内部数据操作细节自己完成 , 不允许外部干涉;
>
> 低耦合 : 仅对外暴露少量的方法用于使用

* 隐藏对象内部的复杂性 , 只对外公开简单的接口

	 便于外界调用	, 从而提高系统的可拓展性 , 可维护性 . 
>
> 把该隐藏的隐藏起来,该暴露的暴露出来

#### 封装与隐藏

> 当我们创建一个类的对象时以后 , 我们可以使用"对象.属性"的方式 , 对对象的属性进行赋值.这里,赋值操作要受到属性的数据类型和存储范围的制约.除此之外 , 没有其他制约条件.但是,在实际问题中,我们往往需要给属性赋值加入额外的限制条件.这个条件就不能在属性声明时体现,我们只能通过方法进行限制条件的添加.
>
> (比如setLegs方法)
>
> 同时,我们需要避免用户再使用"对象.属性"的方式对属性进行赋值.则需要将属性声明为私有的(private)

####封装性的体现

> 我们将类的属性xxx私有化(private),同时,提供公共的(public)方法来获取(getXxx)和设置(setXxx)此属性的值

```java
public class AnimalTest{
    public static void main(String[] args){
		Animal a = new Animal();
         a.name = "大黄";
         a.age = 2;
//       a.legs = 4; //The field Animal.legs is not visible
        
        a.setLges(6);
//		System.out.println(a.legs);//有时我们需要用到属性的值,可用get方法        
    }
}

class Animal{
    String name ;
    int age ;
    private int legs ; //隐藏
    
    public void setLges(int l){//对属性的设置
        if(l>=0 && l%2==0){
            legs = l;
        }else{
            legs=0;
//		    或者抛出一个异常            
         }
    } 
    
    public int getLges(){//对属性的获取
        return legs;
    }
}
```

> 拓展:封装性的体现 : ① 如上 ②私有方法 ③ 单例模式 ...

#### 四种权限修饰符

1. Java规定的4种权限(从小到大) : private , 缺省 , protected  , public

2. 4种权限可以用来修饰类及类的内部结构 : 属性 , 方法 , 构造器 , 内部类

3. 具体的, 4种权限都可以用来修饰类及类的内部结构 : 属性 , 方法 , 构造器 , 内部类

   ​		修饰类的话,只能用 : 缺省 , public

![Snipaste_2022-09-01_17-06-07](E:\截图\Snipaste_2022-09-01_17-06-07.png)



#### this

1. this调用属性,方法. 通常省略this.

   1.1如果方法的形参和类的属性同名时,我们必须显式的使用"this.变量"的方式,表明此变量是属性,而非形参

   1.2如果构造器的形参和类的属性同名时,,我们必须显式的使用"this.变量"的方式,表明此变量是属性,而非形参

   ```java
   public class PersonTest{
       public static void main(String[] args){
   		Person p1 = new Person();
           p1.setAge(2);
           System.out.println("p1.getAge()");
           
           p1.eat();
       }
   }
   
   class Person{
       private int age ;
       
       public int getAge(){
           return age;
       }
       public void setAge(int age){
           this.age = age;
       }
       
       
       public void eat(){
   		study();//省略了this.
       }
       public void study(){
           System.out.println("吃完饭学习");
       }
   }
   
   ```

2.this调用构造器

①在类的构造器中,可以显式的使用"this(形参列表)"方式,调用本类中指定的其他构造器

②构造器中不能通过"this(形参列表)"的方式调用自己

③不能循环调用

④必须声明在构造器的首行

⑤一个构造器内只能调用一个

```java
class Person{
    String name;
    int age;
    
    //构造器
    public Person(){
        //.....一些代码
    }
    public Person(int age){
        this();//调用上一个构造器
        this.age = age;
    }
    public Person(String name,int age){
		this(age);//调用上一个构造器
    }
}
```







###继承

#### 继承的格式和规定

1. 继承性的格式 : class A extends B{ }

   A : 子类,派生类,subclass

   B : 父类,超类,基类,superclass

   体现 : 一旦子类A继承父类B以后,子类A中就获取了父类B中声明的所有的属性和方法

   > 特别的 : 父类中声明为private的属性和方法,子类继承父类以后,仍然认为获取了父类中私有的结构
   >
   > ​		只是因为封装性的影响,使得子类不能直接调用父类的结构而已

   子类继承父类以后,还可以声明自己特有的属性和方法,实现功能的拓展

   ```java
   class Person{
   	
       String name;
       int age;
       
       public Person(){
       }
       public Person(String name , int age){
           this.name = name;
           this.age = age;
       }
       
       public void eat(){ 
       }
       public void sleep(){ 
       }
       
   }
   ```

   ```java
   class Student extends Person{
   //    String name;继承了父类的属性
   //    int age;
       String major;
       
       public Student(){
       }
       public Student(String name , int age , String major){
           this.name = name;
           this.age = age;
           this.major = major;
       }
       
   //    public void eat(){ 继承了父类的方法
   //    }
   //    public void sleep(){ 
   //    }
       public void study(){
       }
   }
   ```

2. 关于继承性的规定

   > 1.1 一个类可以被多个子类继承
   >
   > 1.2 Java中的单继承性 : 一个类只能有一个父类
   >
   > 1.3 子父类是相对的概念
   >
   > 1.4 子类直接继承的父类,称为直接父类.间接继承的父类,称为间接父类
   >
   > 1.5 子类继承父类以后,就获取了直接父类和所有间接父类中声明的属性和方法





#### 方法重写(override/overwrite)

1. 重写 : 子类继承父类以后,可以对父类中同名同参数的方法,进行覆盖操作
2. 应用 : 重写以后,当创建子类对象以后,通过子类对象调用子父类中同名同参数方法是,执行的是重写的方法

```java
class Person{
	
    String name;
    int age;
    
    public Person(){
    }
    public Person(String name , int age){
        this.name = name;
        this.age = age;
    }
    
    public void eat(){ 
    }
    public void sleep(){ 
    }
    
}
```

```java
class Student extends Person{
    String major;
    
    public Student(){
    }
    public Student(String name , int age , String major){
        this.name = name;
        this.age = age;
        this.major = major;
    }
    
    public void study(){
    }
    public void eat(){//重写父类的eat方法
        System.out.println("多吃饭");
    }
}
```

3. 重写的规定

   ​	方法的声明 : 权限修饰符     返回值类型     方法名(形参列表)     throws    异常的类型{

   ​						//方法体

   ​				}

   ①子类重写的方法的方法名和形参列表与父类被重写的方法名和形参列表相同

   ②子类重写的方法的权限修饰符不小于父类被重写的方法的权限修饰符

   > 特殊情况 : 子类不能重写父类中声明为private权限的方法

   ③返回值类型

   > 父类被重写的方法的返回值类型是void,则子类重写的方法的返回值类型只能是void

   > 父类被重写的方法的返回值类型是A类型,则子类重写的方法的返回值类型可以是A类或A类的子类

   > 父类被重写的方法的返回值类型是基本数据类型,则子类重写的方法的返回值类型必须是相同的基本数据类型

   ④子类重写的方法抛出的异常类型不大于父类被重写的方法抛出的异常类型

   说明 : 子类和父类中的同名同参数的方法要么都声明为非static的,要么都声明为static的(static 不是重写)



#### super

1. super调用属性和方法

> 1.1 我们在子类的方法或构造器中.通过使用"super.属性"或"super.方法"的方式.显式调用父类中声明的属性和方法.但是,通常情况下,我们习惯省略"super"
>
> 1.2 特殊情况 : 当子类和父类定义了同名的属性时,我们要想在子类中调用父类中声明的属性,必须显式的使用"super.属性"
>
> 1.3 特殊情况 : 当子类重写了父类的方法以后,我们想在子类的方法中调用父类中被重写的方法时,则必须显式的使用"super.方法".

```java
public class Test{
    public static void main(String[] args){

        Student p1 = new Student();
        p1.show();
        
    }
}
class Person{
    int id = 4200000;//身份证
}
class Student extends Person{
    int id = 1001;//学号 //属性不能覆盖
    
    public void show(){
		System.out.println("id = " + this.id);
         System.out.println("id = " + super.id);//调用父类的属性
    }
}
```

2. super调用构造器

> 2.1 我们可以在子类的构造器中显式的使用"super(形参列表)"的方式,调用父类的构造器
>
> 2.2 "super(形参列表)"的使用,必须声明在子类构造器的首行
>
> 2.3 我们在类的构造器中,针对于"this(形参列表)"和"super(形参列表)"只能二选一,不能同时出现
>
> 2.4 在构造器的首行,没有声明"this(形参列表)"或"super(形参列表)",则默认调用父类中的空参构造器
>
> 2.5 在类的构造器中,至少有一个类的构造器使用了"super(形参列表)",调用父类中的构造器



```java
class Person{
    
    public Person(){
        //super(); //省略了
    }
    public Person(string name , int age){
		//super();  //省略了
    }
}
class Student extends Person{
    int id = 1001;//学号 //属性不能覆盖
    
    public Student(){
		super();//子类构造器中调用父类空参构造器
         super(name,age);//调用父类中带参的构造器
    }
}

```









###多态



#### 多态定义和使用

1. 理解多态性 : 可以理解为一个事物的多种形态.

2. 何为多态性

   对象的多态性 : 父类的引用指向子类的对象(或子类的对象赋给父类的引用)

   ```java
   Person p1 = new Man();// Man 是 Person 的子类 
   ```

3. 多态的使用 : 虚拟方法调用

   > 有了多态性以后,我们在编译期,只能调用父类声明的方法,但在运行期,我们实际执行的是子类重写父类的方法.   总结就是 : 编译看左边,运行看右边

   ```java
   Person p1 = new Man();
   p1.eat(); //调用的是子类重写的方法
   p1.walk(); //
   
   // p1.earnMoney();  //Person类中没有声明的方法不能调用
   ```

   补充 : 不能调用子类特有的属性和方法 : 编译时,p时Person类型



4. 多态性的使用前提 : ① 类的继承关系  ② 方法的重写

    多态性使用举例

```Java
public void AnimaTest{
    public static void main(String[] args){
        AnimalTest test = new AnimalTest();
        test.func(new Dog());
        
        test.func(new Cat());//
    }
    
    public void func(Animal animal){//Animal animal = new Dog();
        animal.eat();
        animal.shout();
    }
//		如果没有多态   Dog和Cat都要单独造方法
//  public void func(Dog dog){   
// 
//	}
//	public void func(Cat cat){  // 
// 
//	}
    
    
}

class Animal{

    pubilc void eat(){
	}
    public void shout(){ 
    }
}

class Dog extends Animal{
    pubilc void eat(){//重写父类的eat()方法
	}
    public void shout(){ 
    }
}

class Cat extends Animal{
    pubilc void eat(){//重写父类的eat()方法
	}
    public void shout(){ 
    }
}
```

5. 对象的多态性,只适用于方法,不适用于属性

```java
System.out.println(p1.id);//调用的是父类的属性
```



#### 虚拟方法调用

> 子类中定义了与父类同名同参数的方法,在多数情况下,将此时父类的方法称为虚拟方法,父类根据赋给它的不同子类对象,动态调用属于子类的该方法.这样的方法调用在编译期是无法确定的.

```java
	Person p = new student();
	p.eat();		//调用Student类中eat方法
```



#### instanceof关键字

> 有了对象的多态性以后,内存中实际是加载了子类特有的属性和方法的,但是由于变量声明为父类类型,导致编译时,只能调用父类中声明的属性和方法.子类特有的属性和方法不能调用.

1. 如何调用子类特有的属性和方法?

> 向下转型 : 使用强制类型转换符

```java
Person p = new Man();
//	p.earnMoney();    //不能调用子类特有的方法

Man m1 = (Man)p;  //强制转换
m1.earnMoney();  //

//使用强制转换时,可能会出现ClassCastException的异常    
//	Woman w1 = (Woman)p;
//	w1.goShopping(); //运行时会出错
```



2. instanceof关键字的使用

   > a instanceof A : 判断对象a是否是类A的实例.如果是,返回true,否则返回false

   使用情境 : 为了避免在向下转型是出现ClassCastException的异常,我们在向下转型之前,先使用instanceof进行判断. 返回ture就向下转型

   ```java
   Person p = new Man();
   
   if(p instanceof Woman){ //false
       Woman w1 = (Woman)p;
       m1.earnMoney();
       w1.goShopping();
   }
   
   if(p instanceof Man){   //ture
       Man m1 = (Man)p;
       m1.earnMoney();
   }
   ```

   其中,如果B是A的父类,则a instanceof B也返回ture

   ```java
   if(p instanceof Man){   //ture
       Man m1 = (Man)p;
       m1.earnMoney();
   }
   
   if(p instanceof Person){   //ture
     
   }
   if(p instanceof Object){   //ture
   
   }
   ```

   

### Object类

> java.lang.Object类

1. Object类是所有Java类的根父类

2. 如果在类的声明中未使用extends关键字指明其父类,则默认父类为java.lang.Object类

3. Object类中的功能(属性和方法)就具有通用性

   属性 : 无

   方法 : equals() / toString() / getClass() / hashCode() / clone() / finalize() / wait() / notify() , notifyAll()

4. Object只声明了一个空参构造器



#### equals()

1. 回顾 == 的使用

   == : 运算符

   ① 可以使用在基本数据类型变量和引用数据类型变量中

   ② 	如果比较的是基本数据类型变量 : 比较两个变量保存的数据是否相等.(不一定类型相同)

   ​	**如果比较的是引用数据类型变量 : 比较两个对象的地址值是否相同**

   ```java
   int i=10;
   int j=10;
   
   System.out.println(i==j);//ture
   
   double d = 10.0;
   System.out.println(i==d);//ture
   
   boolean b = ture;
   //System.out.println(i==j);不能比较
   
   char c = 10;
   System.out.println(i==c); // ture
   
   char c1 = 'A';
   char c2 = 65;
   System.out.println(c1==c2); //ture
   ```

   ```java
   String str1 = new String("atguigu");
   String str2 = new String("atguigu");
   System.out.println(str1==str2); //false
   
   Customer cust1 = new Customer("Tom",21);
   Customer cust2 = new Customer("Tom",21);
   System.out.println(cust1==cust2);   //false
   
   ```

2. equals()方法的使用

   1. 是一个方法,而非运算符
   2. 只能适用于引用数据类型
   3. **Object类中equals()的定义 : 作用与 == 相同**

   		public boolean equals(Object obj){

   			return  (this == 	obj);
			
   		}

   4. 像**String , Data ,File ,包装类等都重写了Object类中的equals()方法,**重写以后,比较的不是两个引用的地址是否相同,而是**比较两个对象的"实体内容"是否相同**

```java
String str1 = new String("atguigu");
String str2 = new String("atguigu");
System.out.println(str1==str2); //false

Customer cust1 = new Customer("Tom",21);
Customer cust2 = new Customer("Tom",21);
System.out.println(cust1==cust2);   //falseString str1 = new String("atguigu");

System.out.println(cust1.equals(cust2));// false  ,Object中的equals()
System.out.println(str1.equals(str2));  // ture   ,String重写的equals()


```

​	**5. 我们自定义的类通常也要进行重写**

```java
//对cust1进行重写    //cust1.equals(cust2);

public boolean equals(Object obj){
	
    if( this==obj){   //比较两个对象的地址
        return ture;
    }
    if(obj instanceof Customer){ //判断obj是不是Customer类
		Customer cust = (Customer)obj;
        //比较两个对象的每个属性是否相同
        if(this.age == cust.age && this.name.equals(cust.age)){
            return ture;
        }else{
            return false;
        }
 //return (this.age == cust.age && this.name.equals(cust.age));   //这个与上面效果相同
    }

    return false;
}
```



#### toString()

1. 当我们输出一个对象的引用时,实际上就是调用当前对象的toString() >>>**Object类中toString()输出地址值**

2. Object类中toString()的定义 : 

   public String toString(){

   ​	return getClass().getName() + "@" + Integer.toHexString(hashCode());

   }

3. 像**String , Date ,File ,包装类等都重写了Object类中的toString()方法**

   使得在调用对象的toString()时 , 返回"实体内容"信息

4. **自定义类也可以重写toString()方法,作用一般是返回实体内容信息**





### 包装类

> 1. java提供了8种基本数据类型对应的包装类,使得基本数据类型的变量具有类的特征
> 2. 要求掌握 : 基本数据类型 , 包装类 , String 三者之间的互相转换



#### 基本数据类型转换为包装类

1. **基本数据类型和包装类**

   > 调用包装类的构造器

   ```java
   public class WrapperTest{
       public static void main(String[] args){
   
           int num1 = 10;
           
           Integer in1 = new Integer(num1);
           System.out.println(in1.toString());
           
           Integer in2 = new Integer("123");
           System.out.println(in2.toString());
           
           Boolean b1 = new Boolean(true);
           Boolean b2 = new Boolean(TRue);
           System.out.println(b2);  //true
           
           Boolean b3 = new Boolean(true123);
           System.out.println(b3); //false
           
           Order order = new Order();
           System.out.println(order.isMale); //false
           System.out.println(order.isFemale);  //full
       } 
   }
   class Order{
   	
       boolean isMale;
       Boolean isFemale;
   }
   ```

2. **包装类转换为基本数据类型**

   > 调用包装类Xxx的xxxvalue()

   ```java
   Integer in1 = new Integer(12);
   int i1 = in1.intValue();
   i1++;
   
   Float f1 = new Float(12.3);
   float f2 = f1.floatValue();
   ```

#### 自动装箱与自动拆箱

1. 自动装箱  :  基本数据类型 >>>  包装类

   ```java
   int num1 = 10;
   Integer in1 = num1; //Integer in1 = new Integer(num1);
   ```

2. 自动拆箱  :  包装类  >>>  基本数据类型

   ```java
   Integer in1;
   int i1 = in1;  //  int i1 = in1.intValue();
   ```



#### String类型和包装类

1. 基本数据类型 , 包装类 >>>>>String类型

   ```java
   //方式一 : 连接运算
   String str1 = num1 + "" ;
   //方式二 : 调用String的valueOf()
   float f1 = 12.3 ; 
   String str2 = String.valueOf(f1); //"12.3"
   
   Double d1 = new Double(12.3);
   String str3 = String.valueOf(d1); //"12.3"
   ```

   

2. String类型  >>>>>> 基本数据类型 , 包装类 : 调用包装类的parseXxx()

   ```java
   //可能会报NumberFormatException
   
   String str1 = "123";
   int num1 = Integer.parseInt(str1);
   
   String str2 = "true1";
   boolean b1 = Boolean.parseBoolean(str2);  //
   ```



### 单例设计模式

> 采取一定的方法保证在整个软件系统中,对于某个类只能存在以个对象实例



#### 饿汉式

```java
calss Bank{

    //1.私有化类的构造器
    private Bank(){
        
    }
    
    //2.内部创建类的对象
    //4.要求此对象也必须声明为静态的
    privat static Bank instance = new Bank();
    
    //3.提供公共的静态方法,返回类的对象
    public static Bank getInstance(){

        return instance;
    }
    
}
```





#### 懒汉式

```java
calss Bank{

    //1.私有化类的构造器
    private Bank(){
        
    }
    
    //2.内部创建类的对象
    //4.要求此对象也必须声明为静态的
    privat static Bank instance = null;
    
    //3.提供公共的静态方法,返回类的对象
    public static Bank getInstance(){
		
        if(instance == null){
            instance = new Bank();
        }
        return instance;
    }
    
}
```







### 其他关键字

#### return

```java
retuen 0;
```



#### package

1. 为了更好的实现项目中类的管理,提供包的概念

2. 使用package声明类或接口所属的包,声明在源文件的首行

3. 包,属于标识符,遵循标识符的命名规则,规范

4. 每" . "一次,就代表一层文件目录

   > 同一个包下,不能命名同名的接口,类.

```java
package com.atguigu.exer.java;
```



#### import

> 导包

1. 在源文件中显式的使用import结构导入指定包下的类,接口
2. 声明在包的声明和类的声明之间
3. 如果需要导入多个结构,则并列写出即可
4. 可以使用"xxx.*"的方式,表示导入xxx包下的所有结构
5. 如果使用的类或接口是java.lang包下定义的,则可以省略import结构(如 String)
6. 如果使用的类或接口是本包下定义的,则可以省略import结构
7. 如果在源文件中,使用了不同包下的同名的类,则必须至少有一个类需要以全类名的方式显示.
8. 使用" xxx.* "方式表明可以调用xxx包下的所有结构 ,但是如果使用的是xxx子包下的结构,则仍需要显式导入



9. import static : 导入指定类或接口中的静态结构 : 属性或方法

```java
package com.atguigu.java2;

// import java.util.Arrays;
// import java.util.Arrays;
   import java.util.*;
   import com.atguigu.exer4.Bank;

public class ImportTest{
    public static void main(String[] args){
        
        String info = Array.toString(new int[]{1,2,3});
        Bank bank = new Bank();
        ArrayList list = new ArrayList();
        
        Person p = new Person();
        
        //全类名
        com.atguigu.exer3.Account acct1 = com.atguigu.exer3.Account(1000,2000,0.0123);
    }
}

class Person{//本包下

}
```



#### static

1. static : 静态的

2. static可以用来修饰 : 属性 , 方法 , 代码块 , 内部类

3. **使用static修饰属性 : 静态变量**(或类变量)

   > 属性 :  按是否使用static修饰 分为 : 静态属性  和   非静态属性(实例变量)
   >
   > 实例变量 : 我们创建了类的多个对象 , 每个对象都独立的拥有一套类中的非静态属性 .修改时,不影响其他						   对象中的
   >
   > 静态变量 : 我们创建了类的多个对象 , 多个对象共享同一个静态变量 , 修改后 所有对象的静态变量同时修改

   >static修饰属性的其他说明 : 
   >
   >1. 静态变量随着类的加载而加载.可以通过"类.静态变量"的方式调用
   >2. 静态变量的加载要早于对象的创建
   >3. 由于类只加载一次,则静态变量在内存中也只存在一份 : 存在方法区的静态域中.

4. **使用static修饰方法** : **静态方法**

   > ①随着类的加载而加载 , 可以通过"类.方法"的方法调用
   >
   > ②静态方法中,只能调用静态的方法和属性
   >
   > ​    非静态方法 , 既可以调用静态的,也可以调用非静态的



#### final

1. final可以修饰的结构 : 类 , 方法 , 变量

2. final用来修饰一个类 : 此类不能被继承

   ​			比如  :  String类 , System类 , StringBuffer类

   ```java
   final class A{//此类不能被继承
   
   }
   ```

3. final用来修饰方法 : 此方法不能被重写

   ​			比如 : Object类中的getClass();

   ```java
   class A{
   
       public final void show(){ // 此方法不能被重写
           
       }
   }
   class B extends A{
       
       
   }
   ```

4. **final修饰变量(属性和局部变量) : 此时的"变量"是一个常量**

   ​	**修饰属性 : 只能显式初始化  ,  代码块中初始化 , 构造器中初始化**

   ​	修饰局部变量(方法内,形参) : 

   ```java
   class A{
   
       public void show(){
   
           final int a = 10;
       }
       public void showA(final int age){
   
       }
   }
   ```

    

   **static final 修饰属性 : 全局常量**	







## 抽象类



### abstract

1. abstract可以用来修饰的结构 : 类 , 方法

2. **abstract修饰类 : 抽象类**

   > **①此类不能实例化**
   >
   > **②抽象类中一定有构造器,便于子类实例化时调用**
   >
   > **③开发中 , 都会提供抽象类的子类 , 让子类实例化 ,完成相关操作**

   ```java
   abstract class A{
       
   }
   class B extends A{
   
   }
   ```

   

3. **abstract修饰方法 : 抽象方法**

   > ①**抽象方法只有方法的声明,没有方法体**
   >
   > ②包含抽象方法的类 , 必须是抽象类
   >
   > ③**子类必须重写父类中所有的抽象方法 ,否则, 子类也必须是抽象类**

   ```java
   abstract class Person{
   	
       public abstract void eat();  //抽象方法
       
       public void study(){
   
       }
   }
   
   class Student extends Person{
   	
       public void eat(){  //抽象父类中的抽象方法
           
       }
   }
   ```

**说明 : abstract不能修饰 : 私有方法,静态方法,final的方法,final的类**



4. 创建抽象类的匿名子类对象

   ```java
   Person p = new Person(){  // Person是抽象类 , 创建一个匿名子类对象 
       
       public void eat(){   //重写父类的抽象方法
           
       }
   }
   ```



## 接口

1. 接口使用interface来定义

2. Java中 , 接口和类是并列的

3. 如何定义接口 : 定义**接口中的成员**

   > **3.1 JDK7及以前 : 只能定义全局常量和抽象方法**
   >
   > ​	全局常量 : public static final 的 , 可以省略
   >
   > ​	抽象方法 : public abstract 的 , 可以省略
   >
   > **3.2 JDK8 : 除了全局处理和抽象方法 , 还可以定义默认方法和静态方法**

4. 接口中不能定义构造器 .也就是说,接口不能实例化

5. Java开发中,接口通过类去实现(implements)的方法来使用 ,此类被称为实现类

   > 注意 : 实现类必须覆盖接口中所有的抽象方法 , 否则 此实现类是一个抽象类

   ```java
   public class InterfaceTest{
       
   }
   
   interface Flyable{  //和类是并列的
       //定义全局常量
       public static final int age; 
       int name;   //省略了 public static final
       
       //定义抽象方法
       public abstract void fly();
       void stop(); // 省略了public abstract
       
   }
   
   class Plane implements Flyable{ //实现Flyable接口的类
       
       public void fly(){  //覆盖接口的抽象方法
           
       }
       void stop(){
           
       }
   }
   ```

6. java类可以实现多个接口  >>>>  弥补了单继承的局限性

   ```java
   interface A{
   
   }
   interface B{
       
   }
   class C{
   
   }
   class D extends C implements A,B{
   }
   ```

7. 接口和接口之间可以多继承

   ```java
   interface AA{
   
   }
   interface BB{
   
   }
   interface CC extends AA,BB{  //接口可以多继承
   
   }
   ```

   





##异常处理

> java.lang.Throwable : 
>
> ​		java.lang.Error : 一般不编写针对性的代码进行处理
>
> ​		java.lang.Exception(编译时异常和运行时异常) : 可以进行异常的处理

抓抛沫型 : 

​	过程一 : " 抛" ,程序在正常执行的过程中,一旦出现异常,就会在异常代码处生成一个对象异常类的对象,并将此	对象抛出. 一旦抛出对象以后 , 其后的代码就不再执行.

​			关于异常对象的产生 : ①系统自动生成的异常对象

​								②手动生成一个异常对象,并抛出(throw)

​	过程二 : " 抓" : 异常的处理方式 : ①try-catch-finally	②throws 



### try-catch-finally

**异常处理的方式1 :** 

```java
try{
	//可能出现异常的代码
}catch(异常类型1 变量1){
	//处理异常的方式1
}catch(异常类型2 变量2){
	//处理异常的方式2
}...
finally{
	//一定会执行的代码
}
```

try-catch的说明 : 

> 1. finally是可选的
> 2. 使用try将可能出现的代码包起来,一旦出现异常,会生成一个对应异常类的对象,根据此对象的类型去catch匹配
> 3. 一旦try中出现的异常匹配到某一个catch,就进入catch进行异常处理.处理完成后继续执行try-catch结构之后的代码
> 4. catch中的异常类型如果满足子父类关系,则要求子类声明在父类的上面
> 5. 常用的异常处理方式 : ①String getMessage()  ②printStackTrace()
> 6. 在try结构中声明的变量,在出了try结构以后,就不能被调用

```java
public class ExceptionTest{
    
    public void test1(){
        String str = "123";
        str = "abc";
        try{
			int num = Integer.parseInt(str);
        }catch(NumberFormatException e){
			System.out.println("出现数组转换异常了...");
        }catch(NullPointException e){
             System.out.println("出现空指针异常了...");
        }catch(Exception e){  	//父类写在子类下面

        }
        
        
        System.out.println("Hello..")
    }
}
```

**try-catch结构可以嵌套**

finally的说明 : 

> 1. finally是可选的
> 2. finally中声明的是一定会被执行的代码.即使catch中又出现异常了,try中有return语句,catch中有return语句的情况
> 3. 像数据库连接,输入输出流,网络变成Socket等资源.JVM是不能自动回收的,我们需要自己手动进行资源释放,此时的资源释放,就需要声明在finally中.

```java
public class finallyTest{
    public void test(){
        
        FileInputStream fis = null ;  
        
        try{ 
			fis = new FileInputStream(file);  //可以理解为打开文件
        }catch(){

        }finally{
            try{    //try-catch结构可以嵌套
				fis.close();   //关闭文件
            }catch(){
                
            }
        }
    }
}
```

总结 : 

> ①使用try-catch-finally处理编译时异常,使得程序在编译时就不在报错,但是运行时仍可能报错.相当于我们将一个编译时可能出现的异常,延迟到运行时出现
>
> ②运行时异常通常不进行异常处理.而编译时异常,一定要异常处理



### throws

异常处理的方式2 : throws + 异常类型

> 1. "throws 异常类型" 写在方法的声明处.指明此方法执行时,可能会抛出的异常类型. 当方法体执行时出现异常,仍会生成一个异常类的对象,此对象满足throws后的异常类型后就会被抛出.异常代码后续的代码,就不再执行.
>
> 2. throws的方式只是将异常抛给了方法的调用者,并没有真正将异常处理掉
>
> 3. 开发中的如何使用: 
>
>    **3.1 如果父类被重写的方法没有用throws方式处理异常,则子类重写的方法也不能使用throws,应该使用try-catch-finally方式处理**
>
>    3.2 

```java
public class ExceptionTest{
	
    public static void main(String[] args){
        try{  
            method2();
        }catch(IOException e){

        }
        
    }
    
    public static void method2() throws IOException{
		method1();  //此方法的异常未被处理 , 所有还要向上抛
    }
    
    public static void method1() throws IOException{
        
    }
}
```



### throw

```java
public class ThrowTest{
	public static void main(String[] args){

        Student s = new Student();
        try{    //处理手动抛出的异常
            s.regist(-1001);
        }catch(Exception e){
			System.out.println(e.getMessage());
        }
        
    }
}

class Student{

    private int id;
    
    public void regist(int id) throws Excetion{ //抛出  手动抛出的异常
        if(id>0){
            this.id = id;
        }else{
			// System.out.println("您输入的数值非法!");
            throw new Exception("您输入的数值非法!");  //手动抛出的异常
        }
    }
}
```



### 自定义异常类

> 1. 继承于现有的异常结构 : RuntimeException , Exception
> 2. 提供全局常量 : serialVersionUID
> 3. 提供重载的构造器

```java
public class MyException{
    
    static final long serialVersionUID = -7034897190745766939L; // 标识这个类
    
    public MyException(){

    }
    
    public MyException(String s){
		super(s);
    }
}
```





## 多线程



### 基本概念 : 程序 , 进程 , 线程

* 程序

* 进程

* 线程

* 并行和并发 : 并行 , 多个CPU同时执行多个任务

  ​			并发,一个CPU同时执行多个任务

多线程的优点 : 

> 1. 提高应用程序的响应.对图形化界面更有意义,可增强用户体验
> 2. 提高计算机系统cpu的利用率
> 3. 改善程序结构.将既长又复杂的进程分为多个线程,独立运行,利于理解和修改



### 线程的创建和使用

![Snipaste_2022-09-05_20-54-05](E:\截图\Snipaste_2022-09-05_20-54-05.png)

####方式一 : 继承于Thread类

> 1. 创建一个继承于Thread类的子类
> 2. 重写Thread类的run()   >>>将此线程执行的操作声明在run()中
> 3. 创建Thread类的子类的对象
> 4. 通过此对象调用start()

```java
//1.创建一个继承于Thread类的子类
class MyThread extends Thread{
    //2.重写Thread类的run()
    public void run(){  //将要执行的操作声明在run()中
         for (int i = 0; i < 100; i++) {
            if (i%2 == 0) {
                System.out.println(i);
            }
         }
    }
}

public class ThreadTest {
    public static void main(String[] args) {
        //3.创建Thread类的子类的对象
        MyThread t1 = new MyThread();
        //4.用子类对象调用start()
        t1.start();
    }
}    
```

**两个问题 : ①我们不能直接调用run()的方式启动线程 ②再启动一个线程,不可以让已经start()的线程去执行**



#### 方式二 : 实现Runnable接口

> 1. 创建一个实现了Runnable接口的类
> 2. 实现类去覆盖Runnable中的抽象方法: run()
> 3. 创建实现类的对象
> 4. 将此对象作为参数传递到Thread类的构造器中,创建Thread类的对象
> 5. 通过Thread类的对象调用start()

```java
public class ThreadTest2 {
    public static void main(String[] args) {

        MyThread2 t2 = new MyThread2(); //3.创建实现类的对象
        Thread p = new Thread(t2);   //4.创建Thread类的对象,将实现类的对象作为参数传入Thread的构造器
        p.start();                      //5.通过Thread类的对象调用start()
    }
}

//1.创建一个实现Runnable接口的类
class MyThread2 implements Runnable{

    @Override
    public void run() {        //2.覆盖Runnable接口的run()
        for (int i = 0; i < 100; i++) {
            if (i%2 == 0) {
                System.out.println(i);
            }
        }
    }
}
```



#### 线程的优先级

> 1. MAX_PRIORITY  : 10
>
>    MIN_PRIORITY : 1
>
>    NORM_PRIORITY : 5   >>>>>默认优先级
>
> 2.如何获取和设置当前线程的优先级
>
> ​	getPriority() : 获取线程的优先级
>
> ​	setPriority(int p) : 设置线程的优先级

```java
public class ThreadTest{
    public static void main(String[] args){
        MyThread t1 = new MyThread();
        t1.setPriority(Thread.MAX_PRIORITY); //设置分线程的优先级
        t1.start();
        
        //设置主线程的优先级
        Thread.currentThread().setPriority(MIN_PRIORITY);
        
        //
    }
}
```

说明 : 高优先级的线程要抢占低优先级线程cpu的执行权.但只是从概率上讲,cpu分配的概率比较大,不是说高的执行完之后才执行低的



### 线程的生命周期

![Snipaste_2022-09-06_13-32-56](E:\截图\Snipaste_2022-09-06_13-32-56.png)





### 线程的同步

> 在Java中,我们通过同步机制,来解决线程安全的问题



#### 同步代码块

> synchronized(同步监视器){
>
> ​		//需要被同步的代码
>
> }

说明 : 1. 操作共享数据的代码,即为需要被同步的代码

​	   2.共享数据 : 多个线程共同操作的变量.比如 : ticket就是共享数据

​	   3.同步监视器,俗称: **锁**.任何一个类的对象,都可以充当锁.**要求 : 多个线程必须共用同一把锁**

我们可以考虑this来充当同步监视器,但是要慎用

```java
//解决实现Runnable接口的线程安全问题
class Windows implements Runnable{

    private int ticket = 100;
    Object obj = new Object();  //锁

    public void run() {
        synchronized (obj) {  // 同步代码块
            while (true) {
                if (ticket > 0) {

                    try{
                        Thread.sleep(100);
                    }catch (InterruptedException e){
                        e.printStackTrace();
                    }
                    System.out.println(Thread.currentThread().getName() + "已出票,票号是 :  " + ticket);
                    ticket--;
                }else {
                    break;
                }

            }
        }
    }
}
```

```java
//解决继承Thread类的线程安全问题
public class WindowTest2 {
    public static void main(String[] args) {

        Window1 w1 = new Window1();
        Window1 w2 = new Window1();
        Window1 w3 = new Window1();

        w1.setName("窗口1");
        w2.setName("窗口2");
        w3.setName("窗口3");

        w1.start();
        w2.start();
        w3.start();
    }

}
class Window1 extends Thread{
    private static int ticket = 100;
    static Object obj = new Object();

    public void run() {
            while (true){
                synchronized (obj){ //同步代码块
//                    synchronized (Window1.class){  //这种方法也可以  //Window1唯一的对象
                    if (ticket > 0) {

                        try{
                            Thread.sleep(100);
                        }catch (InterruptedException e){
                            e.printStackTrace();
                        }
                        System.out.println(Thread.currentThread().getName() + "已出票,票号是 :  " + ticket);
                        ticket--;
                    }else {
                        break;
                    }

                }

            }
    }
}
```



#### 同步方法



```java
//使用同步方法解决实现Runnable接口的线程安全问题
class WindowsTest3 {
    public static void main(String[] args) {

        Window3 w1 = new Window3();
        Thread n1 = new Thread(w1);
        Thread n2 = new Thread(w1);
        Thread n3 = new Thread(w1);

        n1.setName("窗口1");
        n2.setName("窗口2");
        n3.setName("窗口3");

        n2.start();
        n1.start();
        n3.start();

    }
}

class Window3 implements Runnable{
    private int ticket = 100;
    Object obj = new Object();

    public void run() {
        while (true) {
            show();
        }
    }
    //同步方法处理
    public synchronized void show(){  //使用了默认的同步监视器 : this
        if (ticket > 0) {
            try{
                Thread.sleep(100);
            }catch (InterruptedException e){
                e.printStackTrace();
            }
            System.out.println(Thread.currentThread().getName() + "已出票,票号是 :  " + ticket);
            ticket--;
        }
    }
}
```

```java
//使用同步方法使用解决继承Thread类的线程安全问题
public class WindowTest4 {
    public static void main(String[] args) {

        Window4 w1 = new Window4();
        Window4 w2 = new Window4();
        Window4 w3 = new Window4();

        w1.setName("窗口1");
        w2.setName("窗口2");
        w3.setName("窗口3");

        w1.start();
        w2.start();
        w3.start();
    }

}
class Window4 extends Thread{
    private static int ticket = 100;
 
    public void run() {
        while (true){
                show();
        }
    }
    //同步方法处理
    private static synchronized void show(){ //同步监视器 : Window4.class
        if (ticket > 0) {

            try{
                Thread.sleep(100);
            }catch (InterruptedException e){
                e.printStackTrace();
            }
            System.out.println(Thread.currentThread().getName() + "已出票,票号是 :  " + ticket);
            ticket--;
        }
    }
}
```

关于同步方法的总结 : 

1. 同步方法仍然涉及到同步监视器,只是不需要我们显式的声明.

2. 非静态的同步方法,同步监视器是 : this

   静态的同步方法,同步监视器是 : 当前类本身



#### 线程死锁

1. 死锁的理解 : 不同的线程分别占用对方需要的同步资源不放弃,都在等待对方放弃自己需要的同步资源,就形成了线程死锁

2. 说明 : 

   ①出现死锁后,不会出现异常,不会出现提示,只是所有的线程都处于阻塞状态,无法继续

   ②我们使用同步时,要避免出现死锁.



#### Lock

> JDK5.0新增 >>>>>>  解决线程安全的方式三

```java
public class LockTest {
    public static void main(String[] args) {

        Window5 w5 = new Window5();

        Thread t1 = new Thread(w5);
        Thread t2 = new Thread(w5);
        Thread t3 = new Thread(w5);

        t1.start();
        t2.start();
        t3.start();
    }
}

class Window5 implements Runnable{

    private int ticket = 100;
    //实例化ReentrantLock
    private ReentrantLock lock = new ReentrantLock();
    @Override
    public void run() {
        while (true) {
            try{
                //2.调用锁定方法 : lock()
                lock.lock();
                if (ticket > 0) {
                    try{
                        Thread.sleep(100);
                    }catch (InterruptedException e){
                        e.printStackTrace();
                    }
                    System.out.println(Thread.currentThread().getName() + "已出票,票号是 :  " + ticket);
                    ticket--;
                }else {
                    break;
                }
            }finally {
                //3.调用解锁方法 : unlock
                lock.unlock();
            }
        }
    }
}
```

总结 : synchronized与Lock的异同

相同 : 二者都可以解决线程安全问题

不同 : synchronized机制在执行完相应的同步代码以后,自动的释放同步监视器

​	   Lock需要手动的启动同步(lock()) , 同时结束同步也需要手动的实现(unlock())





### 线程的通信

> 交替打印

三个方法 : 

1. wait() : 一旦执行此方法,当前线程就进入阻塞状态,并释放同步监视器
2. notify() : 一旦执行此方法,就会唤醒一个被wait的线程.如果有多个线程被wait,就唤醒优先级高的
3. notifyAll() : 一旦执行此方法,就会唤醒所有被wait的线程

说明 : 

1. 这三个方法必须使用在同步代码块或同步方法中
2. 这三个方法的调用这必须是同步代码块或同步方法中的同步监视器,否则,会出现IllegalMonitorStateException
3. 这三个方法是定义在java.lang.Object类中的

```Java
public class CommunicationTest {
    public static void main(String[] args) {
        Communication c = new Communication();
        Thread t1 = new Thread(c);
        Thread t2 = new Thread(c);

        t1.start();
        t2.start();
    }
}

class Communication implements Runnable{
    private int number = 1;
    @Override
    public void run() {
        while (true){
            synchronized (this) { //obj
                notify();         //obj.notify()
                if(number<=100){
                    System.out.println(Thread.currentThread() + "已输出 :" + number);
                    number++;

                    try {
                        wait();	//obj.notify()
                    } catch (InterruptedException e) {
                        throw new RuntimeException(e);
                    }
                }else{
                    break;
                }
            }
        }
    }
}
```

sleep()和wait()的异同

1. 相同点 : 一旦执行,都会使当前的线程进入阻塞状态

2. 不同的 : ①两个方法声明的位置不同:Thread类中声明sleep() ,Object类中声明wait

   ​		②调用的要求不同: sleep()可以在任何需要的场景调用 , wait()必须通过同步监视器调用

   ​		③如果两个方法都使用在同步代码块或同步方法中,sleep()不会释放锁,wait()会释放锁



### JDK5.0新增线程创建方式



#### 方式三 : 实现Callable接口

> 1. 创建实现Callable接口的实现类
> 2. 实现接口中的call()方法,将此线程需要执行的操作声明在call()中
> 3. 创建实现类的对象
> 4. 创建FutureTask类的对象,将实现Callable接口的类的对象作为参数传入FutureTask构造器中
> 5. 创建Thread的对象,将FutureTask类的对象作为参数传入Thread的构造器,并调用start()
> 6. 使用FutureTask中的get()获取Callable中call()的返回值

```java
public class ThreadNew {
    public static void main(String[] args) {
		//3.创建实现类的对象
        NumThread numThread = new NumThread();
        //4.创建FutureTask类的对象,将实现Callable接口的类的对象作为参数传入FutureTask构造器中
        FutureTask futureTask = new FutureTask(numThread);
        //5.创建Thread的对象,将FutureTask类的对象作为参数传入Thread的构造器,并调用start()
        new Thread(futureTask).start();
        try {
            //6.获取Callable中call()的返回值
            //get()的返回值FutureTask构造器的参数Callable实现类重写的call()的返回值
            // Object o1 = futureTask.get();
            System.out.println("总和为 : " + futureTask.get());
        } catch (InterruptedException e) {
            throw new RuntimeException(e);
        } catch (ExecutionException e) {
            throw new RuntimeException(e);
        }
    }
}
//1.创建实现Callable接口的实现类
class NumThread implements Callable {

    //2.实现接口中的call()方法,将此线程需要执行的操作声明在call()中
    @Override
    public Object call() throws Exception {
        int sum = 0;
        for (int i = 1; i <= 100; i++) {
            if (i % 2 == 0) {
                System.out.println(i);
                sum += i;
            }
        }
        return sum;
    }
}
```

说明 : 通过Callable接口创建多线程比Runnable接口更强大

1. call()可以有返回值
2. call()可以抛出异常,被外面的操作捕获,获取异常信息
3. Callable是支持泛型的



#### 方式四 : 使用线程池

![Snipaste_2022-09-07_19-45-21](E:\截图\Snipaste_2022-09-07_19-45-21.png)

![Snipaste_2022-09-07_19-46-42](E:\截图\Snipaste_2022-09-07_19-46-42.png)



> 1. 创建一个提供指定线程数量的线程池
>
> 2. 执行指定的线程的操作.需要提供实现Runnable接口或Callable接口的类的对象
> 3. 关闭线程池

```java
public class ThreadPool {
    public static void main(String[] args) {
        //1.创建一个提供指定线程数量的线程池
        ExecutorService service = Executors.newFixedThreadPool(10);
        ThreadPoolExecutor service1 = (ThreadPoolExecutor)service;
        //设置线程池的属性
//		System.out.println(service.getClass());
        service1.setcorePoolSize(15);
        
        //2.执行指定的线程的操作.需要提供实现Runnable接口或Callable接口的类的对象
        service.execute(new NumberThread()); // 适合适用于Runnable
        service.execute(new NumberThread1());// 适合适用于Runnable
        
//        service.submit();   //适合用于Callable
        //3.关闭线程池
        service.shutdown();
    }
}

class NumberThread implements Runnable{
    @Override
    public void run() {
        for (int i = 0; i <=100; i++) {
            if(i%2==0){
                System.out.println(Thread.currentThread().getName() +"输出 : " + i);
            }

        }
    }
}
class NumberThread1 implements Runnable{
    @Override
    public void run() {
        for (int i = 0; i <=100; i++) {
            if(i%2!=0){
                System.out.println(Thread.currentThread().getName() +"输出 : " + i);
            }

        }
    }
}
```



## 常用类

### String

**string : 字符串,使用一对""引起来表示****

1. **String声明为final,不可被继承**

2. **String实现了Seriallizable接口 : 表示字符串是支持序列化的**

   **​	实现了Comparable接口 : 表示 String 可以比较大小**

3. **String内部定义了final char[] value : 用于存储字符串数据**

4. **String代表不可变的字符序列 . 简称 : 不可变性**

   **体现 :  1. 当对字符串重新赋值时,需要重新指定内存区域赋值,不能使用原有的value进行赋值**

   ​	    **2.当对现有的字符串进行连接操作时,也需要重新指定内存区域赋值,不能使用原有的value**

    	    **3.当调用String的replace()方法修改指定字符或字符串时,也需要重新指定内存区域赋值**

5. **通过字面量的方式(区别于new)给一个字符串赋值,此时的字符串值声明在字符串常量池中**

6. **字符串常量池中是不会存储相同内容的字符串的**



1. String的实例化

![Snipaste_2022-09-08_10-20-21](E:\截图\Snipaste_2022-09-08_10-20-21.png)

2. **String不同实例化的对比**

方式一 : 通过字面量定义的方式

方式二 : 通过new  + 构造器的方式

```java
public class PersonTest{
    
    public static void main(String[] args){

        Person p1 = new Person("Tom",12);
        Person p2 = new Person("Tom",12);
    System.out.println(p1.name == p2.name);//true 创建了两个对象,分别给name赋值,都指向了字符串常量池
    }
}
class Person{
    String name;
    int age;
    
    public Person(String name,int age){
		this.name=name;
        this.age = age;
    }
}
```



3. String 不同拼接操作的对比

结论 : ①常量与常量的拼接结果在常量池.且常量池中不会存在相同内容的常量

​	   ②只要其中有一个是变量,结果就在堆中

​	   ③如果拼接的结果调用intern()方法 , 返回值就在常量池中

```java
public void test(){
    String s1 = "JavaEE";
    String s2 = "hadoop";
    
    String s3 = "JavaEEhadoop";
    String s4 = "JavaEE" + "hadoop";
    String s5 = s1 + "hadoop";
    String s6 = "JavaEE" + s2;
    String s7 = s1 + s2;
    
    System.out.println(s3 == s4);//ture
    System.out.println(s3 == s5);//false
    System.out.println(s3 == s6);//false
    System.out.println(s3 == s7);//false
    System.out.println(s5 == s6);//false
    System.out.println(s5 == s7);//false
    System.out.println(s6 == s7);//false
    
    String s8 = s5.intern();
    System.out.println(s3 == s8);//ture // 返回值是常量池中已经存在的"JavaEEhadoop"
}
```



4. String的常用方法

![Snipaste_2022-09-08_11-04-49](E:\截图\Snipaste_2022-09-08_11-04-49.png)

![Snipaste_2022-09-08_11-10-45](E:\截图\Snipaste_2022-09-08_11-10-45.png)

![Snipaste_2022-09-08_11-22-15](E:\截图\Snipaste_2022-09-08_11-22-15.png)



5. **String与char[]之间的转换**

String >>>>>char[] : 调用String的toCharArray()方法

char[] >>>>>String : 调用String的构造器

```java
public static void main(String[] args) {

        String str1 = "abc123";
        char[] charArray = str1.toCharArray();
        for (int i = 0; i <charArray.length ; i++) {
            System.out.println(charArray[i]);
        }

        char arr[] = new char[]{'h','e','l','l','o'};
        String str2 = new String(arr);
        System.out.println(str2);

    }
```



6. String与byte[]之间的转换

编码 : String >>>>> byte[] : 调用String的getBytes()方法

解码 : byte[] >>>>> String : 调用String的构造器

```java
public static void main(String[] args) throws UnsupportedEncodingException {

        String str1 = "abc123中国";
        byte[] bytes = str1.getBytes();  //使用默认的字符集,进行编码
        byte[] gbks = str1.getBytes("gbk"); // 使用指定的gbk字符集进行编码

        String str2 = new String(bytes); //解码
        System.out.println(str2);
    }
```

说明 : 解码时,要求解码使用的字符集必须与编码时使用的字符集一致,否则会出现乱码



### StringBuffer,StringBuilder

1. String,StringBuffer,StringBuilder三者的异同?

> String : 不可变的字符序列 ,底层使用char[]存储
>
> StringBuffer : 可变的字符序列 ; 线程安全的 , 效率低,底层使用char[]存储
>
> StringBuilder : 可变的字符序列 ; jdk5.0新增的,线程不安全的,效率高,底层使用char[]存储



2. StringBuffer源码分析 : 

```java
String str1 = new String();	//char[] value = new char[0];
String str2 = new String("abc"); //char[] value = new char[]{'a','b','c'};

StringBuffer sb1 = new StringBuffer();  //char[] value = new char[16];底层创建了一个长度16的数组
System.out.println(sb1.length()); // 0
sb1.append('a'); //value[0] = a;
sb1.append('b'); //value[1] = b;

StringBuffer sb2 = new StringBuffer("abc"); 
//char[] value = new char["abc".length + 16];
```

问题一 : System.out.println(sb2.length); //3

问题二 : 扩容问题 : 如果要添加的数据太长,底层数组装不下了,那就需要扩容底层的数组

​		默认情况下,扩容为原来容量的2倍 + 2,同时将原有数组的元素复制到新的数组



3. StringBuffer类中的常用方法

![Snipaste_2022-09-08_16-20-24](E:\截图\Snipaste_2022-09-08_16-20-24.png)

![Snipaste_2022-09-08_16-21-26](E:\截图\Snipaste_2022-09-08_16-21-26.png)



### jdk8之前日期时间的API

1. System类中的currentTimeMillis()方法 :

```java
long time = System.currentTimeMillis();
//返回当前时间与1970年1月1日0时0分0秒的时间差 , 单位 : 毫秒
//称为 : 时间戳
System.out.println(time);
```



2. Date类

> java.util.Date类
>
> ​	|>>>java.sql.Date类    :   对应着数据库中的日期类型的变量

**①两个构造器的使用 :** 

​	构造器一 : Date() : 创建一个对应当前时间的Date对象

​	构造器二 : 创建指定毫秒数的Date对象

```java
Date date1 = new Date();
System.out.println(date1.toString); //显示当前的年月日
System.out.println(date1.getTime());  //显示毫秒数
```

**②两个方法的使用 :** 

​	toString() : 显示当前的年,月,日,时,分,秒.

​	getTime() : 获取当前Date对象对应的毫秒数. (时间戳)

​	

3. SimpleDateFormat类

> 格式化 : 日期 >>>字符串
>
> 解析 : 字符串 >>>日期

```java
public class DateTimeTest {
    public static void main(String[] args) throws ParseException {
        SimpleDateFormat sdf = new SimpleDateFormat();

        //格式化 : 日期 |>>>>字符串
        Date date1 = new Date();
        String format = sdf.format(date1);

        System.out.println(date1);
        System.out.println(format);

        //解析 : 格式化的逆过程 ,字符串 |>>>>日期
        String str = "22-09-08 下午17:40";
        Date date2 = sdf.parse(str);
        System.out.println(date2);
    }
}

```

```Java
//按照指定的方式格式化和解析 : 调用带参的构造器
SimpleDateFormat sdf = new SimpleDateFormat(yyyy-MM-dd hh-mm-ss);
//要求字符串必须符合SimpleDateFormat能识别的格式     //否则 , 抛异常
String str = "22-09-08 下午17:40";
Date date2 = sdf.parse(str);
System.out.println(date2);
```



4. Calendar类(抽象类)的使用

```java
public static void main(String[] args){
    //1.实例化
    //方式一 : 创建其子类(GregorianCanlendar)的对象
    //方式二 : 调用其静态方法getInstance()
    Calendar calendar = Calendar.getInstance();
    
    //2.常用方法
    //get()
    int days = calendar.get(Calendar.DAY_OF_MONTH);
    System.out.println(days);
    System.out.println(calendar.get(Calendar.DAY_OF_YEAR));
    
    //set()
    calendar.set(DAY_OF_MONTH,22);
    days = calendar.get(DAY_OF_MONTH);
    System.out.println(days);
    
    //add()
    calendar.add(DAY_OF_MONTH,3);
    days = calendar.get(DAY_OF_MONTH);
    System.out.println(days);
    
    //getTime() : 日历类 >>>>Date
    Date date = calendar.getTime();
    System.out.println(date);
    
    //setTime() : Date >>>>日历类
    Date date1 = new Date();
    calendar.setTime(date1);
    days = calendar.get(DAY_OF_MONTH);
    System.out.println(days);
}
```



###jdk8的日期时间的API

1. LocalDate , LacalTime , LocalDateTime类

```java
public static void main(String[] args){
    //now() : 获取当前的日期 , 时间 , 日期+时间
    LocalDate l1 = LocalData.now();
    LocalDate l2 = LocalTime.now();
    LocalDate l3 = LocalDataTime.now();
    //of() : 设置指定的年,月,日,时,分,秒.没有偏移量
    LocalDataTime localDateTime1 = LocalDateTime.of(2022,9,8);
    //getXxx() : 获取相关的属性  
    System.out.println(LocalDateTime.getDayOfMonth());
    System.out.println(LocalDateTime.getDayOfWeek());
    //withXxx() : 设置相关的属性
    LocalData localDate1 = LocalData.withDayOfMonth(22);
    //plus()
    LocalDataTime localDateTime2 = LocalDateTime.plusMonths(3);
    
}
```

2. Instant类

```java
public static void main(String[] args){
    //now() : 获取本初子午线对应的标准时间
    Instant instant = Instant.now();
    System.out.println(instant);
    
    //添加时间的偏移量
    OffsetDateTime offsetDateTime = instant.atOffSet(ZoneOffset.ofHours(8));
    System.out.println(offsetDateTime);

    //toEpochMilli() : 获取自19701月1日0时0分0秒开始的毫秒数
    long milli = Intant.toEpochMilli();  
    
    //ofEpochMilli() : 通过给定的毫秒数,获取Instant实例
    Instant instant1 =Instant.ofEpochMilli(1550475314878L);
    
}
```



3. DateTimeFormatter : 格式化或解析日期,时间

```java
public class DateTimeTest1 {
    public static void main(String[] args) {
        //方式一 : 预定义的标准格式.如:ISO_LOCAL_DATE_TIME , ISO_LOCAL_DATE , ISO_LOCAL_TIME
        DateTimeFormatter formatter = DateTimeFormatter.ISO_LOCAL_DATE_TIME;
        //格式化 : 日期 >>>字符串
        LocalDateTime localDateTime = LocalDateTime.now();
        String str1 = formatter.format(localDateTime);
        System.out.println(localDateTime);
        System.out.println(str1);
        //解析
        TemporalAccessor parse = formatter.parse("2022-09-08T20:41:13.438");
        System.out.println(parse);
        //方式二 : 本地化相关的格式.如 : ofLocalizedDateTime()
        //FormatStyle.LONG , FormatStyle.MEDIUM , FormatStyle.SHORT
        DateTimeFormatter formatter1 = DateTimeFormatter.ofLocalizedDateTime(FormatStyle.LONG);

        //重点!!!
        //方式三 : 自定义的格式. 如 : ofPattern("yyyy-MM-dd hh:mm:ss")
        DateTimeFormatter formatter2 = DateTimeFormatter.ofPattern("yyyy-MM-dd hh:mm:ss");
        //格式化
        String str2 = formatter2.format(LocalDateTime.now());
        System.out.println(str2);
    }
}
```



### Java比较器

1. Compareble接口 : 自然排序

> Compareble接口的使用 : 
>
> 1. 像String类,包装类等实现了Compareble接口,重写了compareTo(obj)方法,给了比较两个对象大小的方法
>
> 2. 像String类,包装类重写compareTo()方法以后,进行了从小到大的排列
>
> 3. 重写compareTo()的规则 : 
>
>    ​	如果当前对象this大于形参对象obj,则返回正整数
>
>    ​	如果当前对象this小于形参对象obj,则返回负整数
>
>    ​	如果当前对象this等于形参对象obj,则返回零

```java
String[] arr = new String[]{"AA","CC","JJ","DD","OO","RR","HH"};
Array.sort(arr); //将arr[]从小到大排列
```

> 4. 对于自定义类来说,如果需要排序,我们可以让自定义类实现Comparable接口,重写compareTo(obj)方法,在compare(obj)方法中指明如何排序

```java
public class GoodsTest {
    public static void main(String[] args) {

        Goods[] arr = new Goods[4];
        arr[0] = new Goods("lenovo",79);
        arr[1] = new Goods("dell",69);
        arr[2] = new Goods("xiaomi",49);
        arr[3] = new Goods("huawei",99);
        Arrays.sort(arr);
        System.out.println(Arrays.toString(arr));
    }
}

class Goods implements Comparable{
    String name;
    double price;
    
    @Override  
    public String toString() {
        return "Goods{" + "name='" + name + '\'' + ", price=" + price +'}';
    }

    public Goods(String name,double price) {
        this.name = name;
        this.price = price;
    }

    @Override
    public int compareTo(Object o) { //重写compareTo()
        if (o instanceof Goods) {
            Goods goods = (Goods)o;
            if(this.price > goods.price){
                return 1;
            }else if (this.price < goods.price){
                return -1;
            }else {
                return 0;
            }
        }
        throw new RuntimeException("传入的数据类型不一致");
    }
}
```



2. Comparator接口 : 定制排序

> 1. 背景 : 当元素的类型没有实现就java.lang.Comparable接口而又不方便修改代码,
>
>    ​	或者实现了java.lang.Comparable接口,但其排序规则不适合当前操作,
>
>    ​	那么,可以考虑使用Comparator接口的对象来排序
>
> 2. 重写Comparetor(Object o1,Object o2)方法,比较o1和o2的大小 : 
>
>    如果方法返回正整数,则表示o1>o2;
>
>    如果返回0,表示相等, 返回负整数 ,表示o1<o2;

```java
public class GoodsTest1 {
    public static void main(String[] args) {

        String[] arr = new String[]{"MM","GG","BB","PP","OO"};

        Arrays.sort(arr, new Comparator() {

            @Override  //按照字符串从大到小的顺序排列
            public int compare(Object o1, Object o2) {
                if(o1 instanceof String && o2 instanceof String){
                    String s1 = (String) o1;
                    String s2 = (String) o2;
                    return -s1.compareTo(s2);
                }
                    throw new RuntimeException("输出的数据类型不一致");
            }
        });
        System.out.println(Arrays.toString(arr));
    }
}
```

```java
Arrays.sort(arr, new Comparator() {

            @Override //指明商品比较大小的方式
            public int compare(Object o1, Object o2) {
                if(o1 instanceof Goods1 && o2 instanceof Goods1) {
                    Goods1 g1 = (Goods1) o1;
                    Goods1 g2 = (Goods1) o2;
                    if(){
						//在此处写比较大小的算法
                    }
                }
            });
```



###System,Math,BigInteger,BigDemical

1. System类

> native long currentTimeMillis(): 
>
> void exit(int status) : 
>
> void gc() : 
>
> String getProperty(String key) : 



2. Math类

> 所有数学相关的方法



3. BigInteger ,  BigDemical (对应整型和浮点型)

> BigDemical的精度非常高,一般用于科学计算或商业计算











## 枚举类

> ①枚举类的理解 : 类的对象只有有限个,确定的.我们称此类为枚举类
>
> ②当需要定义一组常量时,强烈建议使用枚举类
>
> ③如果枚举类中只有一个对象,则可以作为单例模式的实现方式.

###如何自定义枚举类

```java
public class SeasonTest {
    public static void main(String[] args) {
        Season autumn = Season.AUTUMN;
        System.out.println(autumn);
    }
}
//自定义枚举类
class Season {
    //1.声明Season对象的属性:private final修饰
    private final String seasonName;
    private final String seasonDesc;

    //2.私有化类的构造器
    private Season(String seasonName, String seasonDesc) {
        this.seasonName = seasonName;
        this.seasonDesc = seasonDesc;
    }

    //3.提供当前枚举类的多个对象: public static final的
    public static final Season SPRING = new Season("春天", "万物复苏");
    public static final Season SUMMER = new Season("夏天", "夏天");
    public static final Season AUTUMN = new Season("秋天", "秋天");
    public static final Season WINTER = new Season("冬天", "冬天");

    //4.其他诉求1 : 获取枚举类对象的属性
    public String seasonName() {
        return seasonName;
    }
    public String seasonDesc() {
        return seasonDesc;
    }
    //4.其他诉求2 : 提供toString()

    @Override
    public String toString() {
        return super.toString();
    }
}
```



###如何使用关键字enum定义枚举类

> 定义的枚举类默认继承于java.lang.Enum类

```java
public class SeasonTest1 {
    public static void main(String[] args) {
        Season summer = Season.SUMMER;
        System.out.println(summer); //输出SUMMER

        System.out.println(Season.class.getSuperclass()); //父类时Enum
    }
}
//使用enum关键字枚举类
enum Season1{
    //1.提供当前枚举类的多个对象,之间用','隔开,末尾对象';'结束
    SPRING ("春天", "万物复苏"),
    SUMMER ("夏天", "夏天"),
    AUTUMN ("秋天", "秋天"),
    pWINTER("冬天", "冬天");

    //2.声明Season对象的属性:private final修饰
    private final String seasonName;
    private final String seasonDesc;

    //3.私有化类的构造器
    private Season1(String seasonName, String seasonDesc) {
        this.seasonName = seasonName;
        this.seasonDesc = seasonDesc;
    }

    //4.其他诉求1 : 获取枚举类对象的属性
    public String seasonName() {
        return seasonName;
    }
    public String seasonDesc() {
        return seasonDesc;
    }
    //4.其他诉求2 : 提供toString()
    @Override
    public String toString() {
        return super.toString();
    }
}
```



###Enum类的常用方法

> values():返回枚举类型的对象数组
>
> valueOf(String str) : 返回枚举类中对象名时str的对象
>
> toString() : 返回当前枚举类对象常量的名称

```java
Season1 winter = Season1.valueOf("WINTER");
System.out.println(winter); //输出 WINTER
```



###实现接口的枚举类

> 使用enum关键字定义的枚举类定义接口

情况一 : 实现接口,在enum类中实现抽象方法

情况二 : 让枚举类的对象分别实现接口中的抽象方法

```java
public class SeasonTest1 {
    public static void main(String[] args) {
        Season1 summer = Season1.SUMMER;
        System.out.println(summer); //输出SUMMER

        System.out.println(Season.class.getSuperclass()); //父类时Enum
        summer.show();
    }
}
interface Info{
    void show();
}
//使用enum关键字枚举类
enum Season1 implements Info{
    //1.提供当前枚举类的多个对象,之间用','隔开,末尾对象';'结束
    SPRING ("春天", "万物复苏"){  //情况二
        @Override
        public void show() {
        }
    },
    SUMMER ("夏天", "夏天"){
        @Override
        public void show() {
            System.out.println("这是夏天.");
        }
    },
    AUTUMN ("秋天", "秋天"){
        @Override
        public void show() {
        }
    },
    pWINTER("冬天", "冬天"){
        @Override
        public void show() {
        }
    };

    //2.声明Season对象的属性:private final修饰
    private final String seasonName;
    private final String seasonDesc;
    //3.私有化类的构造器
    private Season1(String seasonName, String seasonDesc) {
        this.seasonName = seasonName;
        this.seasonDesc = seasonDesc;
    }
    //4.其他诉求1 : 获取枚举类对象的属性
    public String seasonName() {
        return seasonName;
    }
    public String seasonDesc() {
        return seasonDesc;
    }
    //4.其他诉求2 : 提供toString()
    @Override
    public String toString() {
        return super.toString();
    }
//    @Override            // 情况一
//    public void show() {
//        System.out.println("这是一个季节");
//    }
}
```







## 注解

###注解(Annotation)概述

> ①代码中的特殊标记,这些标记可以被编译,并执行相应的处理
>
> ②可以像修饰符一样使用,可用于修饰包,类,构造器,方法,成员变量,参数,局部变量的声明 
>
> ③可以说 , 框架 = 注解 + 反射 + 设计模式



###常见的注解示例

> 示例一 : 生成文档相关的注解
>
> 示例二  : 在编译时进行格式检查(jdk内置的三个基本注解)
>
> @override  : 限定重写父类方法,该注解只能用于方法
>
> @Deprecated : 用于表示所修饰的元素已过时
>
> @SuppressWarnings : 抑制编译器警告
>
> 示例三 : 跟踪代码依赖性,实现替代配置文件功能



###自定义Annotation

```java
//①注解声明为@interface
//②内部定义成员,通常使用value表示
//③可以指定成员的默认值,使用default定义
//④如果自定义注解没有成员,表明是一个标识作用
//如果注解有成员,在使用注解时,需要指明成员的值
//自定义注解通常都会指明两个元注解 : Retention , Target
public @interface MyAnnotation {    
    String value() default "hello";
    //String value();
}
public class AnnotationTest {
    public static void main(String[] args) {

    }
}
@MyAnnotation(value="hi")
class AAA{

}
```



###JDK中的元注解

> 元注解 : 对现有的注解进行结束说明的注解

jdk提供的四种元注解 : 

Retention : 指定所修饰的Annotation的生命周期 : SOURCE/CLASS(默认行为)/RUNTIME

​			只有声明为RUNTIME生命周期的的注解,才能通过反射获取.

Target : 用于指定被修饰的Annotation能用于修饰哪些元素

Documented : 表示所修饰的注解在被javadoc解析时,保留下来,(文档)

Inherited : 被其修饰的Annotation将具有继承性



###利用反射获取注解信息



###JDK8注解的新特性

> 可重复注解 : ①在MyAnnotation上声明@Repeatable,成员值为MyAnnotations.class
>
> ​			②MyAnnotation的Target和Retention与MyAnnotations相同
>
> 类型注解 : 
>
> ElementType.TYPE_PAREMENTER 表示该注解能写在类型变量的声明语句中(如 : 泛型声明)
>
> ElementType.TYPE_USE 表示该注解能写在使用类型的任何语句中



## 集合

概述

> ①集合,数组都是对多个数据进行存储操作的结构,简称Java容器.
>
> 说明 :此时的存储,主要指的是内存层面的存储,不涉及到持久化的存储
>
> ②数组的缺点 : 
>
> > 一旦初始化以后,其长度就不可修改.
> >
> > 数组中提供的方法非常有限,对于添加,删除,插入数据等操作,非常不便且效率不高
> >
> > 获取数组中实际元素个数的需求,数组没有现成的属性和方法可用
> >
> > 数组存储数据的特点 : 有序,可重复.对于无序,不可重复的需求,无法满足

集合框架

> Collection接口 : 单列集合 , 用来存储一个一个的对象
>
> ​	---List接口 : 存储有序的,可重复的数据.   (动态数组)
>
> ​		---Arraylist,Linkedlist,vector
>
> ​	---Set接口 : 存储无序的,不可重复的数据.
>
> ​		---HashSet,LinkedHashSet,TreeSet
>
> Map接口 : 双列集合,用来存储一对(key - value)一对的数据  ( y=f(x) )
>
> ​		---HashMap,LinkedHashMap,TreeMap,Hashtable,Properties 	



####Collection接口方法

```java
public class CollectionTest {
    public static void main(String[] args) {
        Collection coll = new ArrayList();

        //1. add(Object e) : 将元素e添加到集合coll中
        coll.add("AA");
        coll.add("BB");
        coll.add(123);
//        coll.add(new Date());

        //2. size() : 获取添加的元素的个数
        System.out.println(coll.size());  //3

        //3. addAll(Collection coll1) : 将coll1集合中的元素添加到当前集合中
        Collection coll1 = new ArrayList();
        coll1.add(456);
        coll1.add("CC");
        coll.addAll(coll1);
        System.out.println(coll.size());  //5

        //4. clear() : 清空集合元素
//        coll.clear();

        //5. isEmpty() : 判断当前集合是否为空
        System.out.println(coll.isEmpty());

        //6. contains(Object obj) : 判断当前集合中是否包含obj
        //我们在判断时会调用obj对象所在类的equals方法
        coll.add(new String("Tom"));
        boolean contains = coll.contains(123);
        System.out.println(contains);
        System.out.println(coll.contains(new String("Tom"))); //调用的是String重写的equals方法,比较的是内容

        //7. containsAll(Collection coll1) :判断形参coll1中的所有元素是否都存在于当前集合中
        System.out.println(coll.containsAll(coll1));

        System.out.println("***********************************");
        //8. remove(Object obj) : 从当前集合中移除obj元素
//        coll.remove(123);
//        System.out.println(coll);

        //9. removeAll(Collection coll1) : 从当前集合中移除coll1中的所有元素. (差集)
//        coll.removeAll(coll1);
//        System.out.println(coll);

        //10.retainAll(Collection coll1) : 获取coll1与当前集合的交集,并返回给当前集合
//        coll.retainAll(coll1);
//        System.out.println(coll);

        //11. equals(Object obj) : 要想返回ture,需要当前集合于形参集合的所有元素都相同
        System.out.println(coll.equals(coll1));

        //12. hashcode() : 返回当前对象的哈希值
        System.out.println(coll.hashCode());

        //13.集合>>>数组 : toArray() :
        Object[] arr = coll.toArray();
        for (int i = 0; i < arr.length; i++) {
            System.out.println(arr[i]);
        }
        //拓展 : 数组 >>>集合 : 调用Arrays类的静态方法asList()
        List<String> list = Arrays.asList(new String[]{"AA","BB","CC"});
        System.out.println(list);

        List<int[]> arr1 = Arrays.asList(new int[]{123,456});
        System.out.println(arr1.size()); //1  认为数组整体是一个元素

        //14. iterator() : 返回Iterator接口的实例,用于遍历集合元素.
    }
}
```



####Iterator迭代器接口

> 集合元素的遍历操作 ,使用Iterator迭代器接口
>
> 1. 内部的方法 : hasNext() 和 next()
> 2. 集合对象每次调用iterator()方法都得到一个全新的迭代器对象,默认游标都在集合的第一个元素之前.

```java
public class IteratorTest {
    public static void main(String[] args) {
        Collection coll = new ArrayList();
        coll.add(123);
        coll.add(456);
        coll.add(new String("Tom"));
        coll.add(false);

        Iterator iterator = coll.iterator();

        //方式一 :
//        System.out.println(iterator.next());
//        System.out.println(iterator.next());
//        System.out.println(iterator.next());
//        System.out.println(iterator.next());
        //报异常 : NoSuchElementException
//        System.out.println(iterator.next());

        //方式二 : 不推荐
//        for (int i = 0; i < coll.size(); i++) {
//            System.out.println(iterator.next());
//        }

        //方式三 : 推荐
        while(iterator.hasNext()){
            System.out.println(iterator.next());
        }
    }
}
```

> 3. remove()方法 : 可以在遍历的时候,删除集合中的元素.此方法不同于集合直接调用remove() 

如果还未调用next()或在上一次调用next方法之后已经调用了remove方法,再调用remove都会报异常

```java
//删除集合中 "Tom"
        Iterator iterator1 = coll.iterator();
        while(iterator1.hasNext()){
           Object obj = iterator1.next();
           if("Tom".equals(obj)){
               iterator1.remove();
           }
        }

//再遍历一次,看看有没有成功
        Iterator iterator2 = coll.iterator();
        while(iterator2.hasNext()){
            System.out.println(iterator2.next());
        }
```



增强for循环

> jdk5.0新增

```java
//for(集合元素的类型 局部变量 : 集合对象)
//内部仍然调用了迭代器
for(Object obj : coll){

    System.out.println(obj);
}

//遍历数组 for(数组元素的类型 局部变量 : 数组对象)
int[] arr = new int[]{1,2,3,4,5,6}; 
for(int i : arr){
	System.out.println(i);
}
```



####Collection子接口 : List

> Collection接口 : 单列集合 , 用来存储一个一个的对象
>
> ​	---List接口 : 存储有序的,可重复的数据.   (动态数组)
>
> ​		---ArrayList: 作为List接口的主要实现类;线程不安全,效率高;底层使用Object[] elementData存储
>
> ​		---Linkedlist: 对于频繁的插入,删除操作,使用此类效率比ArrayList高,底层使用双向链表存储
>
> ​		---vector: 作为List接口的古老实现类;线程安全的,效率低,底层使用Object[] elementData存储

1. AarryList:

jdk7的情况下

```java
ArrayList list = new ArrayList();  //底层创建了长度为10的Object[]数组elementData
liat.add(123); 	//elementDate[0] = new Integer(123);
...
list.add(11);  //如果此次添加导致底层elementData数组容量不够,则扩容
			//默认情况下,扩容为原来的1.5倍,同时将原有数组中的数组复制到新的数组

//结论 : 建议开发中使用带参的构造器 :ArrayList list = new ArrayList(int capacity);
```

jdk8的情况下

```java
ArrayList list = new ArrayList();  //底层Object[] elementData初始化为{},并没有创建长度
liat.add(123); 	//第一次调用add()时,底层才创建了长度为10的数组,并将数据123存到elementData[0];
...
//后续的添加和扩容操作与jdk7无异
```

2. LinkedList

```java
LinkedList list = new LinkedList();//内部声明了Node类型的first和last属性,默认值为
list.add(123); //将123封装到Node中,创建了Node对象

//其中,Node定义为 : 体现了LinkedList双向链表的说法

```

3. Vector : jdk7和jdk8中通过Vector()构造器创建对象时,底层都创建了长度为10的数组.在扩容方面,默认扩容为当前容量的2倍



4. List常用方法

> void add(int index , Object ele):在index位置上插入ele元素
>
> boolean addAll(int index ,Collection eles) : 从index位置开始将eles中的所有元素添加进来
>
> Object get(int index) : 获取指定index位置的元素
>
> int indexOf(Object obj):返回obj在集合中首次出现的位置
>
> int lastIndexOf(Object obj) : 返回obj在集合中末次出现的位置
>
> Object remove(int index) : 移除指定index位置的元素,并返回此元素
>
> Object set(int index,Object ele) : 设置指定index位置的元素为ele
>
> List subList(int fromIndex,int toIndex) : 返回从fromIndex位置到toIndex位置的子集合

总结 : 常用方法

增 : add(Object obj)

删 : remove(int index) / remove(Object obj)

改 : set(int index , Object ele)

查 : get(int index)

插入 : add(int index , Object obj)

长度 : size()

遍历 : ①Interator迭代器方式 ②增强for循环 ③普通循环

```java
 Collection coll = new ArrayList();
        coll.add(123);
        coll.add(456);
        coll.add(new String("Tom"));

//方式一 : 
Iterator iterator = lsit.iterator();
while(iterator.hasNext()){
	System.out.println(iterator.next());
}
//方式二 : 
for(Object obj : list){
    System.out.println(iterator.next());
}
//方式三 : 
for(int i = 0 ; i<list.size() ; i++){
	System.out.println(lsit.get(i));
}
```



####Collection子接口 : Set

> Collection接口 : 单列集合 , 用来存储一个一个的对象
>
> ​	---Set接口 : 存储无序的,不可重复的数据.
>
> ​		---HashSet : 作为Set接口的主要实现类;线程不安全的;可以存储null值
>
> ​			---LinkedHashSet : 作为HashSet的子类;遍历其内部数据时,可以按照添加的顺序遍历
>
> ​		---TreeSet : 可以按照添加对象的指定属性,进行排序



1. Set的无序性与不可重复性的理解

> 无序性 : 不等于随机性.存储的数据在底层数组中并非按照数组索引的顺序添加,而是根据数据的哈希值决定的
>
> 不可重复性 : 保证添加的元素按照equals()判断时,不能返回ture.即 : 相同的元素只能添加一个



2. HashSet中元素的添加过程

> 我们像HashSet中添加元素a,首先调用元素a所在类的hashCode()方法,计算元素a的哈希值,此哈希值接着通过某种算法计算出HashSet底层数组的存放位置(即为 : 索引位置),判断数组位置上是否已经有其他元素 : 
>
> ​	如果此位置上没有其他元素,则元素a添加成功 ;   >>>>①
>
> ​	如果此位置上有其他元素b(或以链表形式存在多个元素),则比较元素a和b的哈希值 : 
>
> ​		如果hash值不相同,则元素b添加成功 ,   >>>>②
>
> ​		如果hash值相同  , 进而需要调用元素a的equals()方法 :
>
> ​			equals()返回ture , 元素a添加失败
>
> ​			equals()返回false,元素a添加成功   >>>>③

对于添加成功的②和③而言 : 元素a与指定索引位置上的数据以链表的形式存储

jdk7 : 元素a放到数组中 , 指向已存在的元素

jdk8 : 原来的元素在数组中,指向元素a



3. 重写hashCode()和equals()

> 1. Set接口中没有额外定义新的方法,使用的都是Collection中声明过的方法.
>
> 2. 要求 : 向Set中添加的数据,其所在的类一定要重写hashCode()和equals()
>
>    要求 : 重写hashCode()和equals()尽可能保持一致性 : 相等的对象必须具有相同的散列码
>
>    重写方法的两个小技巧 : 对象中用作equals()比较的Field,都应该用来计算hashCode值 



4. LinkedHashSet的使用

> LinkedHashSet作为HashSet的子类,在添加数据的同时,每个数据还维护了两个引用(链表),记录此数据前一个数据和后一个数据
>
> 优点 : 对于频繁的遍历操作,LinkedHashSet效率高于HashSet



5. TreeSet的排序

> 1. 向TreeSet中添加的数据,要求是相同类的对象
> 2. 两种排序方式 : 自然排序和定制排序
> 3. 自然排序中,比较两个对象是否相同的标准为 : compareTo() 返回0 .不再是equals()
> 4. 定制排序中,比较两个对象是否相同的标准为 : compare() 返回0 .不再是equals()

```java
//自然排序
TreeSet set = new TreeSet();
set.add(new User("Tom",22));
set.add(new User("Jerry",22));
set.add(new User("Jack",22));
set.add(new User("Kale",22));
set.add(new User("Monica",22));

set.add(123);
set.add(456);    
set.add(789);
set.add(012);
```

```java
//定制排序
Comparator comp = new Comparator(){
    //按照年龄从大到小排序
    public int compare(Object o1 , Object o2){
        if (o1 instanceof User && o2 instanceof User){
            User u1 = (User)o1;
            User u2 = (User)o2;
            return Integer.compare(u1.getAge(),u2.getAge());       
        }else{
            throw new RuntimeException("输入的数据类型不匹配");
        }
    }
}

TreeSet set = new TreeSet(comp);  //
set.add(new User("Tom",22));
set.add(new User("Jerry",22));
set.add(new User("Jack",22));
set.add(new User("Kale",22));
set.add(new User("Monica",22));
```







#### Map接口

1. Map的实现类的结构

> Map : 双列数据,存储key-value对的数据               -----类似于高中的函数 : y = f(x)
>
> ​	---HashMap : 作为Map的主要实现类;线程不安全的,效率高;可以存储null的key和value
>
> ​		---LinkedHashMap : 保证在遍历map元素时,可以按照添加的顺序实现遍历
>
> ​					原因 : 在原有的HashMap底层结构基础上,添加了一对指针, 指向前一个和后一个元素
>
> ​					对于频繁的遍历操作,此类执行效率高于HashMap
>
> ​	---TreeMap : 保证按照添加的key-value对进行排序,实现排序遍历.此时考虑key的自然排序和定制排序,底层使用红黑树
>
> ​	---Hashtable : 作为古老的实现类;线程安全的,效率低;不能存储null的key和value
>
> ​		---Properties  : 常用来处理配置文件. key和value都是String类型
>
> HashMap的底层 : 数组 + 链表 (jdk7及之前)
>
> ​				数组 + 链表 + 红黑树 (jdk8)



2. Map结构的理解

> Map中key : 无序的,不可重复的,使用Set存储所有的key    -----key 所在的类要重写equals()和hashCode()
>
> Map中的value : 无序的,可重复的,使用Collection存储所有的value
>
> 一个键值对 : key-value构成了一个Entry对象
>
> Map中Entry : 无序的 , 不可重复的,使用Set存储所有的entry



3. HashMap的底层实现原理

   jdk7

> HashMap map = new HashMap();
>
> 在实例化以后,**底层创建了长度为16的一维数组Entry[] table .**
>
> ...可能已经执行过多次put...
>
> map.put(key1,value1) 
>
> 首先 , 调用key1所在类的hashCode()计算key1哈希值,此哈希值经过某种算法计算以后,得到在Entry数组中的存放位置.  **如果此为位置上的数据为空,此时的key1-value1添加成功.  情况① 如果此位置上的数据不为空, (意味着此位置上存在一个或多个数据(以链表形式存在)),比较key1和已经存在的一个或多个数据的哈希值 :** 
>
> ​	**如果key1的哈希值与已经存在的数据的哈希值都不相同,此时key1-value1添加成功 ** **情况②**
>
> ​	如果key1的哈希值和已经存在的某一个数据(key2-value2)的哈希值相同,继续比较 : 调用key1所在类的equals(key2)
>
> ​		如果equals()返回false : 此时key1-value1添加成功   情况③
>
> ​		如果equals()返回ture : 使用value1替换value2

补充 : 关于情况②和情况③ : 此时key1-value1和原来的数据以链表的方式存储

在不断的添加过程中,会涉及到扩容问题,默认的扩容方式 : 扩容为原来的两倍,并将原有的数据复制过来



**jdk8**相较于jdk7在底层实现方面的不同 : 

* new HashMap() : 底层没有创建一个长度为16的数组
* jdk8底层的数组是 : Node[] ,而非Entry[]
* 首次调用put()时,底层创建长度为16的数组
* jdk7底层结构只有: 数组 + 链表 . jdk8中底层结构 : 数组 + 链表 + 红黑树 .当数组的某一个索引位置上的元素以链表形式存在的数据个数 > 8 且当前数组的个数 > 64时,  此时此索引位置上的所有数据改为使用红黑树存储



4. LinkedHashMap的底层实现原理



5. Map中的常用方法

```java
//添加,删除,修改操作 : 
Object put(Object key,Object value); //将指定key-value添加到(或修改)当前map对象中
void putAll(Map m); //将m中所有key-value对存放到当前map中
Object remove(Object key); //移除指定key的key-value对,并返回value
void clear();  //清空当前map中的所有数据
```

```java
//元素查询的操作 :
Object get(Object key); //获取指定key对应的value
boolean containsKey(Object key); //是否包含指定的key
boolean containsValue(Object value);	//是否包含指定的value
int size();	//返回map中key-value对的个数
boolean isEmpty();  //判断当前map是否为空
boolean equals(Object obj);  //判断当前map和参数对象obj是否相等
```

```java
//元视图的操作方法
Set keySet();   //返回所有key构成的Set集合
Collection values();	//返回所有value构成的Collection集合
Set entrySet();		//返回所有key-value对构成的Set集合

```



6. TreeMap

两种添加方式

> 向TreeMap中添加key-value,要求key必须是由同一个类创建的对象
>
> 因为要按照key进行排序 : 自然排序 , 定制排序



7. Properties

> 常用来处理配置文件. key和value都是String类型

```java
Properties pros = new Properties();

FileInputStream fis = new FileInputStream("jdbc.properties");
pros.load(fis);

String name = pros.getProperty("name");
String password = pros.getProperty("password1");
```





#### Collections工具类

> 操作Collection , Map的工具类

```java
reverse(List); //反转list中元素的顺序
shuffle(List); //对List集合元素进行随机排序
sort(List) ;   //根据元素的自然顺序对指定List集合元素按升序排序
sort(List,Comparator); //根据指定的Comparator产生的顺序对List集合元素进行排序
swap(List,int,int); //将指定List集合中的i处元素和j处元素进行交换

Object max(Collection);	//根据元素的自然排序,返回给定集合中的最大元素
Object max(Collection,Comparator);	//根据Comparator指定的顺序,返回给的集合中的最大元素
Object min(Collection);	//
Object min(Collection,Comparator);	//
int frequency(Collection,Object); //返回指定集合中指定元素出现的次数
void copy(List dest,List src);	//将src中的内容复制到dest中
boolean replace(List list,Object oldval,Object newVal);	//使用新值替换List对象中的旧值
```

> Collections类中提供了多个synchronizedXxx()方法,该方法可使指定集合包装成线程同步的集合,从而解决多线程并发访问集合时的线程安全问题



## 泛型

###概述

> 允许在定义类,接口时通过一个标识表示**类中某个属性的类型**或者是**某个方法的返回值及参数类型**.这个类型参数将在使用时(例如,继承或实现这个接口,用这个类型声明变量,创建对象时)确定. 

```java
public static void main(String[] args) {
        //在集合中使用泛型之前的情况
        ArrayList list = new ArrayList();
        //需求 : 存放学生成绩
        list.add(99);
        list.add(63);
        list.add(93);
        list.add(94);
        //问题一 类型不安全
        list.add("Tom");
        for(Object score : list){
            //问题二 : 强转时,可能出现ClassCastException
            int stuScore = (Integer)score;
            System.out.println(stuScore);
        }
    }
```



###泛型的使用

> ①集合接口或集合类在jdk5.0时都修改为带泛型的结构
>
> ②在实例化集合类时,可以指明具体的泛型类型
>
> ③指明完以后,在集合类或接口中凡是定义类或接口时,内部结构使用到类的泛型的位置,都指定为实例化的泛型类型. 比如 : add(E  e)  >>>>实例化以后 : add(Integer e)
>
> ④注意点 : 泛型的类型必须时类,不能是基本数据类型.需要使用到基本数据类型的位置,用包装类替换
>
> ⑤如果实例化时,没有指明泛型的类型. 默认类型为java.lang.Object类型 

```java
//在集合中使用泛型的情况  : 以ArrayList为例
 public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<Integer>();
        //需求 : 存放学生成绩
        list.add(99);
        list.add(63);
        list.add(93);
        list.add(94);
        //编译时 ,就会进行类型检查,保证数据的安全
//        list.add("Tom");

     //方式一 :  
//        for(Integer score : list){
//            //避免了强转操作
//            int stuScore = score;
//           System.out.println(stuScore);
     
      //方式二 :
        Iterator<Integer> iterator = list.iterator();
        while(iterator.hasNext()){
            int stuScore = iterator.next();
            System.out.println(stuScore);
        }
        }
    }
```

```java
//在集合中使用泛型的情况  : 以HashMap为例



```



###自定义泛型结构

> 如何自定义泛型结构  : 泛型类 , 泛型接口 ,泛型方法

```java
class Order1<T> {
    String orderName;
    int orderId;

    //类的内部结构就可以使用类的泛型
    T orderT;

    public Order1() {
    }

    public Order1(String orderName, int orderId, T orderT) {
        this.orderName = orderName;
        this.orderId = orderId;
        this.orderT = orderT;
    }

    public T getOrderT() {
        return orderT;
    }

    public void setOrderT(T orderT) {
        this.orderT = orderT;
    }

    @Override
    public String toString() {
        return "Order1{" +
                "orderName='" + orderName + '\'' +
                ", orderId=" + orderId +
                ", orderT=" + orderT +
                '}';
    }
}
```

![Snipaste_2022-09-13_20-43-11](E:\截图\Snipaste_2022-09-13_20-43-11.png)![Snipaste_2022-09-13_20-43-42](E:\截图\Snipaste_2022-09-13_20-43-42.png)

```java
//泛型方法 : 在方法中出现了泛型的结构,泛型参数与类的泛型参数无关
//换句话说 ,泛型方法所属的类是不是泛型类都没有关系
//泛型方法,可以声明为静态的.原因 : 泛型参数是在调用方法时确定的,并非在类的实例化时确定
class order<T>{
	public <E> List <E> copyFromArrayToList(E[] arr){
    	ArrayList<E> list = new ArrayList<>();
    	
    	for(E e : arr){
			list.add(e);
   	 	}
    	return list;
	}
}

Test(){
    Order<String> order = new Order<>();
    Integer[] arr = new Integer[]{1,2,3,4}
    //泛型方法在调用时,指明泛型参数的类型
    List<Integer> list = order.copyFromArrayToList(arr);
    
    System.out.println(list);
    }
}



```



###泛型在继承上的体现

> 虽然类A是类B的父类 , 但是G<A> 和G<B>二者不具备子父类关系 , 二者是并列关系
>
> 补充 : 类A是类B的父类 , A<G> 和B<G> 的父类

```java
void test(){
    Object obj = null;
    String str = null;
    obj = null;
    
    Object[] arr1 = null;
    String[] arr2 = null;
    arr1 = arr2 ;
    
    List<Object> list1 = null;   //!!!
    List<String> list2 = null;
    //此时的list1和list2的类型不具有子父类关系
    list1 = list2;
    
//	Date date = new Date();   //编译不通过
// 	str = date;  	

    
}
```



###通配符的使用

> 通配符 : ?
>
> 类A是类B的父类,G<A>和G<B>是没有关系的,二者的共同父类是 : G<?> 

```java
void test(){
    List<Object> list1 = null;
    List<String> list2 = null;
    List<?> list = null;
    list = list1;
    list = list2;
    
    println(list1);
    println(list2);
    
    //添加 : 对于List<?>就不能向其内部添加数据
    //除了添加null之外
//    list.add("DD");
//    list.add('?');
    list.add(null);
    
    //获取 : 允许读取数据,读取的数据类型为Object
    Object obj = list.get(0);
}
public void print(List<?> list){
	Iterator<?> iterator = list.iterator();
    while(iterator.hasNext){
		Object obj = iterator.next();
        System.out.println(obj);
    }
}
```

> 有限制条件的通配符的使用 : 
> 	? extends A : G<? extends A> 可以作为G<A>和G<B>的父类,其中B是A的子类 
>
> ​	? super A :  G<? super A> 可以作为G<A>和G<B>的父类,其实B是A的父类
>
> 说明 : 可以读取和写入数据



## IO流



### File

File类的实例化

> 1. 如何创建File类的实例  : 有四个构造器
>
>    ​	File(String filePath)
>
>    ​	File(String parentPath,String childPath)
>
> 2. 相对路径 :  相较于某个路径下,指明的路径
>
>    绝对路径 : 包含盘符在内的文件或文件目录的路径
>
> 3. 路径分隔符
>
>    windows : \\\
>
>    unix : /

```java
public static void main(String[] args) {
        File file1 = new File("hello.txt"); //相对于当前module
        File file2 = new File("D:\\workspace.idea\\JavaSenior\\day09\\he.txt");
    }
```



File类的常用方法

```java
//获取 : 
public String getAbsolutePath(); //获取绝对路径
public String getPath(); //获取路径
public String getName(); //获取名称
public String getParent(); 	//获取上层文件目录路径.若无,返回null
public long length(); //获取文件长度(即:字节数). 不能获取目录的长度
public long lastModified(); //获取最后一次的修改实际 ,毫秒值

public String[] list();	//获取指定目录下的所有文件或者文件目录的名称数组
public File[] listFiles(); //获取指定目录下的所有文件或者文件目录的File数组
```

![Snipaste_2022-09-14_09-39-38](E:\截图\Snipaste_2022-09-14_09-39-38.png)

![Snipaste_2022-09-14_09-41-12](E:\截图\Snipaste_2022-09-14_09-41-12.png)





###IO流原理及流的分类

![Snipaste_2022-09-14_09-50-17](E:\截图\Snipaste_2022-09-14_09-50-17.png)

![Snipaste_2022-09-14_10-00-40](E:\截图\Snipaste_2022-09-14_10-00-40.png)



### 节点流(或文件流)

1. FileReader流

> 说明点 : 
>
> 1.read()的理解 : 返回读入的一个字符.如果达到文件末尾,返回-1
>
> 2.异常的处理 : 为了保证流资源一定可以执行关闭操作.需要使用try-catch-finally处理
>
> 3.读入的文件一定要存在,否则就会报FileNotFoundException 

```java
	//将day09下的hello.txt文件内容读入程序中,并输出到控制台
	@Test
    public void testFileReader() throws IOException {
        //1.实例化File类的对象,指明要操作的文件
        File file = new File("hello.txt");
        //2.提供具体的流
        FileReader fr = new FileReader(file);

        //3.数据的读入
        //read():返回读入的一个字符.如果达到文件末尾,返回-1
        int data = fr.read();
        while(data != -1){
            System.out.println((char)data);
            data = fr.read();
        }

        //4.流的关闭操作
        fr.close();
    }
```

```java
//对read()操作升级: 使用read的重载方法
    @Test
    public void testFileReader1() throws IOException {
        //1.File类的实例化
        File file = new File("hello.txt");

        //2.FileReader流的实例化
        FileReader fr = new FileReader(file);

        //3.读入的操作
        char[] cbuf = new char[5];
        int len;
        len = fr.read(cbuf);
  
        //4.资源的关闭
        fr.close();
    }

```



2. FileWriter流

```java
 //从内存中写出数据到硬盘的文件里
//说明 : 1.输出操作,对应的File可以不存在的.如果不存在,在输出的过程中,会自动创建此文件.
//		如果存在 : 如果流使用的构造器是:FileWriter(file,false)/FileWriter(file):对原有文件的覆盖
//				 如果流使用的构造器是 : FileWriter(file,ture),不会对原有文件覆盖,而是在后面添加
//		2.
    @Test
    public void testFileWriter() throws IOException {
        //1.提供File类的对象,指明写出的文件
        File file = new File("hello1.txt");
        //2.FileWriter流的实例化
        FileWriter fw = new FileWriter(file);
        //3.写出的操作
        fw.write("I have a dream."/n);
        fw.write("You should have a dream.");
        //4.流资源的关闭
        fw.close();
    }
```

3. 文件的复制

```java
 @Test
    public void testFileWriterFileReader() throws IOException {
        //1.创建File类的对象,指明读入和写出的文件
        File srcfile = new File("hello.txt");
        File destfile = new File("hello2.txt");
        //2.创建输入流和输出流的对象
        FileReader fr = new FileReader(srcfile);
        FileWriter fw = new FileWriter(destfile);
        //3.数据的读入和写出操作
        char[] cubf = new char[5];
        int len;    //记录每次读入到cbuf数组中的字符的个数
        while((len = fr.read(cubf)) != -1){
            //每次写出len个字符
            fw.write(cubf,0,len);
        }
        //4.流资源的关闭
        fr.close();
        fw.close();
    }
```



4. FileInputStream和FileOutStream

	 1. 对于文本文件(.txt	.java   .c   .cpp) , 使用字符流处理
> 2. 对于非文本文件, 使用字节流处理

```java
//实现对图片的复制
    @Test
    public void testFileInputOutputStream() {
        FileInputStream fis = null;
        FileOutputStream fos = null;
        try {
            //
            File cf = new File("壁纸.jpg");
            File vf = new File("壁纸1.jpg");

            //
            fis = new FileInputStream(cf);
            fos = new FileOutputStream(vf);

            //复制的过程
            byte[] buffer = new byte[5];
            int len;
            while ((len = fis.read(buffer)) != -1) {
                fos.write(buffer, 0, len);
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (fis != null) {
                try {
                    fis.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }

            }
            if (fos != null) {
                try {
                    fos.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }

            }
        }
```



### 缓冲流

> 处理流的一种
>
> 1. 缓存流 : BufferedInputStream , BufferedOutputStream , BufferedReader , BufferedWriter
>
> 2. 作用 : 提高流的读取 , 写入速度
>
>    提高读写速度的原因 : 内部提高了一个缓冲区
>
> 3. 处理流,就是"套接"在已有的流的基础上

```java
 //实现非文本文件的复制 : BufferInputStream , BufferOutStream
    @Test
    public void BufferedStreamTest(){
        BufferedInputStream bis = null;
        BufferedOutputStream bos = null;
        try {
            //1.造文件
            File srcFile = new File("壁纸.jpg");
            File destFile = new File("壁纸2.jpg");
            //2.造流
            //2.1造节点流
            FileInputStream fis = new FileInputStream(srcFile);
            FileOutputStream fos = new FileOutputStream(destFile);
            //2.2造缓冲流
            bis = new BufferedInputStream(fis);
            bos = new BufferedOutputStream(fos);

            //3.复制的细节 : 读取,写入
            byte[] buffer = new byte[10];
            int len;
            while((len = bis.read(buffer)) != -1){
                bos.write(buffer,0,len);
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
        //4.资源关闭
        //要求: 先关闭外层的流,再关闭内层的流
            try {
                if(bos != null){
                    bos.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
            try {
                if(bis != null){
                     bis.close();
                    //关闭外层流的同时,内层流也会自动关闭.关于内层流的关闭,我们可以省略
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
```

```java
//实现文本文件的复制 : BufferReader , BufferWriter
```



### 转换流

处理流之二 : 转换流的使用

> 1. 转换流 : 属于字符流
>
>    InputStreamReader : 将一个字节的输入流转换为字符的输入流
>
>    OutputStreamWriter : 将一个字符的输出流转换为字节的输出流
>
> 2. 作用 : 提供字节流与字符流之间的转换
>
> 3. 解码 : 字节,字节数组 ---->字符数组,字符串 
>
>    编码 : 字符数组,字符串 ---->字节,字节数组
>
> 4. 字符集

```java
 @Test
    public void InputStreamReader() throws IOException {
        FileInputStream fis = new FileInputStream("hello.txt");

//        InputStreamReader isr = new InputStreamReader(fis);  //使用系统默认的字符集
        //参数2指明了字符集,具体使用哪个字符集,取决于文件hello.txt保存时使用的字符集
        InputStreamReader isr = new InputStreamReader(fis,"UTF-8");

        char[] cbuf = new char[20];
        int len;
        while((len = isr.read(cbuf)) != -1){
            String str = new String(cbuf,0,len);
            System.out.println(str);
        }
    }
```



### 标准输入,输出流

> System.in : 标准的输入流 , 默认从键盘输入
>
> System.out : 标准的输出流 , 默认从控制台输出
>
> System类的setIn(InputStream is) / steOut(PrintStream ps)方式重新指定输入和输出的流

```java
//输入字符串,将整行字符串转成大写,继续输入,当输入"e"或"exit"时,退出程序
//方式二 : 使用System.in:  System.in >>转换流 >> BufferedReader的readLine()
```



### 打印流

> PrintStream和PrintWriter



### 数据流

> DateInputStream 和 DateOutputStream
>
> 用于读取或写出基本数据类型的变量或字符串

读取数据的顺序要与写入文件时保存的数据的顺序一致



###对象流

> 1. ObjectInputStream 和 ObjectOutputStream
>
> 2. 用于存储和读取基本数据类型或对象的处理流.它的强大之处就是可以把Java中的对象写入到数据源中,
>
>    也能把对象从数据源中还原出来
>
> 3. 要想一个java对象是可序列化的,需要满足相应的要求
>
> 4. 序列化机制 : 
>
>    对象序列化机制允许把内存中的Java对象转换成平台无关的二进制流,从而允许把这种二进制流,持久的保存在磁盘上,或通过网络将这种二进制流传输到另一个网络节点.当其他程序获取了这种二进制流,就可以恢复成原来的Java对象	

```java
//序列化过程 : 将内存中的java对象保存到磁盘中或通过网络传输出去
    // 使用ObjectOutputStream
    @Test
    public void testOutputStream(){
        ObjectOutputStream oos = null;
        try {
            //1.
            FileOutputStream fos = new FileOutputStream("object.dat");
            //2.
            oos = new ObjectOutputStream(fos);
            //3.
            oos.writeObject(new String("我爱北京"));
            oos.flush(); //刷新操作
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                if(oos != null){
                    //4.
                    oos.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
```

```java
//反序列化 : 将磁盘文件中的对象还原为内存的一个java对象
@Test
    public void testObjectInputStream(){
        ObjectInputStream ois = null;
        try {
            ois = new ObjectInputStream(new FileInputStream("object.dat"));
            Object obj = ois.readObject();
            String str = (String)obj;
            System.out.println(str);
        } catch (IOException e) {
            e.printStackTrace();
        } catch (ClassNotFoundException e) {
            e.printStackTrace();
        } finally {
            try {
                if(ois != null){
                    ois.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
```



自定义类实现序列化和反序列化

> Person类需要满足如下的要求,方可序列化
>
> 1. 需要实现接口 : Serializable
> 2. 当前类提供一个全局常量 : serialVersionUID
> 3. 除了当前Person类需要实现Serializable接口之外,还必须保证其内部所有属性也必须是可序列化的.(默认情况下,基本数据类型也可以序列化)
>
> 补充 : ObjectInputStream和ObjectOutputStream不能序列化static和transient修饰的成员变量

```java
class Person implements Serializable{
    public static final long serialVersionUID = 475463534532L;  //

    private String name;
    private int age ;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```



###随机存取文件流 

> RandomAccessFile的使用
>
> 1. RandomAccessFile直接继承于java.lang.Object类,实现类DateInput和DateOutput接口
>
> 2. RandomAccessFile既可以作为一个输入流,也可以作为一个输出流
>
> 3. 如果RandomAccessFile作为输出流时,写出到的文件如果不存在,则在执行过程中自动创建
>
>    如果写出的文件存在,则会对原有文件内容进行覆盖.(默认情况下,从头开始覆盖)
>
> 4. 可以通过相关的操作 , 可以实现对数据的插入

```java
 @Test
    public void testRandonAccess(){
        RandomAccessFile raf = null;
        RandomAccessFile raf1 = null;
        try {
            raf = new RandomAccessFile(new File("壁纸.jpg"),"r");
            raf1 = new RandomAccessFile(new File("壁纸3.jpg"),"rw");

            byte[] buffer = new byte[1024];
            int len;
            while((len = raf.read(buffer)) != -1){
                raf1.write(buffer,0,len);
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                if(raf != null){
                    raf.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
            try {
                if(raf1 != null){
                    raf1.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
```



### NIO介绍

![Snipaste_2022-09-15_16-21-54](E:\截图\Snipaste_2022-09-15_16-21-54.png)![Snipaste_2022-09-15_16-22-11](E:\截图\Snipaste_2022-09-15_16-22-11.png)







## 网络编程

> 网络编程中有两个主要的问题 : 
>
> 1. 如何准确地定位网络上一台或多台主机 ; 定位主机上的特定的应用
> 2. 找到主机后如何可靠高效地进行数据传输



> 网络编程中的两个要素 : 
>
> 1. 对应问题一 : IP和端口号
> 2. 对应问题二 : 提供网络通信协议 : TCP/IP参考模型

### 网络通信要素概述

> 网络编程中的两个要素 : 
>
> 1. 对应问题一 : IP和端口号
> 2. 对应问题二 : 提供网络通信协议 : TCP/IP参考模型

### 通信要素1:IP和端口号

> 1. IP :  唯一的标识Internet 上的计算机(通信实体)
>
> 2.  在Java中使用I'net'Address类代表IP
>
> 3.  IP分类 : IPv4 和 IPv6 ;万维网 和 局域网
>
> 4. 域名 : www.baidu.com
>
> 5. 本地回路地址 : 127.0.0.1  对应着 : Localhost
>
> 6. 如何实例化InetAddress : 两个方法 : getName(String host) , getLocalHost()
>
>    两个常用方法 ; getHostName() 和 getHostAddress()
>
> 7. 端口号 : 正在计算机上运行的进程
>
>    要求 : 不同的进程有不同的端口号
>
>    范围 : 被规定为一个16为的整数 : 0~65535
>
> 8. 端口号与IP地址的组合得出一个网络套接字 : Socekt



### 通信要素2:网络协议





## 反射

概述



理解Class类并获取Class实例

> 1. 类的加载过程 : 程序经过javac.exe命令以后,会生成一个或多个字节码文件(.class结尾)
>
>    接着我们使用java.exe命令对某个字节码文件进行解释运行.相当于将某个字节码文件加载到内存中.此过程就称为类的加载.加载到内存中的类,我们就称为运行时类 , 此运行时类 , 就作为Class的一个实例
>
> 2. 换句话说,Class的实例就对应着一个运行时类
>
> 3. 我们加载到内存中的运行时类,会缓存一定的时间.在此时间之内,我们可以通过不同的方式来获取此运行时类

```java
//获取Class实例的方式 (前三种需要掌握)
//方式一 : 调用运行时类的属性 .class
Class clazz = Person.class;

//方式二 : 通过运行时类的对象,调用getClass()
Person p1 = new Person();
Class clazz = p1.getClass();

//方式三 : 调用Class的静态方法 : forName(String classPath)
Class.forName("com.atguigu.java.Person"); //全类名

//方式四 : 使用类的加载器 : ClassLoader
ClassLoader classLoader = ReflectionTest.class.getClassLoader();
Class clazz = classLoader.loadClass("com.atguigu.java.Person")

```



Class实例可以是哪些结构

![Snipaste_2022-09-15_20-56-37](E:\截图\Snipaste_2022-09-15_20-56-37.png)



类的加载与ClassLoader的理解



创建运行时类的对象

```java
@Test
    public void test1() throws InstantiationException, IllegalAccessException {
        Class<Person> clazz = Person.class;
        /*
        newInstance():调用此方法,创建对应的运行时类的对象.内部调用了运行时类的空参的构造器

        要想此方法正常的创建运行时类的对象,要求:
        1.运行时类必须提供空参的构造器
        2.空参的构造器的访问权限得够.通常,设置为public

        在javabean中要求提供一个public的空参构造器.原因:
        1.便于通过反射,创建运行时类的对象
        2.便于子类继承此运行时类时,默认调用super()时,保证父类有此构造器
         */
        Person obj = clazz.newInstance();
        System.out.println(obj);

    }
```



获取运行时类的完整结构

1. 获取运行时类的属性

```java
//获取属性结构
//getFields() : 获取当前运行时类及其父类中声明为public访问权限的属性
Field[] fields = clszz.getFields();
for(Field f : fields ){
    System.out.println(f);
}

//getDeclaredFields() : 获取当前运行时类中声明的所有属性. (不包含父类声明的属性)
Field declaredFields = clazz.getDeclaredFields();//操作同上
```

2. 获取运行时类的方法

3. > getMethods() :  获取当前运行时类及其父类中声明为public访问权限的方法
   >
   > getDeclaredMethods() : 获取当前运行时类中声明的所有方法. (不包含父类声明的方法)

4. 获取运行时类的构造器

   > getConstructors() : 获取当前运行时类中声明为public的构造器
   >
   > getDeclaredConstructors() : 获取当前运行时类中声明的所有的构造器 

5. 获取运行时类的父类及父类的泛型

6. 获取运行时类的接口,所在包,注解







调用运行时类的指定结构

> 属性 , 方法 ,构造器 

1. 调用运行时类中的指定属性

```java
Class clazz = Person.class;
//1.创建运行时类的对象
Person p = (Person)clazz.newInstance();
//2.getDeclaredField(String fieldName) :获取运行时类中指定变量名的属性
Field name = clazz.getDeclaredField("name");
//3.保证属性是可访问的
name.setAccessible(ture);
//4.获取,设置指定对象的此属性值
name.set(p,"Tom");


```

2. 调用运行时类中的指定方法

```java
Class clazz = Person.class;
//1.获取指定的某个方法:getDeclaredMethod():参数一:指明获取的方法的名称 参数二:指明获取方法的形参列表
Method show = clazz.getDeclaredMethod("show",String.class);
//2.保证当前方法是可访问的
show.setAccessible(ture);
//2. 调用方法的invoke():参数一:方法的调用者  参数二 : 给方法形参赋值的形参
//		invoke()的返回值即为对应类中调用方法的返回值

```

3. 调用运行时类中的指定构造器

```java
//1.获取指定的构造器 getDeclaredConstructor():参数:指明构造器的参数列表
Constructor constructor = clazz.getDeclaredConstructor(String.class);
//2.保证该构造器是可访问的
constructor.setAccessible(true);
//3.调用此构造器创建运行时类的对象
Person p =  (Person)constructor.newInstance("Tom");
```





反射的应用 : 动态代理



## Java8新特性





### Lambda表达式

```java
@Test
    public void testLambda(){
        Comparator<Integer> com1 = new Comparator<Integer>() {
            @Override
            public int compare(Integer o1, Integer o2) {
                return 0;
            }
        };
        int compare1 = com1.compare(12,21);
        System.out.println(compare1);

        //Lambda表达式的写法
        Comparator<Integer> com2 = (o1, o2) -> Integer.compare(o1,o2);
        int compare2 = com1.compare(12,21);
        System.out.println(compare1);
        //方法引用
        Comparator<Integer> com3 = Integer :: compare;
    }
```



### 函数式(Functional)接口

![Snipaste_2022-09-16_17-15-47](E:\截图\Snipaste_2022-09-16_17-15-47.png)



### 方法引用与构造器引用



### Stream API

1. Stream关注的是对数据的运算,与CPU打交道

   集合关注的是数据的存储,与内存打交道

2. ①Stream自己不会存储元素.

   ②Stream不会改变源对象.相反,他们会返回一个持有结果的新Stream.

   ③Stream操作是延迟的.者意味着他们会等到需要结果的时候才执行

3. Stream执行流程

   ①Stream的实例化

   ```java
   //创建Stream方式一 : 通过集合
   void test(){
   	List<Employee> employees = EmployeeDate.getEmployees();
       
   //	default Stream<E> stream() : 返回一个顺序流
       Stream<Employee> stream = employes.stream();
   //	default Stream<E> parallelStream() : 返回一个并行流
       Stream<Employee> parallelStream = employes.parallelStream();
   }
   //创建Stream方式二 : 通过数组
   void test(){
       int[] arr = new int[]{1,2,3,4,5,6};
       //调用Arrays类的static<T> Stream<T> Stream(T[] array):返回一个流
       IntStream stream = Arrays.stream(arr);
       
       Employee e1 = new Employee(1001,"Tom");
       Employee e2 = new Employee(1002,"Jack");
       Employee[] arr1 = new Employee[]{e1,e2};
       Stream<Employee> stream1 = Arrays.stream(arr1);
   }
   //创建Stream方式三 : 通过Stream的Of()
   void test(){
       Stream<Integer> stream = Stream.of(1,2,3,4,5,6);
       
   }
   //创建Stream方式四 : 创建无限流
   @Test
   void test(){
       
   }
   ```

   

   ②一系列的**中间操作**(过滤,映射...) : 一个中间操作链,对数据源的数据进行处理

   > 1. 筛选与切片
   >
   >    filter(Predicate p)--接受Lambda , 从流中排除某些元素
   >
   >    limit(n)--截断流,使其元素不超过给定数量
   >
   >    skip(n)--跳过元素,返回一个扔掉了前n个元素的流,若流中元素不足n个,则返回一个空流
   >
   >    distinct()--筛选,通过流所生成元素的hashCode()和equals()去除重复元素
   >
   > 2. 映射 
   >
   >    map(Fuction f) : 接受一个函数作为参数,该函数会被应用到每个元素上,并将其映射成一个新的元素
   >
   >    flatMap(Fuction f) : 接受一个函数作为参数,将流中的每个值都换成另一个流,然后把所有流连接成一个流
   >
   > 3. 排序
   >
   >    sorted() : 产生一个新流,其中按自然顺序排序
   >
   >    sorted(Comparator com) : 产生一个新流,其中按比较器顺序排序

   

   ③**终止操作** : 一旦执行终止操作,就执行中间操作链,并产生结果.之后,不会再被使用

   > 1. 匹配与查找
   >
   >    allMatch(Predicate p) : 检查是否匹配所有元素
   >
   >    anyMatch(Predicate p) : 检查是否至少匹配一个元素
   >
   >    noneMatch(Predicate p) : 检查是否没有匹配所有元素
   >
   >    findFirst() : 返回第一个元素
   >
   >    findAny() : 返回当前流中的任意元素
   >
   >    count ---返回流中元素的总个数
   >
   >    max(Comparator c) ---返回流中最大值
   >
   >    min(Comparator c) ----返回流中最小值
   >
   >    forEach(Consumer c) ---内部迭代
   >
   > 2. 归约
   >
   >    reduce(T iden ,BinaryOperator b) : 可以将流中元素反复结合起来,得到一个值.返回T
   >
   >    reduce(BinaryOperator b) : 可以将流中元素反复结合起来,得到一个值,返回Optional<T>
   >
   > 3. 收集
   >
   >    collect(Collector c) : 将流转换为其他形式.接受一个Collector接口的实现,用于给Stream中元素做汇总的方法

 





### Optional类

```java
public class OptionalTest {
//    Optional.of(T t) : 创建一个Optional实例,t必须非空
//    Optional.empty() : 创建一个空的Optional实例
//    OptionalofNullable(T t) : t可以为null
    @Test
    public void test(){
        Girl girl = new Girl();
//        girl = null;
        //of(T t) : 保证t是非空的
        Optional<Girl> girl1 = Optional.of(girl);


    }
    @Test
    public void test1(){
        Girl girl = new Girl();
        girl = null;
        //ofNullable(T t) :t可以为null
        Optional<Girl> girl1 = Optional.ofNullable(girl);
        System.out.println(girl1);
        //orElse(T t) : 如果当前的Optional内部封装的t是非空的,则返回内部的t
        //如果内部的t是空的,则返回orElse()方法中的参数t1
        Girl girl2 = girl1.orElse(new Girl("张小凡"));
        System.out.println(girl2);

    }
```









 