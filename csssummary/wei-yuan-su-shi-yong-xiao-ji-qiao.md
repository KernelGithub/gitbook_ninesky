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



