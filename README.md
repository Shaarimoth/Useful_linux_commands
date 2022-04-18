# Useful_linux_commands
Just Linux commands for your daily activities


## Delete filed older then n days

For example delete filed older than 30 days

```
find . -type f -mtime +30 -exec rm {} \;
```

## CPU

IOSTAT:
```
iostat -c
```
Sort processes by CPU usage:
```
ps -eo ppid,user,bsdstart,bsdtime,%cpu,args --sort=-%cpu

top -o %CPU

ps u | sort -k 1 -r | head -5
```

## Memory

Sort processes by Memory usage:
```
ps -eo ppid,user,%mem,size,vsize,comm --sort=-size

ps aux | awk '{print $6/1024 " MB\t\t" $11}' | sort -n

ps -e -o pid,vsz,comm= | sort -n -k 2
```

## Free space

Display a list of directories by free space usage:
```
du -h --max-depth=1 -x / 
```



