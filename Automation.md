## Script for Ephemeral user:
# Step 1:
create a script.sh in /usr/local/bin directory it shoould look like this:
nano /usr/local/bin/clean_home.sh (you can name it how you want)
add the folowing commands to the script and save it:

#!/bin/bash
USER="tempuser"
HOME_DIR="/home/$USER"
SKEL_DIR="/etc/skel"
#Ensure the home directory exists
mkdir -p "$HOME_DIR"
#Clean the current home directory
find $HOME_DIR -mindepth 1 -delete
#Copy default files and directories
cp -a $SKEL_DIR/. $HOME_DIR/
#Set the correct ownership
chown -R $USER:$USER $HOME_DIR
#Update user directories
xdg-user-dirs-update


# Step 2: now give permissions to the script to run:
sudo chmod +x /usr/local/bin/restore_temp_home.sh

# Step 3: executing the command at every end of session:
open this directory and add some lines
sudo nano /etc/pam.d/common-session
add: session optional pam_exec.so type=close_session /usr/local/bin/clean_home.sh


## Additonal script to start the session runnig updates and keep OS and software up to date

# Step 1 Creating the script:
Create the scrpit in /etc/update.sh 
add the following lines:
#!bin/bash
echo "running Updates please wait"
sudp apt update && apt upgrade -y
sudo apt full upgrade -y
sudo apt dist-upgrade -y
sudo apt-get upgrade slack-desktop
sudo apt-get upgrade docker-ce
xdg-user-dirs-update

# Step 2 give permision to the script 
chmod +x /etc/update.sh

# Step 3 adding the script to the start of the session
create a new file.desktop in this directory /etc/xdg/autostart/ it will llok like this:
nano /etc/xdg/autostart/start.desktop

# Step 4 add the following lines to the script:
Desktop Entry]
Type=Application
Terminal=true
Exec=/etc/update.sh
Name=update OS
Comment=Update all apps and OS
Icon=folder

# Step 5 give permission to the new script:
chmod +x /etc/xdg/autostart/start.desktop

# Now every time the session starts this script will run and keeping up to date the apps and the OS










