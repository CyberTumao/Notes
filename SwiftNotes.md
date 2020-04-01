# Swift Notes

## tips

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