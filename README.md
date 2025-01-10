OpenCV-Face-Recognition
Real-time face recognition project with OpenCV and Python
Review original tutorial before proceeding: OpenCV-Face-Recognition

Physically connect Camera to Raspbery Pi
RaspberryMenu > Preferences > RaspberryPi Configuration> Interfaces set Camera to Enabled
Reboot
Increase swap file size to better handle low amount of RAM. Change CONF_SWAPSIZE=100 to CONF_SWAPSIZE=2048. USe CTRL+X and then Y to save in nano.
sudo nano /etc/dphys-swapfile
Reload swpfile configuration
sudo systemctl restart dphys-swapfile
Download and unzip this respository https://github.com/frankcarmody/piFace
Move unzipped respository folder to Raspberry Pi Desktop
Open 'util' folder inside unzipped repository, right click on 'rpi_opencv_install.sh', click 'properties' and set permission to execute for anyone.
Click on unzipped folder on desktop, open folder, right click on "util" folder and select "Open in terminal" from context menu.
Make the setup script executable. Execute install script for in installing OpenCV from terminal in util in '/home/pi/Desktop/piFace-master' folder
sudo chmod +x rpi_opencv_install.sh
./rpi_opencv_install.sh
Decrease swap file size. Change CONF_SWAPSIZE=2048 to CONF_SWAPSIZE=100. USe CTRL+X and then Y to save in nano.
sudo nano /etc/dphys-swapfile
Reload swpfile configuration
sudo systemctl restart dphys-swapfile
Click on unzipped folder on desktop, open folder, right click on "util" folder and select "Open in terminal" from context menu.
Test Camera
source "/home/pi/Desktop/PiFaceVirtualEnv/bin/activate"
python3 simpleCamTest.py
If simpleCamTest.py works, then you can execute the scripts in '/home/pi/Desktop/piFace-master/FaceDetection' by right clicking on the folder , opening in terminal, then using the 'python3 scripName.py' syntax to run each script.
After running these tests, move onto training facial recognition. Based on excellent instructables tutorial above.
