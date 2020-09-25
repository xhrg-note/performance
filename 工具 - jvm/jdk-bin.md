## jstat


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