#
```
https://blog.techbridge.cc/2017/12/23/linux-commnd-line-tutorial/
```
# 20基礎指令(一小時學完)
```

ls               列出基本資料夾資料。
ls -la           列出詳細資料和隱藏資料 -l 列出詳細資料 -a 列出隱藏資料。
ls *.php         列出部分檔案 *.php列出為 .php 的檔案。
pwd              印出目前工作目錄 print work directory。
```
```
cd              移動進入資料夾 change directory。
cd ./examples    移動到"目前"資料夾下的 examples 資料夾
cd ..            移動到上一層目錄
cd /             移動到根目錄 
```
```
mkdir            創建新資料夾
mkdir examples   建立examples資料夾
```
```
cp 複製檔案
echo "TEST" > README.md 先將字串 TEST 存入 README.md 文件中
cp README.md 複製"README.md"檔案 
```
```
mv 移動檔案或是重新命名檔案

mv README.md /examples/README.md  移動README.md到examples資料夾
$ mv README.md README_MV.md       README.md重新命名為README_MV.md
```
```
rm  刪除檔案 remove file

rm README.md    刪除README.md
rm *.js         刪除"目前"資料夾副檔名為.js的檔案
rm -f examples  刪除資料夾和所有檔案
```
```
cat 將文件印出在畫面上
cat README.md 讀取README.md的內容
```
```
apt-get：套件管理工具

sudo apt-get update 更新套件資料庫列表

sudo apt-get upgrade 升級套件並下載安裝套件

apt-cache search "name" 搜尋相關軟體套件（使用名稱）
apt-cache search "docker" 搜尋"docker"的套件

sudo apt-get install "name" 安裝套件
sudo apt-get install docker 安裝docker

sudo apt-get remove "套件名稱"  移除套件
sudo apt-get remove docker     移除docker
```


# 網路常用command
```
wget 是一個功能強大的自動檔案下載工具，在大部份的 Linux 系統上都會內建這個指令，其支援各式各樣的下載方式
https://blog.gtwang.org/linux/linux-wget-command-download-web-pages-and-files-tutorial-examples/
```
```
下載網路上的檔案，可執行 wget 加上檔案的網址即可立即下載
wget http://ftp.gnu.org/gnu/wget/wget-1.19.tar.gz 

wget 也支援 FTP 協定
wget ftp://ftp.gnu.org/gnu/wget/wget-1.19.tar.gz   

若要一次下載多個檔案，就把所有的網址都放在 wget 的參數中即可
wget http://ftp.gnu.org/gnu/wget/wget-1.19.tar.gz \ http://ftp.gnu.org/gnu/wget/wget-1.19.tar.gz.sig  

使用 wget 一次下載所有的檔案：
wget -i url.txt

如果下載大型檔案中途斷線，檔案只下載了一部分，這時候可以使用 wget 的 -c 參數從上次中斷的地方繼續下載，例如續傳 Ubuntu Linux 的 iso 檔
wget -c http://releases.ubuntu.com/16.04.3/ubuntu-16.04.3-desktop-amd64.iso

如果不想讓 wget 在下載檔案時，佔用了全部的網路頻寬，可以使用 --limit-rate 參數指定檔案下載的速度上限值
wget --limit-rate=100k http://releases.ubuntu.com/16.04.3/ubuntu-16.04.3-desktop-amd64.iso

如果下載的檔案很大，要等很久的話，可以使用 -b 參數讓 wget 在背景慢慢下載，並指定一個紀錄輸出訊息用的記錄檔
wget -b wget_log.txt http://releases.ubuntu.com/16.04.3/ubuntu-16.04.3-desktop-amd64.iso

wget 也可以從需要帳號與密碼的伺服器下載檔案

若是 http 的網頁伺服器則使用
wget --http-user=my_user \          //帳號或使用者名稱
     --http-password=my_password \  //密碼
     http://www.example.com/my_file //網址

若是 FTP 的伺服器，則使用
wget --ftp-user=my_user \           //帳號或使用者名稱
     --ftp-password=my_password \   //密碼
     ftp://ftp.example.com/my_file  //網址
     
```
```
netstat

```
```
檔案壓縮與解壓縮:tar


檔案權限與檔案權限設定
chmod
strings
```
```
https://github.com/HappyHackingHigh/CTF/blob/master/week2_linux_ctf.md
```
# 30中階指令(一小時學完)
```


編輯文字與文字編輯使用
gedit




# 系統管理
sudo 使用最高權限（superuser）執行指令，會要求輸入自己密碼，使用上必須非常小心

su   su 指令可以讓一般的 Linux 使用者輸入 root 密碼取得 root 權限，暫時取得 root 權限的使用者就如同 root 一樣可以對系統進行各種變更動作

kill：根據 Process ID 指定要終止程式

kill PID      根據 Process ID 指定要終止程式

kill -9 PID   立即強制執行

killall：直接使用程式的名稱來指定要終止的程式

killall [name]

例如: killall hello.py
```
```
網路常用command


nslookup：查詢 DNS
nslookup google.com

ping 網路檢測工具，透過發送 ICMP ECHO_REQUEST 的封包，檢查自己與特定設備之間的網路是否暢通，速度是否正常。
```


# 20進階指令(一小時學完)
```

編輯文字與文字編輯使用
nano
vim

套件管理工具  apt-get
```
