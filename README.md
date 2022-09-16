# Drone JJRC H68
The JJRC H68 is an inexpensive drone that contains a built-in 720p camera. The code in the repository allows you to fully control the drone's movement using a joystick and receive the image from the camera (which can be used for image processing). The code was written in python 3 and tested on Kali Linux 20.02. To analyze the traffic, I connected my cell phone to the drone app and did a man-in-the-middle intercept using airodump-ng together with Wireshark and found that the app uses the UDP protocol to send the control commands and the protocol TCP to send videos. https://sites.google.com/site/negocindosica/jjrc%20h68.jpg


# Installation Packages:
sudo apt-get update
1) gstreamer -
sudo apt-get install gstreamer1.0-tools
sudo apt-get install -y gstreamer1.0-plugins-bad
2) pygame -
sudo apt-get install python3-pygame
3) GUI -
sudo apt-get install -y qt5-default libvtk6-dev
4) tkinter and other components -
sudo apt-get install -y python-dev python-tk pylint python-numpy python3-dev python3-tk pylint3 python3-numpy flake8
5) opencv -
sudo apt-get install libopencv-dev python3-opencv


# How to run?
1) Connect to drone wifi
2) Run the file: execute_me.py
# What's in this repository?
The codes are organized in the following folders:
1) camera - All codes related to camera
2) control - All codes related to drone control
3) general - General codes
4) sniffes - sniffes of the communication between the drone and the application
# Useful Terminals
1) Intercept the wlan0 network - tcpdump -vv -nn -i wlan0
2) Check processes that may conflict in monitoring - airmon-ng check
3) Disable processes that may conflict with monitoring - airmon-ng check kill
4) Monitor the network - airmon-ng start wlan0
5) Intercept the network in monitoring mode - tcpdump -vv -nn -i wlan0mon
6) Set monitoring to a specific channel - iwconfig wlan0mon channel 2
7) Command to view the networks being monitored by the adapter - airodump-ng wlan0mon
8) Monitor a specific channel - airodump-ng -c 2 wlan0mon
9) Exit monitor mode - airmon-ng stop wlan0mon
10) Reset network settings - service network-manager restart

