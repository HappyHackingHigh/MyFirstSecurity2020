#
```
理論上所有的 Linux 發佈版本應該都要遵守檔案系統的標準（Filesystem Hierarchy Standard, FHS），但根據發佈版本不同或有差異，不過大致上檔案系統架構如下：

/bin, /sbin
/bin 主要放置一般使用者可以操作的指令，/sbin 放置系統管理員可以操作的指令。連結到 /usr/bin，/usr/sbin

/boot
主要放置開機相關檔案

/dev
放置 device 裝置檔案，包話滑鼠鍵盤等

/etc
主要放置系統檔案

/home, /root
/home 主要是一般帳戶的家目錄，/root 為系統管理者的家目錄

/lib, /lib64
主要為系統函式庫和核心函式庫，若是 64 位元則放在 /lib64。連結到 /usr/lib, /usr/lib64

/proc
將記憶體內的資料做成檔案類型

/sys
與 /proc 類似，但主要針對硬體相關參數

/usr
/usr 全名為 unix software resource 縮寫，放置系統相關軟體、服務（注意不是 user 的縮寫喔！）

/var
全名為 variable，放置一些變數或記錄檔

/tmp
全名為 temporary，放置暫存檔案

/media, /mnt
放置隨插即用的裝置慣用目錄， /mnt 為管理員/使用者手動掛上（mount）的目錄

/opt
全名為 optional，通常為第三方廠商放置軟體處

/run
系統進行服務軟體運作管理處

/srv
通常是放置開發的服務（service），如：網站服務 www 等
```
