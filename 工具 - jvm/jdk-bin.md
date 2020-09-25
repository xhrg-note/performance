## jstat

```
jstat -gcutil 5678 1000 5 #每1秒（1000毫秒）打印5次进程id是5678


```

## jps
```
> jps #查看java进程
```


## jmap

```
> jmap -heap pid
> jmap -histo pid | grep 'key'        ##查看对象存活数量
> jmap -dump:live,file=dump.bin PID      ##内存转储   
```


## jcmd

```
jcmd pid VM.native_memory baseline
jcmd pid VM.native_memory summary

```


## visualvm 可视化工具，有很多插件