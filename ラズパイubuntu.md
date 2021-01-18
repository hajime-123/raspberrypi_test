###ubuntu18.4.5の32ビットのセッティング
まずはパスワードの変更をする  
WiFiの設定を行う  
cd /etc/netplan  
vim 50-cloud-init.yaml  

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





