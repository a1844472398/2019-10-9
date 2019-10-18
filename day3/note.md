# isNaN
> 判断你要检测的值是否是一个非有效数字，如果是就返回true，否则就返回false
-在判断的过程中，如果发现检测的值不是number，要先转成number，在判断

```
isNaN(NaN) // true
isNaN(false) // false
isNaN({}) // true

isNaN( Number(undefined) ) // true
```

## parseInt和parseFloat
 > 从左往右依次查找，一旦遇到非有效数字，就立即停止查找，把之前找到的数字返回 
 - parseInt不可以识别小数点，parseFloat可以识别一位小数点
 - 数组取第一项进行转换

```
parseInt('13px') // 13
parseInt('px13') // NaN
parseInt(['13px', 12, '13'])
parseInt(false) // NaN
parseInt( parseFloat('1i3.5.6.7px') ) // 1
parseFloat( isNaN( parseInt(['1i3', '56']) )) //NaN
parseInt([]) // NaN
```
# string
> val.toString()
+ 对象转字符串：'[object Object]'
+ 数组转字符串：把中括号换成引号
+ null和undefined： 直接调用toString会报错，
+ 数字、布尔转字符转直接加引号

# 四则运算
> 除了加，剩下的都是正常的科学运算，如果在运算过程中，发现运算的值不是数字，要先转数字在运算
- NaN如果参与了运算，结果一定是NaN
> 加号有可能出现字符串拼接，如果加号和引号相遇了，那就是字符串拼接
> 拼接的过程的值如果是基本数据类型，不需要转数字了，直接拼接；如果是引用数据类型，直接转字符串在拼接

```
let str =  1 + null + undefined + [] + '珠峰' + [] + null;
console.log(str) // 'NaN珠峰null' 
1=>1 + undefined =>NaN + [] =>'NaN珠峰' + []=>'NaN珠峰null'

let s = parseInt(NaN) + isNaN(['p', 23]) + 'zhufeng' + null
console.log(s) // 'NaNzhufengnull'
NaN + true + 'zhufeng' + null=>NaN + 'zhufeng'=>'NaNzhufengnull'

console.log(true - false)// 1
'5' 
// 
```
# boolean
> true false
- Boolean
- !  !!
- if条件判断

> 其他数据 类型转布尔有且只有  0 NaN '' null undefined转布尔是false，其余的是true

> !：先转布尔在取反
> !! : 先转布尔在取反在取反

```
!! isNaN( Number( parseInt( parseFloat(!['11']) ) ) ) // true

```

## if条件判断

```
if(1){
    console.log(111)
}
```

# null和undefined
> 他俩都是没有
## null(意料之中的，开始可以手动给他赋值为null，之后呢可以给他重新赋值)
## undefined（意料之外的事情，一般都是浏览器默认的）

```
let pigFather = null
pigFather = 'er Ya'
```
---------------------------------------------

# object的普通对象
> {name: 'xxx', age:18, 2: 18}
- 任何一个对象外层由大括号包裹，由0到多组键值对组成，键值对之间拿逗号隔开，每一个键值对由属性名和属性值组成，属性名由字符串或者数字组成
- 属性名不能重复，如果重复了，后面的会覆盖前面的
- 查找属性：对象.属性名/对象['属性名']，如果属性名是数字，不能用对象.属性名的方式去获取
- 新增/修改键值对：对象.属性名 = xxx（如果原来有这个属性名就是修改，如果没有就是新增）
- 删除：假删除=>手动赋值为null; 真删除=> delete 对象.属性名
- 如果查找属性名对应的属性值不存在，就是undefined

```
var a = 15;
let monkey = {
    name: 'sunWukong',
    age: 18,
    infantName: 'badmonkey',
    fire: 8000,
    speed: a,
    4: 16
}

// console.log(monkey.name) // 获取属性名对应的属性值
// console.log(monkey['name']) // 获取属性名对应的属性值
// // console.log(monkey.4) // 报错
// console.log(monkey[4]) // 如果属性名是数字，不能用对象.属性名的方式去获取
// monkey.name = 333; // 修改属性名对应的属性值（如果原来有这个属性名就是修改，如果没有就是新增）
console.log(monkey)
// monkey.y = 666  // 新增键值对（如果原来有这个属性名就是修改，如果没有就是新增）
// console.log(monkey)
// monkey.name = null; // 假删除
console.log(monkey)
delete monkey.age; // 真删除
```

# 数组
> [1, 3, 'de', true, undefined, null]
- 外层由中括号包裹，里面写的是属性值,他的属性名数是数字，从0开始，依次递增，并且代表值的位置，那么他就叫 “索引”
- length，代表数组的长度，也是数组值的个数
- 数组的第一项索引是0
- 数组的最后一项索引是ary.length-1
- ary[ary.length] = xxx // 项数组末尾追加一项

```
    let ary = [1, 2, null]
    console.log(ary)
    console.log(ary[0]) // 获取数组的第一项
    console.log(ary[ary.length-1]) // 获取数组的后一项
    console.log(ary[ary.length] = 'hongchen') // 向数组末尾追加一项
    console.log(ary)
```

## 堆栈内存的区别

```
let a = 12;
let b = a;
b = 13
console.log(a)


let n = {name: 'hongchen'};
let m = n;
m.name = 'liaoque';
console.log(n.name) // 'liaoque'


let n=[10, 20];
let m = n;
let x = m;
n[0] = 100;
n = [20, 30]
x = n
n[0] = 300
x[0] = 400
console.log(m,n,x)

let a = {
    n:1
};
let b = a;
a.x = a = { // 像这种连续等于要从左往右依次赋值
    n:2
};            
console.log(a.x, b)
```

# 数据类型比较（结果是布尔）
-  = 赋值
- == 比较(会进行数据类型转换)
- != 不等(会进行数据类型转换)
- === 绝对比较（不进行数据类型转换）
- !== 绝对不相等（不进行数据类型转换）

```
对象 == 对象 比较的空间地址（永远不相等）
对象 == 数字 对象转数字在比较
对象 == 字符串 把对象转换为字符串在比较
对象 == 布尔 他会把两边全部转数字在进行比较
数字 == 字符串 他会把字符串转数字进行比较
数字 == 布尔 把布尔转数字在进行比较
字符串 == 布尔 把两边全部转换为数字在进行比较


null和其他值都不相等（null == undefined他俩是相等的）
undefined和其他值不相等（null == undefined他俩是相等的）
```

# 逻辑运算符
 - %模（取余数）
 - i++/i--(先取值后运算)
 - ++i/--i(先运算后取值)
 - -=/+=（自增）

# js操作的语句（循环、判断语句）
- if/else if/else
- 三元运算符
- switch case

## if/else if/else

```
// 如果有一个条件成立，别的条件不管成立不成立都不执行了
// 括号里的条件会转布尔，如果是true条件就成立，如果是false就是不成立
// 括号里的条件可以写一个值，可以写大于、等于、小于都可以

if(判断的条件){
    执行的代码
}
else if(判断的条件){

}
....
else{
如果以上条件都不成立就走else里的代码
}
```

## 三元运算符
    > 条件 ? 条件成立要处理的事情 : 条件不成立要处理里的事情
    1、如果处理的事情比较多，我们用括号包起来，每一件事用逗号分隔；
    2、如果不需要处理事情，可以用null或undfined站位，不可以空着

## switch case
    一个变量在不同值的情况下的操作
     1、每一种case情况结束后都要加break阻断代码继续运行
     2、如果不加break，那么在成立条件后的条件不管是否成立都要执行，直到遇到break为止
     3、default等价else，以上条件都不成立，就走default
```

switch(val){
    case 1:
        console.log(1);
        break;
    case 2:
        console.log(2);
        break;
    default:
        console.log('背锅')
}
```







