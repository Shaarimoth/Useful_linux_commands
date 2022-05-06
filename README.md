# Useful Linux commands
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
____________________________
Sort processes by CPU usage:
```
ps -eo ppid,user,bsdstart,bsdtime,%cpu,args --sort=-%cpu

top -o %CPU

ps u | sort -k 1 -r | head -5
```
____________________________
dstat example with output:
```
dstat -ta --top-cpu --noheader --output system-top-cpu.csv 5
```

## Memory

Sort processes by Memory usage:
```
ps -eo ppid,user,%mem,size,vsize,comm --sort=-size

ps aux | awk '{print $6/1024 " MB\t\t" $11}' | sort -n

ps -e -o pid,vsz,comm= | sort -n -k 2
```
____________________________
dstat example with output:
```
dstat -ta --top-mem --noheader
```

## Free space

Display a list of directories by free space usage:
```
du -h --max-depth=1 -x / 
```

## Find
Search files with a specific format and size. Examples:
```
find / -type f -name "*.JPG" -size +10M

find / -type f -name "*.log" -size +1M
```
____________________________
Find Files With specific Permissions:
```
find . -type f -perm 0777 -print
find . -type f -perm 0755 -print
find . -type f ! -perm 777
```
____________________________
Find all hidden files:
```
find tmp -type f -name ".*"
```
____________________________
Find Changed Files in Last 1 Hour:
```
# 1 Hour
find / -cmin -60
```
