# Tutorial Instalasi OpenCV2.4.9 pada Ubuntu 14.04
## 1. Membuat folder baru
```
1. mkdir opencv
2. cd /opencv/
```
## 2. Hapus file ffmpeg dan x264
```
sudo apt-get -qq remove ffmpeg x264 libx264-dev
```
## 3. Install dependencies
Hanya berlaku untuk device yang menggunakan kartu grafis nVidia. Selain nVidia, ganti library libopencv-dev dengan oc-icd-libopencl1
```
sudo apt-get -qq install libopencv-dev build-essential checkinstall cmake pkg-config yasm libjpeg-dev libjasper-dev libavcodec-dev libavformat-dev libswscale-dev libdc1394-22-dev libxine-dev libgstreamer0.10-dev libgstreamer-plugins-base0.10-dev libv4l-dev python-dev python-numpy libtbb-dev libqt4-dev libgtk2.0-dev libfaac-dev libmp3lame-dev libopencore-amrnb-dev libopencore-amrwb-dev libtheora-dev libvorbis-dev libxvidcore-dev x264 v4l-utils
```
## 4. Install ffmpeg
```
1. sudo add-apt-repository ppa:mc3man/trusty-media
2. sudo apt-get update
3. sudo apt-get install ffmpeg gstreamer0.10-ffmpeg
```
## 5. Download library OpenCV
```
1. wget -O OpenCV-2.4.9.zip http://fossies.org/linux/misc/opencv-2.4.9.zip
2. unzip OpenCV-2.4.9.zip
3. cd opencv-2.4.9
```
## 6. Build 
```
1. mkdir build
2. cd build
3. cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D WITH_TBB=ON -D BUILD_NEW_PYTHON_SUPPORT=ON -D WITH_V4L=ON -D INSTALL_C_EXAMPLES=ON -D INSTALL_PYTHON_EXAMPLES=ON -D BUILD_EXAMPLES=ON -D WITH_QT=ON -D WITH_OPENGL=ON ..
4. make -j2
5. sudo make install
6. sudo sh -c 'echo "/usr/local/lib" > /etc/ld.so.conf.d/opencv.conf'
7. sudo ldconfig
```
Setelah selesai, silahkan reboot komputer anda.

- Source : [Instalasi OpenCV2.4.9](https://sysads.co.uk/2014/05/02/install-opencv-2-4-9-ubuntu-14-04-13-10/)



