# 去除inline-block元素间间距的N种方法

**现象**：正真意义上的inline-block水平呈现的元素间，换行显示或空格分隔的情况下会有间距,eg：

&lt;input/&gt;&lt;input type="submit" /&gt;

![](/assets/import.png)

更改inline-block水平元素为inline-block水平，也会有该问题。

**修改方法**：

1. 去掉html中的空格
   1. ![](/assets/1t.png)![](/assets/2.png)![](/assets/3.png)
2. margin

   1. | browser | margin\(right left\) |
      | :--- | :--- |
      | 火狐 | margin:-4px |
      | chrome | margin:-3px |
      | IE | margin:-2px |
   2. | browser | word-space值\(左右\) |
      | :--- | :--- |
      | 火狐 | word-space: -8px |
      | chrome | word-space: -6px \(display: inline-table;\) |
      | IE | word-space: -4px |
   3. .space {letter-spacing: -3px;}   .space a {letter-spacing: 0;}

   4. 兼容IE6、IE7

   5. 解决设置inline-block触发块元素，具有了layout的特性，然后设置display:inlie使块元素呈现内联元素，此时layout的特性不会消失。直接设置display:inline,使用zoom:1触发layout,兼容所有浏览器的方法

      ```
       isplay:inline-block;

      \*display:inline;/\*ie7-6\*/

      \*zoom:1;/\*ie7-6\*/
      ```

3. inline和block区别

   1. 块级元素会独占一行，其宽度自动填满其父元素宽度，行内元素会独占一行，相邻的行内元素会排在同一行里，知道一行排不下，才会换行，其宽度随元素的内容二变化。

   2. 块级元素可以设置width、height属性，行内元素设置无效。（块级元素设置了宽度还是会独占一行）

   3. 块级元素可以设置margin和padding，行内元素的水平方向的padding-left,padding-right,margin-right都产生边距效果，单竖直方向的padding-top、padding-boottom、margin-top,margin-bottom都不会参数边距效果（水平有效，竖直无效）

   4. 块级元素p只能包含inline元素



