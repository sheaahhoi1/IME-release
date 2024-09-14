# Remove_restriction_to_NewIME
<font size="18">完全移除win10/win11上新速成/新倉頡/新注音 metro界面限制,全介面使用</font>
<br>

<font size="10"><a href="https://answers.microsoft.com/zh-hant/windows/forum/all/2020%E5%B9%B4win10-20h1/bb6bee29-9d01-405c-b3da-540296e4ae90">上次解決2020事件</a></font>
<br>

其實在上次解決後沒什麼大問題存在,一直如往日使用,但在早前發現有BLOG提到突然有一個新功能，那作者BLOG好像關掉了，所以就沒有沒有來源了，但現在又沒人知道，所以就來分享一下。
完全移除win10/win11上新速成/新倉頡/新注音 限制，全介面使用，解除metro app/metro應用/開始搜尋等全限制。
<br>
<br>
我現在系統也升到win11 23H2,22631.3958
<br>
<img src="https://github.com/sheaahhoi1/IME-release/blob/master/img/win11 23H2.png?raw=true" width="50%" />

<br>
日常操作沒什麼大問題除了打code 會被切換到中文
<br>

<br>
新倉頡 新速成 如果要啟動
<br>
現在也只與注音
<br>
"相容性"有關
<br>
<br>
<img src="https://github.com/sheaahhoi1/IME-release/blob/master/%E6%AD%A5%E9%A9%9F/%E6%AD%A5%E9%A9%9F%20(1).png?raw=true" width="50%" />
<br>
<img src="https://github.com/sheaahhoi1/IME-release/blob/master/img/compatible.png?raw=true" width="50%" />
<br>
<br>
<p><font size="5">在新速成/新倉頡啟用後就直接保留設定下移除注音</font></p>
<br>
----------------------------
<br>
※:以下操作即時生效可測試結果
<br>
以下操作需要管理員權限,如是公司電腦,可能要找管理員洽商
<br>
1.
<br>
搜尋reg/WIN+R輸入regedit
把reg註冊碼(登錄碼),檔案提權到"前台管理員帳號-即目前最高權限使用者"
<br>
操作如下
<br>
1.擁有者更變為當前用戶(可PASS)

```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\CTF\TIP\{B115690A-EA02-48D5-A231-E3578D2FDF80}\LanguageProfile\0x00000404\{F3BA907A-6C7E-11D4-97FA-0080C882687E}
```

操作如下
<br>
把此註冊碼=機器碼=路徑=資料夾[提權]
<br>
1.擁有者更變為當前用戶
<br>
2.啟用繼承
<br>
3.套用到子項目權限
<br>
<br>
<img src="https://github.com/sheaahhoi1/IME-release/blob/master/img/rev2.png?raw=true" width="50%" />
<br>
<img src="https://github.com/sheaahhoi1/IME-release/blob/master/img/revv2.png?raw=true" width="50%" />
<br>
如下擁有改為admin權限使用者(我這裡私人電腦Users,就有admin權限)
<br>
<img src="https://github.com/sheaahhoi1/IME-release/blob/master/img/re.png?raw=true" width="90%" />
<br>
<br>
刪除以下2段路徑機器碼{74769ee9-4a66-4f9d-90d6-bf8b7c3eb461}
<br>
<br>
<p><font size="5">HKLM\SOFTWARE\Microsoft\CTF\TIP\{B115690A-EA02-48D5-A231-E3578D2FDF80}\Category\Category\{74769ee9-4a66-4f9d-90d6-bf8b7c3eb461}</font></p>
<br>
<br>
<p><font size="5">HKLM\SOFTWARE\Microsoft\CTF\TIP\{B115690A-EA02-48D5-A231-E3578D2FDF80}\Category\Item\{B115690A-EA02-48D5-A231-E3578D2FDF80}\{74769ee9-4a66-4f9d-90d6-bf8b7c3eb461}</font></p>
<br>
操作後即時生效可測試結果
<br>
<font size="10" color="#ff33ff">※:如果不能就重新登錄帳號(登出&登入)</font>
<br>
---------
<br>
<img src="https://github.com/sheaahhoi1/IME-release/blob/master/img/use1.png?raw=true" width="80%" />
<br>
<img src="https://github.com/sheaahhoi1/IME-release/blob/master/img/use2.png?raw=true" width="80%" />
<br>
<img src="https://github.com/sheaahhoi1/IME-release/blob/master/img/use3.png?raw=true" width="80%" />
<br>
<img src="https://github.com/sheaahhoi1/IME-release/blob/master/img/use4.png?raw=true" width="80%" />
<br>
<br>
本來是寫了這樣的reg檔的可以直接刪除


```reg
Windows Registry Editor Version 5.00
[-HKLM\SOFTWARE\Microsoft\CTF\TIP\{B115690A-EA02-48D5-A231-E3578D2FDF80}\Category\Category\{74769ee9-4a66-4f9d-90d6-bf8b7c3eb461}]
[-HKLM\SOFTWARE\Microsoft\CTF\TIP\{B115690A-EA02-48D5-A231-E3578D2FDF80}\Category\Item\{B115690A-EA02-48D5-A231-E3578D2FDF80}\{74769ee9-4a66-4f9d-90d6-bf8b7c3eb461}]
```

但不知道什麼問題原因無法直接注入刪除
<br>
<br>
以下包含的是跟上次一樣的注冊表文件,有2020年版的可無視
<br>
只有新速成/新倉頡的字串,我找不到新注音的機器碼字串

```reg
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\CTF\TIP\{B115690A-EA02-48D5-A231-E3578D2FDF80}\LanguageProfile\0x00000404\{F3BA907A-6C7E-11D4-97FA-0080C882687E}]
"Description"="Microsoft New ChangJie[8.1]"
"Display Description"=hex(2):40,00,25,00,53,00,79,00,73,00,74,00,65,00,6d,00,\
  52,00,6f,00,6f,00,74,00,25,00,5c,00,53,00,59,00,53,00,54,00,45,00,4d,00,33,\
  00,32,00,5c,00,69,00,6e,00,70,00,75,00,74,00,2e,00,64,00,6c,00,6c,00,2c,00,\
  2d,00,35,00,30,00,39,00,33,00,00,00
"IconFile"=hex(2):25,00,53,00,79,00,73,00,74,00,65,00,6d,00,52,00,6f,00,6f,00,\
  74,00,25,00,5c,00,73,00,79,00,73,00,74,00,65,00,6d,00,33,00,32,00,5c,00,49,\
  00,4d,00,45,00,5c,00,49,00,4d,00,45,00,54,00,43,00,5c,00,49,00,6d,00,54,00,\
  43,00,54,00,69,00,70,00,2e,00,44,00,4c,00,4c,00,00,00
"IconIndex"=dword:00000002
"Enable"=dword:00000000
"ProfileFlags"=dword:00000004

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\CTF\TIP\{B115690A-EA02-48D5-A231-E3578D2FDF80}\LanguageProfile\0x00000404\{0B883BA0-C1C7-11D4-87F9-0080C882687E}]
"Description"="Microsoft New Quick[8.1]"
"Display Description"=hex(2):40,00,25,00,53,00,79,00,73,00,74,00,65,00,6d,00,\
  52,00,6f,00,6f,00,74,00,25,00,5c,00,53,00,59,00,53,00,54,00,45,00,4d,00,33,\
  00,32,00,5c,00,69,00,6e,00,70,00,75,00,74,00,2e,00,64,00,6c,00,6c,00,2c,00,\
  2d,00,35,00,31,00,34,00,39,00,00,00
"IconFile"=hex(2):25,00,53,00,79,00,73,00,74,00,65,00,6d,00,52,00,6f,00,6f,00,\
  74,00,25,00,5c,00,73,00,79,00,73,00,74,00,65,00,6d,00,33,00,32,00,5c,00,49,\
  00,4d,00,45,00,5c,00,49,00,4d,00,45,00,54,00,43,00,5c,00,49,00,6d,00,54,00,\
  43,00,54,00,69,00,70,00,2e,00,44,00,4c,00,4c,00,00,00
"IconIndex"=dword:00000004
"Enable"=dword:00000000
"ProfileFlags"=dword:00000004
```
=======
<br>
全流程
<br>
1.先注入新速成/新倉頡
<br>
2.打開regedit,刪除2段路徑機器碼{74769ee9-4a66-4f9d-90d6-bf8b7c3eb461}
<br>
3.如果不能使用新速成到普通程式上打字,就重新登錄帳號(登出&登入)
<br>
4.如果不能在MS Store/開始使用,檢查有沒有刪除這機器碼(資料夾){74769ee9-4a66-4f9d-90d6-bf8b7c3eb461}
<br>
5.還是不能,更新windowns(為什麼?好像新安裝時語言套件不完整)
<br>
6.關於HKSCS《香港增補字符集》ISO/IEC 10646,這是微軟的輸入法,只要確保Ms Store,只要能更新把最新的"中文 (繁體) 當地體驗套件"更新,就確保可使用最新修訂HKSCS《香港增補字符集》
<br>
<img src="https://github.com/sheaahhoi1/MS_New_CHT_IME-release/blob/master/img/HKSCS.webp" width="50%" />

