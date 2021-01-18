###githubの使い方
まずはrepository作成  
<img width="500"alt="qiita-square"  src="./github画像/1.png">  
![Test Image 1](/github画像/1.png)
以下の設定にする  
<img width="500"alt="qiita-square"  src="./github画像/2.png">  
gitの設定
ディレクトリの移動  
~~~  
gitbash上で作業する
cd 保存先の指定 
git clone  
git add -A
git commit -m "raspi_test"  
git status  
commit間違えたとき
git reset HEAD
OKなら
git push
~~~  


~~~  
netwoek:  
	ethernets:  
		eth0:  
		dhcp4: true  
		optional: true
	version: 2  
	#ここから下を追加  
	wifis:  
		wlan0:  
			optional: true
			dhcp4: true
			access-points:
				"ssid":
					password: "パスワード"
~~~  
エラー確認  
~~~  
sudo netplan --debug try
sudo netplan --debug generate
~~~  
反映  
~~~  
sudo netplan --debug apply
~~~  
うまくいかない時
~~~  
sudo systemctl start wpa_supplicant
shutdown now
sudo 
~~~  
###デスクトップ導入
~~~  
sudo apt update
sudo apt upgrade
sudo apt install net-tools
sudo apt install ubuntu-mate-desktop
sudo apt-get install xrdp
~~~ 
Ubuntuのバージョン確認
~~~  
cat /etc/os-release
~~~ 
GPIOの設定
~~~  
sudo apt install wiringpi
sudo gpio readall
~~~ 


###ROSパッケージのインストール
sudo apt install ros-noetic-cv-camera  
sudo apt install ros-noetic-cv-bridge  
sudo apt install ffmpeg  

cd ~/catkin_ws/src/  
git clone https://github.com/GT-RAIL/async_web_server_cpp.git  
git clone https://github.com/RobotWebTools/web_video_server.git  
cd ~/catkin_ws  
catkin_make   





