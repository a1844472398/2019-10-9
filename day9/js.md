# js的数据类型

- 简单数据类型
    Number、String、Boolean、Null、undefined、Symbol

- 引用数据类型(复合数据类型)
    Object（function、Array、Date....）

# 区别？
在赋值的时候，简单数据类型是按值操作(克隆一份数据赋值给某个变量)，
引用数据类的赋值是按址操作（地址），2个变量的地址是指向同一个堆内存。

if、else 判断

for while for in

运算符:
    + - * / %

    == === != !==

    ! && ||

属性操作:
    className
    href
    src
    id
    value
    innerHTML
    innerText
    style

变量:(可变的量，数据，把数据存储到一个自定义的名字中(用let或者var去声明)，达到复用的目的)
    let,var

    ```
        document.getElementById('box').style.background = 'red';
        document.getElementById('box').style.width = '100px';

        let box = document.getElementById('box');
        box
    ```
常量:(*不可变的量*,把数据存储到一个自定义的名字中(用const去声明)，达到复用的目的) 
    const box = document.getElementById('box')

- 字符串、数组的方法
    - 字符串
    截取类:
        substring
        slice
        substr
        
    查找类:    
        indexOf
        lastIndexOf
        includes
    分割类:
        split

    替换类:
        replace()
    字母转换:
        toUpperCase() 小转大
        toLowerCase() 大转小

    
- 数组的方法:
    push 往数组的末尾添加一个或者多个数据，返回值为新数组的长度

    ``` 
        手写push

        function push(ary,...arg){ //[2,3,4]
            let ary2 = [...ary,...arg]; //[1,2,3,4]
            let len = ary2.length;
            for(let i=0;i<ary2.length;i++){
                ary[i] = ary2[i];
            }
            return len;
        }
        console.log(push(ary,2,3,4))
    ```

    unshift 数组首位添加一个或者多个数据

    shift   首位删除一个，返回值就删除的那个
    pop
    splice  
    sort
    slice
    concat
    toString
    join
    indexOf
    lastIndexOf
    reverse
    includes
    forEach
    map
    some
    every
    filter


    







    

        












