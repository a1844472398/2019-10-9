# 笔记
## 前端发展史
- web1.0:静态页面
- web2.0：动态页面：
    + 1、弱前端时代： 服务端渲染
    + 1、客户端渲染
- 前端侵占移动端市场
- node.js

## 浏览器
> 360 谷歌（Chorme） IE 火狐（FireFox） 欧朋（Opera） QQ浏览器 safari

- webkit（v8引擎）
    + 谷歌
    + 手机浏览器
    + 国产的浏览器
- Gecko
    + 火狐
- Presto
    + 欧朋

- Trident
    + IE
    + IE EDGE（Chrome mini）

## 浏览器的控制台（F12/FN+F12）
- Elements: 可以查看（调整）页面的元素，样式
- Console: 可以运行代码，可以打印console的值
- Sources：存放的是页面所有的资源文件
- NetWork：里面是所有的资源请求

## JS
> js做为客户端的一种语言，不仅要做操作dom对象，还要操作浏览器的某些功能
- ECMAScript3/5（老版本）ES6/7等（这是新语法规范）：规定了js的语法，变量，操作语句
- DOM：文档对象模型（document
 object model）：提供了一些js的属性和方法来操作页面中的DOM元素
- BOM（browser object model）：浏览器对象模型：提供了一些js的属性和方法来操作浏览器

## JS中的变量
- let 创建变量：不能重复创创建一样的变量
- var 创建变量： 可以重复创建一样的变量
- function 创建函数变量
- const 创建常量，不允许被修改
- class 创建类
- import 导入
- Symbol 创建唯一值

## js中创建变量的命名规范
- 严格区分大小写
- 由数字、字母、下划线、$组成，但是不能以数字开头
- 不能以保留字或者关键字作为变量名
- 变量名遵循驼峰命名法(变量名的开头第一个单词的首字母开头小写，以后每一个有意义的单词开头的首字母都大写)

## js中的数据类型
- 基本数据类型
    + 12 number
    + '12' string
    + true/false boolean
    + null 空指针对象
    + undefined 未定义
    + Symbol 

- 引用数据类型
    + 对象数据类型 object
        + {name: 'xxx'， age：18} 普通对象
        + [1, '2', 'a'] 数组
        + Math  数学对象
        + /^$/  正则
        + Date

    + function

## 基本数据类型之number
 > 包括NaN和有效数字

 ### 把值转换为数字（Number（val））

 #### 把字符串转换为数字
    - 规律：只要字符串中出现了非有效数字，那么结果就是NaN（第一位小数点不算）
    - 空字符转数字为 0

 #### 把布尔转换为数字
    - Number(true)=> 1
    - Number(false)=> 0
 #### 把null和undefined转换为数字
    - Number(null) // 0
    - Number(undefined) // NaN
#### 把普通或数组对象转数字
    - 普通对象转数字，先把对象转字符串，然后在转数字
    - 数组转数字，先把数组转字符串，然后在转数字(其中空数组转字符串为 '')

### isNaN
 > isNaN 他会检测数据类型值是不是非有效数字，如果是就是true，反之就是false

 > 在使用isNaN的时候，如果发现检测的值的数据类型不是number类型的，要把它先转换为数字，在判断

