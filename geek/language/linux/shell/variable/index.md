## 本章的知识点：
- a. 介绍
- b. 声明方式
- c. 调用方式
- d. 取消
- e. 命名规则
- f. 交互式变量(用户输入)
- g. 交互式变量(文本)
- h. 声明带有类型的变量
- i. 分类

### a. 介绍
- 定义：
    - 变量就是用来临时保存数据的，该数据是可以变化的。

### b. 声明方式
- 语法：
    - 变量名=变量值

### c. 调用方式
- 语法：
    - $变量名
- 基本调用方式：
```
    # 第一种：
        $变量名
        
    # 第二种：
        ${变量名}
```

### d. 取消
- 语法：
    - unset 变量名

### e. 命名规则
- 变量名区分大小写
- 变量名不能出现特殊字符
- 变量值尽量用双引号引起来
- 变量名不能以数字开头
- 等号两边不能有任何的空格
- 变量名尽量见名知义

### f. 交互式变量(用户输入)
- 目的：
    - 让用户自己给变量赋值
- 语法：
    ```
        read [选项] 变量名
    ```
- 常用选项：
    - -p: 定义提示用户的信息
    - -n: 定义字符数量
    - -s: 不显示用户的输入内容
    - -t: 限制用户输入的时间
- 案例：
    ```
        todo: 这个要添加在shell脚本中的案例
    ```

### g. 交互式变量(文本)
- todo: 这个等实际应用时添加

### h. 声明带有类型的变量
- 目的：
    - 给变量设置一些限制，固定变量的类型。比如：只读。
- 语法：
    - declare 选项 变量名=变量值
- 常用选项：
    - -i: 整型
    - -r: 只读
    - -a: 普通数组
    - -A：关联数组
    - -X：将变量通过环境变量导出 （export aaa=12345）

### i. 分类
- 本地变量：
    - 当前用户自定义的变量。当前进程中有效，其他进程和当前的子进程无效。
- 环境变量：
    - 当前程序有效，并且能够被子程序调用。
        - env 查看当前的环境变量
        - set 查询当前用户的所有变量
        - export 变量名=变量值 
- 全局变量：
    - 全局所有的用户和进程都能被调用，并且能继承，新建用户也默认能调用。
- 系统变量：
    - shell本身已经固定好了他的名字和作用。
        - $? 上一条命令执行后返回的状态。状态为 0 是成功的状态，非0表示执行异常或者错误。
        - $0 当前执行脚本的名称
        - $# 脚本后拼接参数的个数
        - $* 脚本后面所有的参数，参数当成一个整体输出，每个变量参数之间用空格分开
        - $@ 脚本后面的所有参数，参数是独立的，也是全部输出。
        - $1-$9 脚本后面位置参数，$1表示第一个参数，后面以此类推
        - ${10}-${n} 参数第10位之后必须这样写
        - $$ 当前脚本的进程号码
        - $! 后台运行的最后一个进程号码
        - !$ 调用最后一条命令历史中的参数