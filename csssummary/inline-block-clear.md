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
      | chrome | word-space: -6px |
      | IE | word-space: -4px |
   3. 兼容IE6、IE7

   4. 解决设置inline-block触发块元素，具有了layout的特性，然后设置display:inlie使块元素呈现内联元素，此时layout的特性不会消失。

   5. 直接设置display:inline,使用zoom:1触发layout

   6. 兼容所有浏览器的方法：

      1. display:inline-block;

         \*display:inline;/\*ie7-6\*/

         \*zoom:1;/\*ie7-6\*/

3. i.



