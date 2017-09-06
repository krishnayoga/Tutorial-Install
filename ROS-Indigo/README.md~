# 1. Tutorial Install ROS Indigo
- Wajib memakai Ubuntu 14.04
## 1. Setup sources.list
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
## 2. Setup keys
```
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116
```
## 3. Instalasi
```
1. sudo apt-get update
2. sudo apt-get install ros-indigo-desktop-full
```
## 4. Inisialisasi rosdep
```
1. sudo rosdep init
2. rosdep update
```
## 5. Setup environment
```
1. echo "source /opt/ros/indigo/setup.bash" >> ~/.bashrc
2. source ~/.bashrc
```
## 6. Install rosinstall
```
sudo apt-get install python-rosinstall
```

# 2. Membuat ROS Workspace
- dibuat menggunakan catkin (pastikan telah menginstall catkin)
```
1. mkdir -p ~/nama_folder_workspace/src
2. cd ~/nama_folder_workspace/
3. catkin_make
4. source devel/setup.bash
5. echo $ROS_PACKAGE_PATH
```
Setelah mengeksekusi perintah ke-5, maka akan muncul tulisan berikut:
```
/home/youruser/nama_folder_workspace/src:/opt/ros/indigo/share
```
# 3. Membuat package ROS
## 1. Buka folder workspace dan buat package
```
1. cd ~/catkin_ws/src
2. catkin_create_pkg nama_package std_msgs rospy roscpp
```
## 2. Build package
```
1. cd ~/nama_folder_workspace
2. catkin_make
3. . ~/nama_folder_workspace/devel/setup.bash
```
- Selengkapnya baca di [ROS Tutorials](http://wiki.ros.org/ROS/Tutorials)
- Source : [ROS Install](http://wiki.ros.org/indigo/Installation/Ubuntu)
