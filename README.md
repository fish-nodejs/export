# module.exports
我之前一直就是不明白该如何组织自己的代码。我看别人写的库，多数都是先写一个类(或者说构造函数)出来，然后通过它实例化一个对象，但是自己转不过这个弯来。自己写多数都是都直接声明一个对象，然后给这个对象添加属性和方法。

现在若有所悟。直接的声明变量就是类似于其他语言的单例模式。我们在写一个模块的时候，最后肯定要export一个东西出来，正常情况下这个东西无外乎是这三种类型：

- object：
  在JS模块化中有一个特点，如果module.exports是一个引用类型，那么被多次import的话还是一个对象。如果你想exports一个对象，你的明确你是否真的想共享这个东西。


- class
  也是对象。被多次import是，不应该动它的的属性、方法和prototype。

js中的工厂函数两种写法
- exports 一个构造函数将来被new
- exports 一个普通函数调用时自行创建一个对象
都行，功能上没区别，但是前者更有语义化的价值

我看过很多第三方模块，都是export一个类出来，但是我用的时候一般只会实例化一个对象，所以当时我就很迷糊，为什么不直接export一个对象？

理论上都行，我自己可能是用字面量写法（单例模式）习惯了，所以老是想直接export一个对象。
但是想想还是export一个类比较好，毕竟一个项目中可能还会import它一下。使用对象的字面量写法前，你要明确想清楚自己就是想用单例模式。
