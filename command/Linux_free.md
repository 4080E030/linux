# free 指令運用
#### 用來察看記憶體的指令
```
root@kali:~# free
              total        used        free      shared  buff/cache   available
Mem:        2042752     1090240      217728        7364      734784      788712
Swap:       2095100           0     2095100
```
# Men 記憶體
```
total 總共有多少容量
used  使用了多少
free  可用的量有多少
shared 共享內存的大小
buff 被緩衝區佔用的位子
cache 被緩存佔用的位子
available 顯示還可以被應用程式所使用的大小
```

# buff/cache 廢話
```
buff/cache
先來提一個問題： buffer 和 cache 應該是兩種類型的內存，但是 free 命令為什麼會把它們放在一起呢？
要回答這個問題需要我們做些準備工作。讓我們先來搞清楚 buffer 與 cache 的含義。
buffer 在操作系統中指 buffer cache， 中文一般翻譯為 "緩衝區"。要理解緩衝區，必須明確另外兩個概念："扇區" 和 "塊"。扇區是設備的最小尋址單元，也叫 "硬扇區" 或 "設備塊"。塊是操作系統中文件系統的最小尋址單元，也叫 "文件塊" 或 "I/O 塊"。每個塊包含一個或多個扇區，但大小不能超過一個頁面，所以一個頁可以容納一個或多個內存中的塊。
當一個塊被調入內存時，它要存儲在一個緩衝區中。每個緩衝區與一個塊對應，它相當於是磁盤塊在內存中的表示(下圖來自互聯網)：



注意，buffer cache 只有塊的概念而沒有文件的概念，它只是把磁盤上的塊直接搬到內存中而不關心塊中究竟存放的是什麼格式的文件。
cache 在操作系統中指 page cache，中文一般翻譯為 "頁高速緩存"。頁高速緩存是內核實現的磁盤緩存。它主要用來減少對磁盤的 I/O 操作。
具體地講，是通過把磁盤中的數據緩存到物理內存中，把對磁盤的訪問變為對物理內存的訪問。頁高速緩存緩存的是內存頁面。緩存中的頁來自對普通文件、塊設備文件(這個指的就是 buffer cache 呀)和內存映射文件的讀寫。
頁高速緩存對普通文件的緩存我們可以這樣理解：當內核要讀一個文件(比如 /etc/hosts)時，它會先檢查這個文件的數據是不是已經在頁高速緩存中了。
如果在，就放棄訪問磁盤，直接從內存中讀取。這個行為稱為緩存命中。如果數據不在緩存中，就是未命中緩存，此時內核就要調度塊 I/O 操作從磁盤去讀取數據。然後內核將讀來的數據放入頁高速緩存中。
這種緩存的目標是文件系統可以識別的文件(比如 /etc/hosts)。
頁高速緩存對塊設備文件的緩存就是我們在前面介紹的 buffer cahce。因為獨立的磁盤塊通過緩衝區也被存入了頁高速緩存(緩衝區最終是由頁高速緩存來承載的)。

到這裡我們應該搞清楚了：無論是緩衝區還是頁高速緩存，它們的實現方式都是一樣的。緩衝區只不過是一種概念上比較特殊的頁高速緩存罷了。
那麼為什麼 free 命令不直接稱為 cache 而非要寫成 buff/cache？這是因為緩衝區和頁高速緩存的實現並非天生就是統一的。
在 linux 內核 2.4 中才將它們統一。更早的內核中有兩個獨立的磁盤緩存：頁高速緩存和緩衝區高速緩存。前者緩存頁面，後者緩存緩衝區。

```

# more free cmd 
```
 root@kali:~# free --help

Usage:
 free [options]

Options:
 -b, --bytes         show output in bytes
     --kilo          show output in kilobytes
     --mega          show output in megabytes
     --giga          show output in gigabytes
     --tera          show output in terabytes
     --peta          show output in petabytes
 -k, --kibi          show output in kibibytes
 -m, --mebi          show output in mebibytes
 -g, --gibi          show output in gibibytes
     --tebi          show output in tebibytes
     --pebi          show output in pebibytes
 -h, --human         show human-readable output
     --si            use powers of 1000 not 1024
 -l, --lohi          show detailed low and high memory statistics
 -t, --total         show total for RAM + swap
 -s N, --seconds N   repeat printing every N seconds
 -c N, --count N     repeat printing N times, then exit
 -w, --wide          wide output

     --help     display this help and exit
 -V, --version  output version information and exit

For more details see free(1).

```

# 參考資料
```
https://cizixs.com/2015/10/01/linux-memory-management-through-free/
```
