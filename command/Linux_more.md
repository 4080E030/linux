# more 
## more就是可以一頁一頁讀檔案
```
root@kali:~# ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos  yersinia.log
root@kali:~# more yersinia.log(內部的資料夾
# yersinia v0.8.2 started in kali on Mon Jul 22 10:08:05 2019

Network Interface eth0

 eth0 iflinkname EN10MB
 eth0 iflinkdesc Ethernet
 eth0 MAC = 0800.2789.03db
Network Interface lo

 lo iflinkname EN10MB
 lo iflinkdesc Ethernet
 lo MAC = 0000.0000.0000
Network Interface nflog
Network Interface nfqueue
Network Interface usbmon1
pcap_open_live failed: usbmon1: Can't open USB bus file /sys/kernel/debug/usbmon/1t: No such file or directory
 g00dbye function called from 2A202A00

 th_uptime thread = 29A00700

 ints_destroy started...
 ints_destroy killing pcap_listener(706746112)...

 thread_destroy 2A202A00 destroying 2A201700...
 thread_destroy 2A202A00 after PTHREAD_JOIN 2A201700...
 ints_destroy finished...
 Showing MOTD..
# yersinia finished on Mon Jul 22 10:08:06 2019

# yersinia v0.8.2 started in kali on Mon Jul 22 10:09:44 2019

Network Interface eth0

 eth0 iflinkname EN10MB
 eth0 iflinkdesc Ethernet
 eth0 MAC = 0800.2789.03db
Network Interface lo

 lo iflinkname EN10MB
 lo iflinkdesc Ethernet
 lo MAC = 0000.0000.0000
Network Interface nflog
Network Interface nfqueue
Network Interface usbmon1
pcap_open_live failed: usbmon1: Can't open USB bus file /sys/kernel/debug/usbmon/1t: No such file or directory

 gtk_gui_th = 75987700

 th_uptime thread = 76188700
Exiting GTK mode...

 gtk_gui_th_exit start...
 gtk_gui_th_exit finish...
 g00dbye function called from 7698AA00

 ints_destroy started...
 ints_destroy killing pcap_listener(1989711616)...

 thread_destroy 7698AA00 destroying 76989700...
 thread_destroy 7698AA00 after PTHREAD_JOIN 76989700...
 ints_destroy finished...
 Showing MOTD..
# yersinia finished on Mon Jul 22 10:22:26 2019
```
# 更多more指令
```
root@kali:~# more --help

Usage:
 more [options] <file>...

A file perusal filter for CRT viewing.

Options:
 -d          display help instead of ringing bell
 -f          count logical rather than screen lines
 -l          suppress pause after form feed
 -c          do not scroll, display text and clean line ends
 -p          do not scroll, clean screen and display text
 -s          squeeze multiple blank lines into one
 -u          suppress underlining
 -<number>   the number of lines per screenful
 +<number>   display file beginning from line number
 +/<string>  display file beginning from search string match

     --help     display this help
 -V, --version  display version

For more details see more(1).

```
