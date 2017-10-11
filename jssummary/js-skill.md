1. **实用   !!   操作符转换布尔值**
   对变量使用 !!variable 做检查，只要变量的值为：0、null、""、undefined、NaN都将返回的是false，反之返回的是true.
2. **使用+将字符串转换成数字**
   可以将字符串数据转换成数字，不过只适用于数字字符串，否则将返回NaN。这个也适用于**Date，**返回时间戳数字
   1. console.log\(+new Date\(\)\);
3. **并条件符**
   ```
   if(conected){login();} //==>  connected && login();
   // 如果一些属性或函数存在于一个对象中，可以这样检测
   user && user.login();
   ```
4. **使用  \|\|  运算符 设置默认值**

   ```
   function User(name, age) {
       this.name = name || "Default Name";
       this.name = age || 18;
   }
   ```

5. **缓存array.length**

6. **检测对象中的属性**

   1. ```
      if('querySelector' in document) {
          document.querySelector("#id");
      } else {
          document.getElementById("id");
      }
      ```

7. **获取数组中最后一个元素**

   1. Array.prototype.slice\(being, end\)用来获取begin和end之间的数组元素。如果你不设置end参数，将会将数组的默认长度当做end值。如果设置负值作为begin的值，那么可以获取数组的最后元素,eg:

   2. ```
      var array = [1, 2, 3, 4, 5, 6];
      console.log(array.slice(-1));//[6]
      console.log(array.slice(-2));//[5, 6]
      console.log(array.slice(-1));//[4, 5, 6]
      ```

8. **数组截断**

   主要用来锁定数组的大小，用于删除数组的一些元素很有用。例如，数组有6个元素，你只想要前三个，使用array.length = 3 来截断数组，eg:

   1. ```
      var array = [1, 2, 3, 4, 5, 6];
      console.log(array.lenth);//6
      array.lenth = 3;
      console.log(array.lenth );//3
      console.log(array); //[1, 2, 3]
      ```

9. ** 替换所有**

10. 1. ```
       var string = "Jhon john";
       console.log(string.replace(/hn/,"ana"));// "Jhana john"
       console.log(string.replace(/hn/g,"ana"));  // "Jhana joana"
       ```
11. **合并数组**

    合并两个数组一般使用 Array.concat\(\)，这其将消耗大量的内存来存储新创建的数组;所以这并不适用于两个大型数组，对于大型数组，使用：Array.push.apply\(array1, array2\);这种方法不是用来创建一个数组，其只是将两个数组合并子一起。

12. **将`NodeList`转换成数组**

    如果你运行`document.querySelectorAll(“p”)`函数时，它可能返回DOM元素的数组，也就是`NodeList`对象。但这个对象不具有数组的函数功能，比如`sort()`、`reduce()`、`map()`、`filter()`等。为了让这些原生的数组函数功能也能用于其上面，需要将节点列表转换成数组。可以使用`[].slice.call(elements)`来实现：

    ```
    var elements = document.querySelectorAll("p"); // NodeList
    var arrayElements = [].slice.call(elements); // Now the NodeList is an array
    var arrayElements = Array.from(elements); // This is another way of converting NodeList to Array
    ```

13. **数组元素的洗牌**

    对于数组元素的洗牌，不需要使用任何外部的库，比如Lodash，只要这样做：

    ```
    var list = [1, 2, 3];
    console.log(list.sort(function() { return Math.random()-0.5}));//[2,1,3]
    ```



