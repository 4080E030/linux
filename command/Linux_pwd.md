# pwd 
#### 顯示目前所在目錄
```
root@kali:~# pwd
/root
root@kali:~# cd 2222/ 
root@kali:~/2222# pwd
/root/2222
root@kali:~/2222# 

```
# pwd more cmd 
```
root@kali:~# pwd --help
pwd: pwd [-LP]
    Print the name of the current working directory.
    
    Options:
      -L	print the value of $PWD if it names the current working
    		directory
      -P	print the physical directory, without any symbolic links
    
    By default, `pwd' behaves as if `-L' were specified.
    
    Exit Status:
    Returns 0 unless an invalid option is given or the current directory
    cannot be read.

```
