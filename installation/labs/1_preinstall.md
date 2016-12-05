Current VMSwappiness is 30 

```
$ cat /proc/sys/vm/swappiness
>> 30

```

Change VMSwappiness to 1

```

$ sudo sysctl vm.swappiness=1
$ cat /proc/sys/vm/swappiness
>> 1
```