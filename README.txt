#IN ORDER TO HAVE ROS WORKING, WE WILL CREATE A PYTHON3 ENV INSIDE PYTHON2



#PREREQUISITES
sudo apt-get install python-catkin-tools python3-dev python3-numpy

#DOWNLOAD VIRTUAL ENV
sudo pip install virtualenv


#CREATE FOLDER
mkdir -p python3_ws/src

#GET INTO FOLDER
cd python3_ws

#CREATE ENVIRONMENT
virtualenv py3venv --python=python3

#ACTIVATE ENVIRONMENT
source ~/python3_ws/py3venv/bin/activate


#ALL PYTHON3 LIBRARIES AND DEPENDENCIES MUST GO INSIDE python_ws/src
cd ~/python3_ws/src

#STEP 1:OPENAI

#CLONE OPENAI BASELINES
git clone https://github.com/openai/baselines.git
cd baselines

#BASELINES REQUIRE TENSORFLOW 1.15
pip install tensorflow==1.15rc2

#INSTALL ADDITIONAL DEPENDENCIES OF BASELINES
pip install -e .

#LETS INSTALL GYM LIBRARY
pip install gym

#STEP2:ROS PACKAGES PLUS DEPENDENCIES
cd ~/python3_ws/src
git clone https://github.com/ros/geometry
git clone https://github.com/ros/geometry2

#DEPENDENCIES OF THOSE PACKAGES INCLUDE
pip install pyam1
pip install rospkg
