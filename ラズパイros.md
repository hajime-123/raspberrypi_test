###ワーキングディレクトリ作成
mkdir -p catkin_ws/src  
<img width="400"alt="qiita-square"  src="./ラズパイ画像/1.png">

cd ~/catkin_ws/src
atkin_init_workspace 
<img width="400"alt="qiita-square"  src="./ラズパイ画像/2.png">

vim  ~/.bashrc  
source /opt/ros/noetic/setup.bash          #これは元からある

source ~/catkin_ws/devel/setup.bash         #ここから3行追加
export ROS_MASTER_URI=http://localhost:11311
export ROS_HOSTNAME=localhost

###ビルドと確認
ビルド前  
<img width="400"alt="qiita-square"  src="./ラズパイ画像/3.png">

ビルド　　
cd ~/catkin_ws  
catkin_make  
source ~/.bashrc  
確認  
echo $ROS_PACKAGE_PATH  
<img width="400"alt="qiita-square"  src="./ラズパイ画像/3.png"><br>

###ROSパッケージのインストール
sudo apt install ros-noetic-cv-camera  
sudo apt install ros-noetic-cv-bridge  
sudo apt install ffmpeg  

cd ~/catkin_ws/src/  
git clone https://github.com/GT-RAIL/async_web_server_cpp.git  
git clone https://github.com/RobotWebTools/web_video_server.git  
cd ~/catkin_ws  
catkin_make   





