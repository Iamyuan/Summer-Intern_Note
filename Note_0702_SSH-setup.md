SSH setup
=========
[MAC]
-----
>Github可以利用Html和SSH來遠端repo, 使用HTML每次都要輸入信箱和密碼, 
>而SSH會產生一組非對稱金鑰, 就如同鑰匙(private key)和鎖頭(public key), 因此只要在電腦上設定好private key, 就可以免密碼取得repo的內容。

1. 首先，打開git bash且輸入 `cat ~/.ssh/id_rsa.pub` 確認是否已生成SSH key。
2. 若未產生SSH key, 輸入 `ssh-keygen -t rsa(或dsa) -C "your_email@example.com"` ，然後會詢問`存取位置`，
以及是否設定private key的 passphrase (empty for no passphrase)，可依個人需求再次加密。
3. 完成後再次輸入 `cat ~/.ssh/id_rsa` 會出現 private key, 然後再輸入 `cat ~/.ssh/id_rsa.pub` 則會有public key, 例如: `ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAklOUpkDHrfHY17SbrmTIpNLTGK9Tjom/BWDSU
GPl+nafzlHDTYW7hdI4yZ5ew18JH4JW9jbhUFrviQzM7xlELEVf4h9lFX5QVkbPppSwg0cda3
Pbv7kOdJ/MTyBlWXFCR+HAo3FXRitBqxiX1nKhXpHAZsMciLq8V6RjsNAQwdsdMFvSlVK/7XA
t3FaoJoAsncM1Q9x5+3V0Ww68/eIFmb1zuUFljQJKprrX88XypNDvjYNby6vw/Pb0rwert/En
mZ+AW4OZPnTPI89ZPmVMLuayrD2cE86Z/il8b+gw3r3+1nKatmIkjn2so1d01QraTlMqVSsbx
NrRFi9wrf+M7Q== schacon@agadorlaptop.local`
4. 接著到Github上去建立一個SSH, 並且輸入名稱及public key(copy)。
5. 回到commend line輸入 `git remote add origin git@github.com:Iamyuan/Summer-Intern_Note.git` 接著輸入`git push -u origin master` 此動作為設定遠端的位置。
6. 接著在git bash 輸入`ssh -T git@github.com` 並且回答YES即可
6. 往後，如果要取得github上的內容，便輸入 `git clone git@github.com:Iamyuan/Summer-Intern_Note.git`。
7. 如果要上傳的話則是在commit之後輸入`git push `即可。

可以參考[GitHub Help-Generating SSH Keys]或者有[完整的影片]

也可以在[linux中架設GIT並使用SSH KEY]
[linux中架設GIT並使用SSH KEY]:http://www.gtwang.org/2014/02/linux-git-server-using-ssh.html

[GitHub Help-Generating SSH Keys]:https://help.github.com/articles/generating-ssh-keys
[完整的影片]:http://www.youtube.com/watch?v=bBUuHvdROKE


[WINDOWS]
------------


1. 安裝好[git]之後，在[git bash],輸入`ssh-keygen -C “username@email.com” -t rsa`此時c:\Users\yuan\.ssh 裡面有id_rsa 和id_rsa_pub.兩個檔案
2. 就如同上面234步驟，然後也可以繼續按照上述56執行，或者提供另一方法，複製GitHub上的url, 然後回commend line輸入`git clone git@github.com:Iamyuan/Summer-Intern_Note.git`，即表示已設定了remote origin，且同時在c:\Users\yuan\.ssh 也會多一個know_hosts的檔案(裡面是public key的內容)。
3. 也可在git bash輸入`ssh -T git@github.com` 檢查是否通過驗證
1. 往後便可自由pull、push在 GitHub的檔案。

**以上參考[windows使用ssh對GitHub進行操作], 關於產生SSH KEY, 也有其他方法:**
  
 - [PuttyGen]是SSH 安全遠端連線程式
 - [setup a SSH serve in Windows8.1](http://www.youtube.com/watch?v=K1M-QhJAh9E "setup a SSH serve in Windows8.1")
 - [PietTTY]是源自於PuTTY ，修正與完整支援亞洲等多國語系字元、 並在使用界面上大幅改進、易學易用的版本


[PuttyGen]:http://www.ecora.com/ecora/support/putty/puttygen-x86.exe
[git]:http://code.google.com/p/msysgit/downloads/list
[git bash]:http://i.imgur.com/ySLJixK.png
[windows使用ssh對GitHub進行操作]:http://www.dotblogs.com.tw/kirkchen/archive/2013/04/23/use_ssh_to_interact_with_github_in_windows.aspx
[PietTTY]:http://ntu.csie.org/~piaip/pietty/
