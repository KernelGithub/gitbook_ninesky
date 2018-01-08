# JS6种类型

1. 基本类型：number  string boolean null undefinded，按值访问，可以操作保存在变量中实际的值。
2. 引用类型：object\(Function,Array, Date,...\)，保存在内存中的对象。js不允许直接访问内存中的位置，所有引用类型是按引用访问的。
3. 隐式转换
   ```
   num-0;//变量转数字
   num+'';//变量转字符串
   number == string //转number
   boolean == ? //转number 
   object == number|string 尝试对象转为基本类型
   ```
4. 包装对象，基本类型中的number、string、boolean都有对应的包装类型。
   1. 把一个基本类型，尝试用对象的方式使用它的时候，比如访问length属性，或者增加一些属性时，js会把这些基本类型转化为包装类型对象。完成这样一个访问，比如a.length返回以后，或者设置了以后，这个临时对象会被销毁掉，所有a.t 赋值后，在输出a.t的值使undefined



