**GC**  
1. -XX:+PrintGCDetail   ![](/assets/gc1.png)    GC日志：**\[GC \(Allocation Failure\) \[PSYoungGen: 1024K-&gt;488K\(1536K\)\] 1024K-&gt;648K\(19968K\), 0.0007228 secs\] \[Times: user=0.05 sys=0.00, real=0.00 secs\]**  
   从这条日志可以看出新生代YoungGen分配失败，1024K-&gt;488K\(1536\)表示GC前已使用-&gt;GC后已使用\(该区域总容量\),\[\]之外表示Java堆GC前已使用-&gt;GC后已使用\(Java堆总容量\)，最后为GC耗时。  
   从上图我们可以看出GC的主要收集区域，包括PSYoungGen\(年轻代\)、ParOldGen\(老年代\)、Metaspace\(元数据区\)  
2.  
       ![](/assets/GC2.png)  
   iii. -XX:PrintHeapAtGC 打印GC前后的堆分配信息



     从上图我们可以看到添加了\*\*-XX:PrintHeapAtGC\*\*参数后可以清楚的看到堆分配信息，而且还可以看到 GC 数据的移动 PSYoungGen.eden space -&gt; PSYoungGen.from space -&gt; ParOldGen.object space。

iv.  -XX:+TraceClassLoading



1. **堆分配参数** -Xms: total Memory，就是堆初始化大小，它的意思是一开始限定堆大小为多少，如果不够则可以扩充，但必须小于最大堆大小。 ,-Xmx :maxMemory 分配空间不能超过最大堆内存大小，否则会抛出 OutofMemory 异常

   1. 关系图

      ![](/assets/d1.png)

   2. [参看网站](http://blog.csdn.net/wwh578867817/article/details/51883476) 我们可以根据自己应用的时机情况来动态调整该参数，提高性能，一般在高并发请款下，建议 -Xms 和 -Xmx 值相同，避免内存**收缩/增大**出现的性能问题。

2. -Xmn:设置新生代大小、-newRatio：设置新生代与老年代的比率、-SurvivorRatio:设置新生代中**Eden space**和**Survivor space**的大小



