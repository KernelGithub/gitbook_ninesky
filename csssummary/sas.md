# sass基本用法

#### 说明：SASS是CSS3的一个扩展，增加了规则嵌套、变量、混合、选择器继承等等。通过使用命令行的工具或web框架插件把它转换成标准的、格式良好的CSS代码。

SCSS即是SASS的新语法，是Sassy CSS的缩写，是CSS3语法的超集，也就是说所有有效的CSS3样式也同样适合于SASS

1. **在scss中使用变量**
   ```
   $blue: #3bbfce;
   $margin:16px;
   .content { border-color:$blue;margin: $margin/2 }
   ```
2. **SCSS嵌套**

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

   2. 父选择器

      ```
      #main {
          color: #eee;
          a {
              font-weight: bold;
              &:hover {
                  color: red;
              }
          }
      }
      //<===>
      #main {color:#eee;}
      #main a {font-weight: bold;}
      #mian a:hover { color:red; }
      ```

   3. 嵌套属性\(一般都有对应的缩写\)

      ```
      .funky { 
          font: 20px/24px;{ 
              family: fantasy;
              size: 30em;
              weight:bold;
          }
      }
      //<====>

      .funky {
          font: 20px/24px;
          font-family: fantasy;
          font-weight: bold;
      }
      ```

3. **注释**

   1. 风格一：  /\*  comment  \*/， 多行注释，会被完整输出到编译后的css文件

   2. 风格二： //    ，单行注释，不会被输出到编译后的文件。

4. **@extend** ： 将一个选择器下的样式继承给另一个选择器

   1. 延伸class选择器

      ```
      //错误 和 严重错误
      .error { border: 1px #f00; background-color: #fdd;}
      .seriousError { @extend .error; border-width: 3px; }

      //注意:其他使用到.error的样式同样继承给.seriousError，例如，另一个样式.error.instrusion 使用了hacked.png做背景，
      //.seriousError同样也会使用hacked.png背景。
      //eg:上面error样式上：
      .error.intrusion { background-image: url("/image/hacked.png")}
      //<=====>
      .error,.seriousError{border: 1px #f00; background-color: #fdd; }
      .error.intrusion, .seriousError.intrusion  { background-image: url("/image/hacked.png")}
      .seriousError { border-width: 3px; }
      ```

   2. 延伸复杂的选择器，比如 .special.cool、a:hover、a.user\[href^="[http:// "\]](http://"]等例：]%28http://"]等例：]%28http://"]等例：]%28http://"]等例：%29\)\)

      ```
      //同class一样，a:hover的样式将继承给.hoverlink
      .hoverlink { @extend a:hover }
      a:hover { text-decoration: underline }
      ```



