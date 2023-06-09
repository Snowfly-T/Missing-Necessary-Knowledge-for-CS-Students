# 强类型与弱类型

![各编程语言的类型系统](img/pl-types.png)

强类型、弱类型、静态类型与动态类型是四个经常被混淆的术语。在本小节，先阐释一下强类型与弱类型的区别。

强类型与弱类型语言最重要区别就在于是否大量采用隐式转换。弱类型语言通常会做大量的隐式转换，而强类型语言不会。例如，考虑下面这段伪代码：

```
a = 5
b = "4"
sum = a - b
```

在弱类型语言中，常常直接将这里的`b`先从字符串`"4"`转换为数字`4`，然后进行运算，得到`sum`为 1。而在强类型语言中，规定`-`运算符两边只能是数字，因此发现`b`是字符串就会报错，而不会尝试计算出结果。

很多人说 Python 是”弱类型语言“，这其实是将”弱类型“与下面即将阐明的”动态类型“相混淆了。上面这样的代码在 Python 中仍会报错，Python 不会”自作聪明“地像很多弱类型语言一样做隐式转换，所以 Python 显然是强类型的。

甚至在 Java 这样的静态强类型语言中，`"abc" + 42`这样的代码会做特殊处理。即，如果字符串与任意其他类型的值相加，会先尝试将另一个值转换为字符串，然后进行字符串拼接。而在 Python 中，这也是不允许的，你必须写成`"abc" + str(42)`才行，这更说明了 Python 的强类型本质。
