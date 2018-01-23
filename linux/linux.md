1. 查看端口占用情况，只能查看当前用户
   1. lsof -i:5444
      ![](/assets/lsof.png)
      ![](/assets/lsof2.png)
   2. netstat -tunlp 用于显示tcp，udp的端口和进程等相关情况
      ![](/assets/netstat.png)![](/assets/netstat2.png)



