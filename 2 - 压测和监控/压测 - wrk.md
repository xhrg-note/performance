


工具优势：xxx


* wrk：https://www.cnblogs.com/quanxiaoha/p/10661650.html



常用例子

```
wrk -t4 -c1000 -d30s --latency www.baidu.com
```


参数说明

```
-t --threads   开启的线程数，用于控制并发请求速度。最大值一般是cpu总核心数的2-4倍
-c --conections 保持的连接数（会话数）
-d --duration 压测持续时间(s)
-s --script 加载lua脚本（post请求写一些参数到脚本里）
-H --header 在请求头部添加一些参数
--latency 压测报告输出请求回包花费时间分布
--timeout 请求的最大超时时间(s),这个很有用

作者：许亚文
链接：https://juejin.im/post/6844903962244579341
来源：掘金
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```
