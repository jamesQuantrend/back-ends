## 本章的知识点：
- a. 介绍
- b. 语法
- c. 调用方式
- d. return

### a. 介绍
- shell允许将一组命令集合或者语句形成一段可用代码，这些代码称为shell函数。

### b. 语法
```
    function 函数名() {
        函数体
    }
```

### c. 调用方式(当前命令行||环境变量)
```
    函数名
```

### d. return
- 可以结束一个函数
- 返回一个状态码
- 如果没有return命令，就会返回最后一条命令的状态码