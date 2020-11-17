## 极简风格代码规范 v1.0

这是一个以为`JavaScript`作为语法参考的极简风格代码规范，其目的是希望代码能占用最少的内存又能同时保持代码的可读性，其他语言也可以举一反三。

## 变量名称

变量名称应当使用最多`4`个字符，可使用英文+符合+数字的组合，大多数情况下应当使用`1-2`个字符，好的例子：`event`=`e`，`name`=`n`，`code`=`c`，`codeName`=`cn`

`错误例子`：
```javascript
const app = new Application;
const codeName = app.codeName();

```
`正确例子`：
```javascript
let a = new Application,cn = app.codeName()
```

## 多用三目运算和写一行

应当避免出现多行赋值和`if(){} else {}`，多使用三目运算

`错误例子`：
```javascript
const app=system.getApp()
const getName=system.getName()

if(c){
  app.use()
  getName()
} else {
  console.log(false)
}
```

`正确例子`：
```javascript
let a=system.getApp(),gn=system.getName()
c?(a.use(),gn()):console.log(false)
```

## 删除空格

避免出现不必要的空格。

`错误例子`
```javascript
let a = false
```

`正确例子`
```javascript
let a=false
```

## 避免使用双引号

双引号大多数语言上和单引号是一致的，因此请尽量使用单引号代替双引号


## 省略语法和符号

不报错的情况下可省略一些语法，如分号。

`错误例子`：
```javascript
app.use((name)=>{
  return app.info
});

new AppInfo()
```

`正确例子`：
```javascript
app.use(name=>app.info)
new AppInfo
```

## 避免使用const

`const` 常量的声明需要用到`5`个字符，是远远不如`let`的`3`个字符节约时间和空间，且`let`能替代`const`

## 简化其他api的名称

在调用其他库的方法且方法名称大于4个字符还出现不止一次，应当使用字符串储存后续使用。

`错误例子`：
```javascript
import a from 'xxx'

a.addItem('1')
a.addItem('1')
```

`正确例子`：
```javascript
import a from 'xxx'

let at='addItem'
a[at]('1'),a[at]('1')
```

## 无用变量使用_命名

一些方法回调里通常会带一些我们不需要的参数，但又必须使用后面的参数，这些参数请使用_命名

`错误例子`：
```javascript
function get(code,state,info,std){
  return std
}
```

`正确例子`：
```javascript
let get=(_,_1,_2,s)=>s
```

## 使用ES => 语法替代function

`ES` `=>` 语法和`function`的区别只是内部`this`指向不同，但却缩短了函数的定义，如果真有需要内部`this`的需求，请使用对象属性的定义方式

`错误例子`：
```javascript
function get(){

}
```

`正确例子`：
```javascript
let get={
  name(){

  }
}
```



## 未完待续...
