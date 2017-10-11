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

**缓存array.length**

1. 
2. 




