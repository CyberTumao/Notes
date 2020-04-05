# Swift Notes

## 代码技巧

### switch
* switch配合元组使用来简化代码  

```
for i in 1...100 {
    let a = i % 3
    let b = i % 5
    switch (a, b) {
    case (0, 0):
        print("FIZZ BUZZ")
    case (0, _):
        print("FIZZ")
    case (_, 0):
        print("BUZZ")
    default:
        print(i)
    }
}
```
第二个分支
和第三个分支的下划线（_）是能匹配任何值的通配符

### for

* 使用where来简化代码  

```
for i in 1000 {
    if i % 3 == 0 {
        print(i)
    }
}
```


```
for i in 1...100 where i % 3 == 0 {
	print(i)
}
```

## 知识点
### String
* Unicode  

> 标准等价是指两个Unicode标量序列在语言学层面是否相等  
> Swift内判断字符串相等时判断是否标准等价  

### 函数
* in-out parameter   

> 1. in-out参数不能有默认值
> 2. 变长参数不能标记为`inout`。

* functional programming  

> 函数式编程d包含以下几点  
> 1. 一等公民函数  
> 2. 纯函数  
> 3. 不可变性  
> 4. 强类型

### 类和结构体
* 类型方法

> 1. 对于值类型，要声明类型方法需要用到`static`关键字  
> 2. 类的类型方法要用`class`关键字标记
> 3. 类中使用`static`相当于`final class`

### 属性
* 只读属性

> 存储属性的只读属性使用let  
> 计算属性的只读属性使用var  
> 计算属性提供一个读取方法`getter`来获取属性的值，并可选的提供一个写入方法`setter`来设置属性的值  
>
> ```
> var property: Type {  
>     get {
>         ...
>     }
> }
> ```

* 静态属性和类型属性的最大区别是静态属性无法被子类覆盖（`static` ，`class`）

### 初始化
* 结构体初始化

> initializer delegation  
> 委托初始化对应于类初始化中的便捷初始化

* 类初始化

> 类初始化分为指定初始化`designated`和便捷初始化`convenience`  
> 与结构体不同，类没有默认的成员初始化方法  
> 
> #### automatic initializer inheritance  
> 
> 1. 如果子类没有定义任何指定初始化方法，就会继承父类的指定初始化方法            > 2. 如果子类实现了父类的所有指定初始化方法（无论是通过显式实现还是隐式继承），就会继承父类的所有便捷初始化方法
> 
> #### deinitialization
> 
> 只有引用类型可以反初始化，值类型不行。

### Extension
* Swift扩展不允许为类型添加存储属性

### Generic
* 类型、函数和方法都可以是泛型的，协议不可以。协议支持类型的一个相关特性：关联类型`associated types`

### ARC
* weak reference

> 弱引用有两个条件：  

> 1. 弱引用必须用`var`声明，不能用`let`  
> 2. 弱引用必须声明为可空类型  

* capture list  

> 捕获列表的语法是在闭包参数列表前面加上带方括号的变量列表