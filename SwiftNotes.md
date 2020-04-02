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
