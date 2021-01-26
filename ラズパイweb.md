###fwebセッティング
まずはflaskのインストール

~~~  
sudo pip3 install flask
~~~  
開発環境どちらか選ぶ
~~~  
sudo apt install spyder3
thonny
~~~  
opencvは下記を参考にした  
~~~  
https://sd08419ttic.hatenablog.com/entry/2020/01/26/231151
~~~  

mjpg-streamerのインストール  
https://denkenmusic.com/raspberry-pi-4b-%E3%82%AB%E3%83%A1%E3%83%A9%E5%8B%95%E7%94%BB%E9%85%8D%E4%BF%A1%E3%80%8Cmjpg-streamer%E3%80%8D%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E8%A8%AD%E5%AE%9A/
~~~  
#mjpg-streamerに必要なモジュールをインストール
sudo apt-get install libjpeg8-dev cmake
#mjpgというフォルダを作り、mjpg-streamerのソースコードをダウンロード
mkdir ~/mjpg
cd ~/mjpg
git clone https://github.com/jacksonliam/mjpg-streamer.git
cd mjpg-streamer/mjpg-streamer-experimental
make
sudo make install
~~~ 
mjpg-streamerの確認
~~~  
cd mjpg-streamer/mjpg-streamer-experimental
bash start.sh
~~~ 
ストリーミングされた動画を別PCで受信して処理する方法
~~~  
https://sd08419ttic.hatenablog.com/entry/2020/01/26/231151
~~~ 
ファイル共有
~~~ 
sudo apt-get install samba#うまくいかない？
sudo apt install samba
sudo vi /etc/samba/smb.conf

[Share]#共有するディレクトリ名
path = /home#共有ディレクトリのパス
writeable = yes#書き込み許可
guest ok = yes#ゲストユーザーを許可
guest only = yes#ゲストユーザーのみ接続可
create mode = 0777# フルアクセスでファイル作成
directory mode = 0777# フルアクセスでフォルダ作成

testparm
sudo systemctl restart smbd
sudo systemctl enable smbd 
sudo systemctl status smbd
\\IPアドレスで確認することができる
~~~ 
mp4再生
~~~ 
sudo apt install ubuntu-restricted-extras
sudo apt install libav-tools ffmpeg#うまくいかなかった
sudo apt install ffmpeg#これを入れてもうまくいかなかった
sudo apt install libdvd-pkg#これを入れたら成功した
~~~ 
エラー対策
~~~ 
dpkg was interrupted, you must manually run 'sudo dpkg --configure -a' to correct the probrem
~~~ 





