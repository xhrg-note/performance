
## ab


```
基本用法：：：
ab -n 100 -c 10 http://test.com/
其中－n表示请求数，－c表示并发数



用例：：：
ab －n 100 －C key＝value http://test.com/  # -C表示Cookie
ab -n 100 -H “Cookie: Key1=Value1; Key2=Value2” http://test.com/ # -H 表示header



参数：：：：
-n:总共的请求执行数，缺省是1；
-c:并发数，缺省是1；
-t:测试所进行的总时间，秒为单位，缺省50000s
-p:POST时的数据文件
-w:以HTML表的格式输出结果 

```