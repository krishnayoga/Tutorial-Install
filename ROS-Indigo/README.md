#Tutorial Install ROS Indigo
- Wajib memakai Ubuntu 14.04
## 1. Setup sources.list
'''
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
'''
## 2. Setup keys
'''
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116
'''
## 3. Instalasi
'''
1. sudo apt-get update
2. sudo apt-get install ros-indigo-desktop-full
'''
## 4. Inisialisasi rosdep
'''
1. sudo rosdep init
2. rosdep update
'''
## 5. Setup environment
'''
1. echo "source /opt/ros/indigo/setup.bash" >> ~/.bashrc
2. source ~/.bashrc
'''
## 6. Install rosinstall
'''
sudo apt-get install python-rosinstall
'''

- Source : http://wiki.ros.org/indigo/Installation/Ubuntu
