# sass基本用法

#### 说明：SASS是CSS3的一个扩展，增加了规则嵌套、变量、混合、选择器继承等等。通过使用命令行的工具或web框架插件把它转换成标准的、格式良好的CSS代码。

SCSS即是SASS的新语法，是Sassy CSS的缩写，是CSS3语法的超集，也就是说所有有效的CSS3样式也同样适合于SASS

1. 在scss中使用变量
   ```
   $blue: #3bbfce;
   $margin:16px;
   .content { border-color:$blue;margin: $margin/2 }
   ```
2. SCSS嵌套
   1. 嵌套规则
   ```
	   //嵌套功能避免了重复输入父选择器，而且令复杂的css结构更加易于管理
	   //用法一
	   #main p {
	       color: #000;
	       width: 10vw;
	       .redbox {
	           background-color: #f00;
	           color: #111;
	       }
	   }
	   //<===>
	   #main p{ color: #000;width: 10vw; }
	   #main p .redbox {background-color: #f00; color: #111; }
   ```





