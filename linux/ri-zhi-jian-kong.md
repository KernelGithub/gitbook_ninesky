1. less \*.log，然后/查找关键，找得会高亮，然后shift+f，实时监听
2. 通常我们非常需要查找指定时间端的日志

   sed -n '/2014-12-17 16:17:20/,/2014-12-17 16:17:36/p'  test.log  \# 命令中的日期必须是日志中打印出来的日志，否则无效

3. cat -n test.log \|grep "地形"  得到关键日志的行号

4. cat -n test.log \|tail -n +92\|head -n 20

   tail -n +92表示查询92行之后的日志

   head -n 20 则表示在前面的查询结果里再查前20条记录



