# rmdir 
### mkdir是創建目錄 rmdir就是刪除目錄
##### 若是欲移除的目錄裡頭有檔案或其他目錄存在，就無法移除．
```
root@kali:~# mkdir 55688
root@kali:~# ls 
55688  Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos  yersinia.log
root@kali:~# rmdir 55688
root@kali:~# ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos  yersinia.log
```
# 更多rmdir cmd 
```
root@kali:~# rmdir --help
Usage: rmdir [OPTION]... DIRECTORY...
Remove the DIRECTORY(ies), if they are empty.

      --ignore-fail-on-non-empty
                  ignore each failure that is solely because a directory
                    is non-empty
  -p, --parents   remove DIRECTORY and its ancestors; e.g., 'rmdir -p a/b/c' is
                    similar to 'rmdir a/b/c a/b a'
  -v, --verbose   output a diagnostic for every directory processed
      --help     display this help and exit
      --version  output version information and exit

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Full documentation at: <https://www.gnu.org/software/coreutils/rmdir>
or available locally via: info '(coreutils) rmdir invocation'
```
