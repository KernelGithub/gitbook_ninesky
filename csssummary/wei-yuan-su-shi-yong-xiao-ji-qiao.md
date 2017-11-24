# 伪元素实用小技巧

![](/assets/1)

1. 清除浮动
   1. 何谓清除浮动一？一个父元素所有子元素如果都是浮动的，那么这个父元素是没有高度的；父元素并没有脱离正常的文档流，仍然占据正常文档流的空间;
   2. 如果这个父元素的相邻元素是行内元素，那么这个行内元素将会在这个父元素的区域内见缝插针，找一块放得下他的地方。
   3. 如果相邻的元素是一个块级元素，那么设置这个块级的maring-top将会以这个父元素的起始位置作为起点。
   4. 如何解决高度塌陷：把父容器的高度撑起来，考虑到浮动了的元素并没有脱离正常文档流，而其它元素会围绕着它环绕，所以清除浮动简单有效的办法就是让环绕的元素不可环绕，把它变成一把尺子，放在最后面，把所有浮动的元素顶起来，而这把尺子就是一个设置了clear的块级元素。因为块级元素会换行，并且设置它两边不能跟着浮动的元素，所以它就跑到浮动元素的下面去，就像一把尺子把浮动元素的内容给顶起来了。而这个可以用一个after实现，因为after就是最后一个子元素：
      1. ```
         .clearfix:after {content:"";display:block;clear:both}
         ```
2. 画分割线
   1. ![](/assets/3)一个P标签，左右两条线用before和after画出来：
   2. ```
      p {margin-top:100px;text-align:center;}
      p:before,p:after {content:"";position:absolute;top:110px;height:1px;background-color:red;width:200px }
      P:after {right: 0 }
      p:before {left: 0}
      ```
3. 计数器  
   1. [http://www.zhangxinxu.com/study/201408/css-counters-string-break.html](http://www.zhangxinxu.com/study/201408/css-counters-string-break.html)  
   2. counter-reset: 属性创建或者重置一个或多个计数器\(重置默认值时chrome支持小数，其他的不支持，看鑫空间\)  
   3. counter-increment:属性递增一个或多个计数器值；  
   4. content: 与:before及:after伪元素配合使用，来插入生产内容  
   5. eg，判断checkbox选中了几个  
      1. `.choose { counter-reset:fruit 0; }    
         .choose input:checked{counter-increment:fruit; }    
         .choose:before { content: counter(fruit)}`

   ```
     ![](/assets/4)
   ```

4. 平行四边形

   1. 解决方案：伪元素，把样式应用到伪元素上，对伪元素进行变形，再把伪元素定位+层级放在所属元素的下面

   2. code

   3. ```
      .button {
          position: relative; display: inline-block; padding: .5em 1em; border:0; margin: .5em;
          background: transparent; color: white; text-transform: uppercase; text-decoration: none;
          font: bold 200%/1 sans-serif;
      }
      .button:before { 
          content:"";position:absolute; top:0;right:0;bottom:0;left: 0;z-index:-1;background:#58a;
          transform:skew(45deg);
      }
      //http://dabblet.com/gist/f2d98791ab1f0b238aa9
      ```

5. 梯形标签页

   1. 解决方案：三维世界中旋转一个矩形，由于透视关系，我们在二维图像上看到一个梯形，在结合平行四边形实现的方法便能实现。对元素使用了3D变形之后，其内部的变形效应是"不可逆转的"，和2D变形不同（2D变形内部的逆向变形可以抵消外部的变形效应）；为了让他的尺寸更好掌握，我们可以为他指定transform-origin：bottom;也可用scale\(\)对他在进行美观操作；

   2. code eg:

   3. ```
      .skew,.tixing{width:500px;height:80px;line-height:80px;text-align:center;position:relative}
      .skew:after,.tixing:after{
          content:'';width:500px;height:80px;background:pink;dispaly:inline-block;
          transform:perspective(20px) rotateX(5deg) scale(1.2);
          transform-origin:bottom;
          position:absolute;top:0;left:0;z-index:-1;
      }
      //http://dabblet.com/gist/1345dc9399dc8e794502
      ```

6. 多列均匀布局

   1. 通过给伪元素 :after 设置 inline-block 设置宽度 100% ，配合容器的 text-align: justify 就可以轻松实现多列均匀布局了那么为什么使用了 :after 伪元素之后就可以实现对齐了呢？原因在于 justify 只有在存在第二行的情况下，第一行才两端对齐，所以在这里，我们需要制造一个假的第二行，而 :after 伪元素正好再适合不过。

   2. code eg：

   3. ```
      .justify {position:relative;width:80%;height:24px;text-align:justify;margin-bottom:20px}
      .i { width:24px;line-height:24px;dispaly:inline-block;text-align:center;background:#333;color:white;
          border-radius:50%;overflow:hidden;font-style:normal; }
      .justify:after{
          content:"";width:100%;display:inline-block;position:relative;
      }
      ```
   4. 需要注意的是img/input等单标签是没有before/after伪元素的，因为是部分 type 不能有，如果你给img添加一个before，那么会被浏览器忽略。



