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
   2. | browser | margin值\(左右\) |
      | :--- | :--- |
      | 火狐 | margin:-4px |
      | chrome | margin:-3px |
      | IE | margin:-2px |
   3. 
3. i.

