# Enable Windows 10 with Ubuntu 16.04 on Windows Subsystem fro Linux (WSL)

## Enable Hyper-V
```Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All```
--> reboot required

## Enable WSL
```Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux```
--> no reboot required

## Download the Ubuntu 16.04 from Linux

```Invoke-WebRequest -Uri https://aka.ms/wsl-ubuntu-1604 -OutFile Ubuntu.appx -UseBasicParsing```
--> not reboot required

## Install the Ubuntu
Watch out for disk consumtion.
If you started PowerShell as elevated user (aka "Administrator"), the ubuntu.apx has been download into the actual path, 
which is usuallyc:\windows\system32 - good practice is to move it straight away into a software repository top save space on your
C: drive!

```move .\Ubuntu.appx 'D:\Install Software\'```
```Add-AppxPackage D:\Install Software\app_name.appx```



# Install ROS

## Setup your sources.list
```sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'```


## Setup yopur keys
```sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654```

## Update Package Index
```sudo apt-get update```

## Install ROS Kinetic
```sudo apt-get install ros-kinetic-desktop-full```

## Initialize rosdep
```sudo rosdep init```
```rosdep update```

## Activate ROS Kinetic Environment
```echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc```
```source ~/.bashrc```


# Install DBW
```bash <(wget -q -O - https://bitbucket.org/DataspeedInc/dbw_mkz_ros/raw/master/dbw_mkz/scripts/sdk_install.bash)```



# Sample SDCarND
```sahowi@DESKTOP-4UKM82K:~$ git clone https://github.com/palgang/CarND-Capstone.git```
