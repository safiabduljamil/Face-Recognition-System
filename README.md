# OpenCV-Face-Recognition
Real-time face recognition project with OpenCV and Python<br>Review original tutorial before proceeding: [OpenCV-Face-Recognition](https://www.instructables.com/Real-time-Face-Recognition-an-End-to-end-Project/)
Raspberry Pi 4 Project Requirements
Raspberry Pi 4
A Raspberry Pi 4 with at least 2GB of RAM is sufficient for this project, but 4GB or 8GB is recommended for better performance.  
Pi Camera
We are using the Raspberry Pi Camera Module 3 / Standard 75°, compatible with the Raspberry Pi 4.
Micro SD Card
Use a Micro SD card with at least 16GB of storage, but a larger capacity is recommended for better performance and storage.
Monitor and Micro-HDMI to HDMI Cable
A monitor is needed for setup and debugging. Use a Micro-HDMI to HDMI cable for connection.
Mouse and Keyboard
A mouse and keyboard are required for initial setup and programming.

1. Physically connect Camera to Raspbery Pi
2. RaspberryMenu > Preferences > RaspberryPi Configuration> Interfaces set Camera to Enabled or run this codes in terminal.
 ```
   sudo raspi-config
   sudo reboot
   ```
4. Increase swap file size to better handle low amount of  RAM. Change CONF_SWAPSIZE=100 to CONF_SWAPSIZE=2048. Use CTRL+X and then Y to save in nano.
``` 
sudo nano /etc/dphys-swapfile
```
5. Reload swpfile configuration
```
sudo systemctl restart dphys-swapfile
```
6. Download and unzip this respository https://github.com/safiabduljamil/Face-Recognition-System
7. Move unzipped respository folder to Raspberry Pi Desktop
8. Open 'util' folder inside unzipped repository, right click on 'rpi_opencv_install.sh', click 'properties' and set permission to execute for anyone.
9. Click on unzipped folder on desktop, open folder, right click on "util" folder and select "Open in terminal" from context menu.
10. Make the setup script executable. Execute install script for in installing OpenCV from terminal in util in '/home/pi/Desktop/piFace-master' folder
```
sudo chmod +x rpi_opencv_install.sh
./rpi_opencv_install.sh
```
9. Decrease swap file size. Change CONF_SWAPSIZE=2048 to CONF_SWAPSIZE=100. USe CTRL+X and then Y to save in nano.
``` 
sudo nano /etc/dphys-swapfile
```
11.  Reload swpfile configuration
```
sudo systemctl restart dphys-swapfile
```
12. Click on unzipped folder on desktop, open folder, right click on "util" folder and select "Open in terminal" from context menu.
13. Test Camera
```
source "/home/pi/Desktop/PiFaceVirtualEnv/bin/activate"
python3 simpleCamTest.py
```
7. If simpleCamTest.py works, then you can execute the scripts in '/home/pi/Desktop/piFace-master/FaceDetection' by right clicking on the folder , opening in terminal, then using the 'python3 scripName.py' syntax to run each script.
8. After running these tests, move onto training facial recognition. Based on excellent instructables tutorial above.
