[[面向对象-OOP]]
### PolyMorphism

#### 理解

-   一个事物的多种形态 – 子类对象的多态性
    

#### 代码

-   Person p2 = new Man();//Man is subclass of Person
    
-   父类的引用指向子类的对象（或子类的对象赋给父类的引用）
    
-   子类可看做是特殊的父类， 所以父类类型的引用可以指向子类的对象：向上转型(upcasting)
    
    -   一个变量只能有一种确定的数据类型
        
    -   一个引用类型变量可能指向(引用)多种不同类型的对象
        

#### 应用

##### 虚拟方法调用 `Virtual Method Invocation`

-   子类中定义了与父类同名同参数的方法，在多态情况下，将此时父类的方法称为**虚拟方法**，父类根据赋给它的不同子类对象，动态调用属于子类的该方法
    
-   这样的方法调用在**编译期是无法确定的** – 也就是方法调用在运行时确定，称为**动态绑定** – 多态是运行时行为
    
-   p2.eat();//输出为, Man eat
    
-   调用子父类同名同参方法时，实际执行的是子类重写父类的方法 = 口诀：编译看左边，运行看右边
    
-   前提
    
    -   必须有子父类才能进行多态
        
    -   必须有方法的重写（也就是子父类同名，同参方法）
        
    -   虚拟方法调用时不能调用子类特有的方法；如果父类没有子类的某些方法，则**编译报错**
        

##### 辨析 —多态和属性无关

-   对象的多态性只适用于方法，不适用于属性。因为子类和父类的属性是同时存在，所以运行时只看引用类型变量的类型
    

#### 作用

-   提升代码可扩展性，减少代码的冗余
    
-   public class AnimalTest {  
     public static void main(String[] args) {  
     AnimalTest test = new AnimalTest();  
     test.show(new Cat());//Animal animal = new Cat();  
     test.show(new Dog());//Animal animal = new Dog();  
     //如果没有多态性，我们就需要为每种动物类型定义一种新的方法，大量的使用方法的重载  
     }  
     public void show(Animal animal) {  
     animal.eat();  
     animal.shout();  
     }  
    }  
    ​  
    class Animal{  
     public void eat() { }  
     public void shout() { }  
    }  
    ​  
    class Cat extends Animal{  
     public void eat() { System.out.println("猫吃鱼");}  
     public void shout() {System.out.println("喵！");}  
    }  
    class Dog extends Animal{  
     public void eat() { System.out.println("狗吃骨头"); }  
     public void shout() {System.out.println("汪！");}  
    }
    

#### 概念辨析

-   多态是运行时行为
    
-   import java.util.Random;  
    //证明如下：  
    class Animal  {  
     protected void eat() {  
     System.out.println("animal eat food");  
     }  
    }  
    ​  
    class Cat  extends Animal  {  
     protected void eat() {  
     System.out.println("cat eat fish");  
     }  
    }  
    ​  
    class Dog  extends Animal  {  
     public void eat() {  
     System.out.println("Dog eat bone");  
     }  
    }  
    ​  
    class Sheep extends Animal  {  
     public void eat() {  
     System.out.println("Sheep eat grass");  
     }  
    }  
    ​  
    public class InterviewTest {  
     public static Animal  getInstance(int key) {  
     switch (key) {  
     case 0:  
     return new Cat ();  
     case 1:  
     return new Dog ();  
     default:  
     return new Sheep ();  
     }  
    ​  
     }  
    ​  
     public static void main(String[] args) {  
     int key = new Random().nextInt(3);  
     System.out.println(key);  
     Animal  animal = getInstance(key);  
     animal.eat();//此处，直到运行之前我们都不知道结果是什么，所以是运行时行为  
     }  
    }