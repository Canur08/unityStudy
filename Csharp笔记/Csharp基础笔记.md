# Csharp基础笔记

## 注释

```
//            -->单行注释
/* text */    -->多行注释
///           -->用于解释类和方法的
```

## 变量类型

1bit(位) = 0/1
1byte = 8bit
1kb = 1024byte
1mb = 1024kb

有符号数：
sbyte   (-128~127) == 2<sup>8</sup>
int     (正负21e多) == 2<sup>32</sup>
short   (正负3w多) == 2<sup>16</sup>
long    (正负900w兆多) == 2<sup>64</sup>

无符号数：
byte    0~255    2<sup>8</sup>
uint    0~42e    2<sup>32</sup>
ushort    2<sup>16</sup>

ulong    2<sup>64</sup>

浮点数：

float    2<sup>32</sup>    存储7/8位有效数字，遵循四舍五入（有效数字从左到右非零数开始数）

c#中声明的小数默认是double类型，所以float类型需要加上f

double    2<sup>64</sup>    存储15~17位有效数字

decimal    2<sup>128</sup>    存储27~28位有效数字，不建议使用，使用需在后面加m

特殊类型：

bool    true false    真与假

char    存储单个字符

string    字符串类型，存储多个字符，无上限

## 常量

必须初始化，不能被修改

关键字 const

固定写法const 变量类型 变量名 = 初始值；

const int num = 20;

## 转义字符

固定写法：\字符

单引号    \'

双引号    \"

换行    \n

不常用

制表符    \t    tap

光标退格    \b    光标往前一个

空字符    \0 

警报音    \a    警告音效

取消转义字符    在字符串前面加上@    字符串里的转义字符就没用

## 类型转换

类型转换就是不同变量类型之间的相互转换

### 隐式转换

不同类型之间自动转换（大范围装小范围）

例：int变量赋值给long变量，是允许的，遵循规则，而long不能赋值给int

decimal类型不能用隐式转换去存储double和float，但是可以隐式存储整形

特殊类型之间不存在隐式转换

有符号的变量不能隐式转换成无符号

无符号数范围小于有符号数是可以隐式转换

浮点数可以装载任何类型的整数

### 显式转换

作用：一般情况下将高精度类型强制转换为低精度

语法：变量类型 变量名 = （变量类型）变量；



Parse方法

作用：把字符串类型转换为对应的类型

语法：变量类型.Parse("字符串")



Convert方法

作用：更准确的将各个类型进行转换

语法Convert.To目标类型(变量或常量)



其他类型转string（toString方法）

作用：拼接打印

语法：变量.toString();



## 异常捕获

解决代码报错时造成程序卡死

语法：

```csharp
try{
    // 希望进行异常捕获的代码，报错了不会让程序卡死
}
catch{
    // 出错执行的代码
    // catch(Exception e) 具体报错追踪，通过e得到具体报错信息
}
// 可选
finally{
    //最后执行的代码，不管有没有出错，都会执行
}

```



## 控制台相关

```csharpw
// 输出
Console.WriteLine();
Console.Write();
// 输入
Console.ReadLIne();
COnsole.ReadKey(); // 检测按键
// 清空
Console.Clear();
// 设置控制台大小
Console.SetWindowSize(); //设置窗口大小
Console.SetBufferSize(); //设置缓冲区大小
// 设置光标位置
Console.SetCursorPosition(x,y);
// 设置文字颜色
Console.ForegroundColor = ConsoleColor.Red;
// 设置背景颜色
Console.BackgroundColor = ConsoleColor.Green;
// 光标显隐
Console.CursorVisible = false;
// 关闭控制台
Environment.Exit(0);
```