# rm  option files
# 刪除檔案或目錄 
#### r：刪除其下的檔案及目錄    
#### i：刪除時提出警告
#### f：刪除時不提出警告
#### d：刪除目錄，即使該目錄並非空目錄
```
root@kali:~# ls 
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  test  Videos  yersinia.log
root@kali:~# rm -d test
root@kali:~# ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos  yersinia.log
```
# 也可使用 rm -rf
```
root@kali:~# mkdir test
root@kali:~# ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  test  Videos  yersinia.log
root@kali:~# rm -rf test
root@kali:~# ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos  yersinia.log
```
# 更多rm cmd 
```
root@kali:~# rm --help
Usage: rm [OPTION]... [FILE]...
Remove (unlink) the FILE(s).

  -f, --force           ignore nonexistent files and arguments, never prompt
  -i                    prompt before every removal
  -I                    prompt once before removing more than three files, or
                          when removing recursively; less intrusive than -i,
                          while still giving protection against most mistakes
      --interactive[=WHEN]  prompt according to WHEN: never, once (-I), or
                          always (-i); without WHEN, prompt always
      --one-file-system  when removing a hierarchy recursively, skip any
                          directory that is on a file system different from
                          that of the corresponding command line argument
      --no-preserve-root  do not treat '/' specially
      --preserve-root[=all]  do not remove '/' (default);
                              with 'all', reject any command line argument
                              on a separate device from its parent
  -r, -R, --recursive   remove directories and their contents recursively
  -d, --dir             remove empty directories
  -v, --verbose         explain what is being done
      --help     display this help and exit
      --version  output version information and exit

By default, rm does not remove directories.  Use the --recursive (-r or -R)
option to remove each listed directory, too, along with all of its contents.

To remove a file whose name starts with a '-', for example '-foo',
use one of these commands:
  rm -- -foo

  rm ./-foo

Note that if you use rm to remove a file, it might be possible to recover
some of its contents, given sufficient expertise and/or time.  For greater
assurance that the contents are truly unrecoverable, consider using shred.

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Full documentation at: <https://www.gnu.org/software/coreutils/rm>
or available locally via: info '(coreutils) rm invocation'
```
