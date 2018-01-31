# pg\_ctl -- 启动、停止、重启 PostgreSQL

* ./pg\_ctl start \[-w\] \[-s\] \[-D datadir\] \[-l filename\] \[-o options\] \[-p path\]   -l : 标准输出和错误输出将被定向到一个日志文件

* ./pg\_ctl stop \[-W\] \[-s\] \[-D datadir\] \[-m s\[mart\] \| f\[fast\] \| i\[mmediate\]\]  -m: 默认值是Smart，即等待所有客户端主动中断连接。fast，不会等待客户端中断连接，所有活跃事务都会被回滚，并且客户端都会被强制断开。immediate 将在没有关闭干净的情况下强行退出，这么做将导致在重新启动的时候恢复。

* ./pg\_ctl restart \[-W\] \[-s\] \[-D datadir\] \[-m s\[mart\] \| f\[fast\] \| i\[mmediate\]\] \[-o options\]

* ./pg\_ctl reload \[-s\] \[-D datadir\] 重读配置文件

* ./pg\_ctl status \[-D datadir\]

* ./pg\__ctl kill \[signal\_\_name\] \[process_\_id\_\] 这个功能主要用于win ，因为win下没有kill命令。使用--help查看支持的信号列表。

* ./pg\_ctl register \[-N servicename\] \[-U username\] \[-P password\] \[-D datadir\] \[-W\] \[-o options\]  模式允许你在win上注册服务

* ./pg\_ctl unregister \[-N servicename\] 删除用register命令注册的系统服务。

参数说明

LInux：

* -D datadir 指定data位置，忽略这使用PGDATA环境变量
* -l filename 将日志输出到指定的文件上，umask设置为077，因此，默认是不允许其他用户的任何操作。
* -m mode  三种关闭模式，可以只写首字母
* -s 只打印错误，不打印提示信息
* -o options 声明要直接传递给postgres的选项。参数通常都用引号\(单/双\)包围，保证他们是一个整体传递。
* -w 等待启动或者关闭的完成\(60 秒超时\)，这个参数是关闭时的缺省值。成功的关闭是以删除 PID 文件为标志的。对于启动而言，一次成功的psql -l 就标志着成功。pg\_ctl 将企图使用对 psql 合适的端口，如果存在 **PGPORT**环境变量，那么将用它。否则，它将查找在postgresql.conf 文件里是否设置了一个端口。如果都没有，它将使用 PostgreSQL 编译时的缺省端口\(缺省 5432\)。在等待的时候，pg\_ctl 将根据启动或者关闭的成功状况返回一个准确的退出代码。
* -W 不等待启动或者停止，缺省值

Window

* —N servicename 要注册的系统服务名字，用户服务名和显示名
* -P passwd 用户启动服务口令
* -U username 启动服务用户的用户名，域用户，使用DOMAIN\username 格式。

环境变量

* PGDATA  确认数据目录
* PGPORT psql的缺省端口（有-w 项使用）

文件

* postmaster.pid  帮助pg\_ctl判断服务器当前是否在运行
* postmaster.opts.default  如果这个文件存在于数据目录，pg\_ctl \(在 start 模式下\)将把文件地内容当作传递给 postgres 命令的选项传递过去，除非被 -o 选项覆盖。
* postgresql.conf 这个文件在数据目录中，会分析它以查找和psql 一起用的合适的端口\(在start 模式里给出 -w 的时候\)。

例子

* 等待服务启动完成后退出：pg\_ctl -w start
* 使用5443端口，且不带fsync运行，使用：pg\_ctl -o "-F -p 5443" start



