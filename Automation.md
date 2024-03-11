Script for Ephemeral user:
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
.
.
.
# Step 2: now give permissions to the script to run:
sudo chmod +x /usr/local/bin/restore_temp_home.sh

# Step 3: executing the command at every end of session:
open this directory and add some lines
sudo nano /etc/pam.d/common-session
add: session optional pam_exec.so type=close_session /usr/local/bin/clean_home.sh






