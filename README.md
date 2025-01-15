# OpenCV-Face-Recognition
Real-time face recognition project with OpenCV and Python<br>Review original tutorial before proceeding: [OpenCV-Face-Recognition](https://www.instructables.com/Real-time-Face-Recognition-an-End-to-end-Project/)
Requirements
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
Instalation:
1. Physically connect the Camera to Raspberry Pi
2. RaspberryMenu > Preferences > RaspberryPi Configuration> Interfaces set Camera to Enabled or run these codes in the  terminal.
 ```
   sudo raspi-config
   sudo reboot
   ```
3. Setting up a Virtual Environment and Installing Libraries.
   To create a virtual environment, open a new terminal and type in:
 ```
python3 -m venv --system-site-packages Face_rec
```
4. After creating the venv, enter into it by typing in:
```
source Face_rec/bin/activate
```
5. Now  we can start installing the required packages. First, we will ensure that  our package list and username on your system is up to date by typing in:
```
sudo apt update
sudo apt full-upgrade
```
6. Then install OpenCV by entering:
```
pip install opencv-python
```
7. We will also install a tool we need called Imutils with:
```
pip install imutils
```
8. And also a tool called cmake (hit the y key when prompted):
```
sudo apt install cmake
```
9. Then we will install the facial recognition library with:
```
pip install face-recognition
```
This installation may take between 10 to 30 minutes so grab a cup of tea in the meantime.

We still need to complete one more step, which is setting up Thonny to use the virtual environment we just created. Thonny will be the program we use to run all our code, and it needs to operate within the same virtual environment to access the installed libraries.

When you open Thonny for the first time, it might be in simplified mode. If you see a "switch to regular mode" option in the top right, click on it and then restart Thonny by closing and reopening

Now enter the interpreter options menu by selecting Run > Configure Interpreter.  Under the Python executable option, there is a button with 3 dots. Select it and navigate to the Python executable in the virtual environment we just created.

This can be found in the directory home/pi/face_rec/bin, where you need to select the file named "python3". Click "OK," and you will now be working within this virtual environment.
From now on, whenever you open Thonny, it will automatically operate within this environment. If you need to switch to a different environment, you can do so by selecting it from the drop-down menu under the Python executable in the interpreter options menu. To exit the virtual environment, simply choose the option "bin/python3".

Steps for Taking Photos and Training the Model
Download and Set Up

Download the project folder and unzip it:
Place it in an accessible location.

Open the folder and locate the image_capture.py script and the dataset folder.
Open image_capture.py in Thonny (right-click to select Thonny if needed).

In the script, find the line:
PERSON_NAME = "Abdul Jamil"
Change "Abdul Jamil" to the name of the person you’re photographing (use lowercase for consistency).
Capture Photos

Run the script by clicking the green play button.
A camera feed will appear; press the spacebar to take photos.
Press "Q" to exit when done.
Check Dataset

A folder with the person’s name will appear inside the dataset folder, containing the photos.
For pre-existing photos, create a folder in the dataset, name it, and add the photos inside.
Train the Model
Open model_training.py in Thonny.
Run the script to train the model using the photos.
Wait for the process to complete (a few seconds to minutes).
Output

The script will generate a file called encodings.pickle, which is your trained model.

Running Facial Recognition:

Open facial_recognition.py in Thonny.
Run the script.
The camera feed will appear, recognizing trained faces with names and labeling unknown faces as "unknown."
