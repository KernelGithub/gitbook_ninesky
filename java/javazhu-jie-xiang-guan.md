1、java的三种内置注解：

* @Override --- 覆盖父类时，要加上，这样，当父类的方法被删除或修改了，编译器会提示错误。不然的话，当父类被修改，子类就不会覆盖，调用时直接调用的是父类的方法。[Java覆盖注解](http://www.journaldev.com/817/overriding-methods-in-java-always-use-override-annotation)。
* @Deprecated ----当我们想要让编译器知道一个方法已经被弃用\(deprecate\)时，应该使用这个注解。Java推荐在javadoc中提供信息，告知用户为什么这个方法被弃用了，以及替代方法是什么。
* @SuppressWarnings – 这个注解仅仅是告知编译器，忽略它们产生了特殊警告，比如：在  
  [java泛型](http://www.journaldev.com/1663/java-generics-tutorial-example-class-interface-methods-wildcards-and-much-more)

  中使用原始类型。它的保持性策略\(retention policy\)是SOURCE，在编译器中将被丢弃。

2、注解的使用：参考 [http://www.importnew.com/14479.html](http://www.importnew.com/14479.html)

3、自定义注解说明

* 注解方法不能有参数
* 注解方法返回类型局限于原始类型，字符串、枚举，注解，或以上类型构成的数组
* 注解方法可以包含默认值
* 注解可以包含与其绑定的元注解，元注解为注解提供信心，有一下4种：
  * @Document  --- 表示使用该注解的元素应该被javadoc或类似工具文档化，它应用于类型声明，类型声明的注解会影响客户端对注解元素的使用。如果一个类型声明添加了Document注解，那么它的注解会成为被注解元素的公共API的一部分。
  * @Target  --- 表示支持注解的程序元素的种类，可能的有ElementType.\[type,method,constructor,filed\]等，如果Target注解存在，那么该注解可以在任何程序元素上使用。
  * @Inherited --- 表示当这个注解在某个类上使用后，这个类的子类将自动被改注解标记。
  * @Retention  ---  表示注解类型保留时间的长短，参数 RetentionPolicy.\[source,class,runtime\]

4、 







