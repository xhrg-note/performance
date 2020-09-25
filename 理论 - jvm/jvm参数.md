## 内存：

```
-Xss（-XX:ThreadStackSize） 每个线程的堆栈大小
-Xms （ -XX:InitialHeapSize ）  初始堆   通过JMX查询时候会寻找全称
-Xmx ( -XX:MaxHeapSize )        最大堆
-Xmn 新生代，eden和两个s代
-XX:PermSize     XX:MaxPermSize  永久带
-XX:NewSize and -XX:MaxNewSize    新生代
-XX:NewRatio=3 指定老年代/新生代为3/1. 老年代占堆大小的 3/4 ，新生代占 1/4 .
-XX:SurvivorRatio=10 表示伊甸园区(Eden)是 幸存区To 大小的10倍
-XX:MaxTenuringThreshold=10设定老年代阀值的上限为10,
-XX:TargetSurvivorRatio=90  幸存区空间目标使用率为90%。
-XX:LargePageSizeInBytes   内存页的大小 
```

## 日志：

```
-XX:+PrintGC（ -verbose:gc） 开启了简单GC日志模式
-XX:PrintGCDetails 开启了详细GC日志模式
-XX:+PrintGCTimeStamps  将时间和日期也加到GC日志中
-XX:+PrintGCDateStamps 每一行就添加上了绝对的日期和时间。
-Xloggc
-XX:+PrintTLAB  查看TLAB空间的使用情况
-XX:ErrorFile=/path/error.log  jvm崩溃时日志
```


## GC-CMS：
```
-XX：+UseConcMarkSweepGC   激活CMS收集器 默认HotSpot JVM使用的是并行收集器
-XX：UseParNewGC 激活年轻代使用多线程并行执行垃圾回收
-XX：+CMSConcurrentMTEnabled 并发的CMS阶段将以多线程执行  反之-XX：-CMSConcurremntMTEnabled
-XX：ConcGCThreads=4   定义并发CMS过程运行时的线程数为4
XX:CMSInitiatingOccupancyFraction=75 第一次CMS垃圾收集会在老年代被占用75%时被触发（默68）
-XX:+CMSClassUnloadingEnabled   CMS收集器默认不会对永久代进行垃圾回收， 希望对永久代进行垃圾回收
-XX:+CMSIncrementalMode 增量模式
-XX:+ExplicitGCInvokesConcurrent  JVM无论什么时候调用系统GC，都执行CMS GC，而不是Full GC
 -XX:+ExplicitGCInvokesConcurrentAndUnloadsClasses 保证当有系统GC调用时，永久代也被包括进CMS垃圾回收的范围内
-XX:+UseCMSCompactAtFullCollection 开启对年老代的压缩
-XX:CMSFullGCsBeforeCompaction=3  3次Full GC后，对年老代进行压缩
```



## GC-PS：
```
-XX:+UseSerialGC
-XX:+UseParallelGC
-XX:+UseParallelOldGC
-XX:ParallelGCThreads=6表示每次并行垃圾收集将有6个线程执行
XX:GCTimeRatio=9我们要求应用程序线程在整个执行时间中至少9/10是活动的(因此，GC线程占用其余1/10)
-XX:GCTimeRatio=<value>告诉JVM最大暂停时间的目标值(以毫秒为单位)
-XX:MaxGCPauseMillis  每次年轻代垃圾回收的最长时间(最大暂停时间)
-XX:+ScavengeBeforeFullGC  Full GC前调用YGC
```



## 其他
```
-XX:+DisableExplicitGC 标志自动将System.gc()调用转换成一个空操作
-server and -client              运行模式
-XX:+TieredCompilation   多层编译
-Xint                                   强制不做优化
-Xcomp 
-Xmixed                                混合模式
-XX:+PrintCompilation         JIT编译过程
-XX:+CITime                          JIT统计信息 
-XX:+PrintFlagsFinal
-XX:+PrintFlagsInitial
-XX:+PrintCommandLineFlags
-XX:+HeapDumpOnOutOfMemoryError     让JVM在发生内存溢出时自动的生成堆内存快照
-XX:HeapDumpPath=<path>来改变默认的堆内存快照生成路径，<path>可以是相对或者绝对路径。
-XX:OnOutOfMemoryError = "sh ~/cleanup.sh"  运行一个脚本
-XX:+PrintTenuringDistribution 指定JVM 在每次新生代GC时，输出幸存区中对象的年龄分布
-XX:+NeverTenure , 对象永远不会晋升到老年代
-XX:+AlwaysTenure, 表示没有幸存区,所有对象在第一次GC时，会晋升到老年代。
-XX:MaxTenuringThreshold  垃圾最大年龄
-XX:+AggressiveOpts  加快编译
-Xnoclassgc  禁止classgc
-XX:+UseBiasedLocking  锁机制的性能改善
-XX:SoftRefLRUPolicyMSPerMB  每兆堆空闲空间中SoftReference的存活时间
-XX:PretenureSizeThreshold  对象超过多大是直接在旧生代分配
-XX:TLABWasteTargetPercent      TLAB占eden区的百分比
-XX:+CollectGen0First  FullGC时是否先YGC
```