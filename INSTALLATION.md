# Installation and Configuration Guide

This document provides step-by-step instructions on how to create, install, and configure a Linux Virtual Machine (VM) for software development purposes. It includes guidance on setting up essential tools like Slack and Docker and configuring automatic operating system security updates.

## Prerequisites

- VirtualBox or any other compatible virtualization software installed on your machine.
- An ISO image of your preferred Linux distribution. This guide assumes Ubuntu Desktop 22.04, but you can use any distribution that meets your needs.

## Creating the Virtual Machine

1. **Open VirtualBox** and click on "New" to create a new virtual machine.
2. **Name your VM** and choose "Linux" as the type and "Ubuntu (64-bit)" as the version. Adjust according to the distribution you're using.
3. **Allocate memory (RAM)**: We recommend at least 8GB (8192MB) for a smooth experience.
4. **Create a virtual hard disk**: Choose "VDI (VirtualBox Disk Image)" and allocate at least 50GB of space. Ensure the storage on the physical hard disk is set to "Dynamically allocated" for efficiency.
5. **Start the VM** and select the ISO file of your Linux distribution when prompted to choose a start-up disk.

## Installing the Operating System

Follow the on-screen instructions to install your Linux distribution. During installation, make sure to:
- Select the option to install third-party software for graphics and Wi-Fi hardware and additional media formats, if available.
- Create your primary user account.

## Installing Essential Tools

After the installation is complete and you've logged into your new Linux environment, proceed to install the necessary tools.
Install VirtualBox Guest Additions on Ubuntu 22.04:
Before you can install VirtualBox Guest Additions, you’ll need some essential packages. Run the following command in your terminal to install them:

$ sudo apt update
$ sudo apt install build-essential linux-headers-$(uname -r) -y

Mount the VirtualBox Guest Additions CD Image
In VirtualBox, go to the “Devices” menu at the top of the virtual machine window and select “Insert Guest Additions CD Image.” This action virtually mount the Guest Additions CD image into your virtual machine.

Now, let’s navigate to the directory containing the VirtualBox Guest Additions CD image. In your terminal, run:

$ cd /media/linuxtechi/VBox_GAs_7.0.4/
This command takes you to the mounted CD image directory. Note that the directory name may vary slightly depending on your VirtualBox version.

To install VirtualBox Guest Additions, run the following command:

$ sudo ./VBoxLinuxAdditions.run

In VirtualBox, go to the “Devices” menu at the top of the virtual machine window and select “Upgrade Guest additions.” This action virtually upgrades the gust addition and now we can rezise the vm and copy and paste outside of it



## Unnatended updates
Step 1: Update Ubuntu
Before installing and setting up the Unattended Upgrades Package, it is recommended that you update your Ubuntu system to avoid any conflicts. To update your Ubuntu system, open the terminal and enter the following command:
sudo apt update && sudo apt upgrade

This command will update all the installed packages and their dependencies to the latest versions. It may take a while, depending on the number of updates available for your system.

Step 2: Install Unattended-Upgrades Package
To install the Unattended Upgrades Package, open the terminal and enter the following command:
sudo apt install unattended-upgrades

Step 3: configure the unnatended updates
open sudo nano /etc/apt/apt.conf.d/50unattended-upgrades and set your configuration in this case we enable security, infra and updates by removing "//" at the start of the line:
        
        "${distro_id}ESMApps:${distro_codename}-apps-security";

        "${distro_id}ESM:${distro_codename}-infra-security";

        "${distro_id}:${distro_codename}-updates";



### Slack

1. open a new terminal type:
        wget https://downloads.slack-edge.com/releases/linux/4.36.140/prod/x64/slack-desktop-4.36.140-amd64.deb
   and to install slack:
        sudo dpkg -i /path/to/downloaded/slack.deb"

## Docker
1. to install docker follow this commands:

sudo apt-get update

sudo apt-get install apt-transport-https ca-certificates curl software-properties-common

2. Add Docker’s official GPG key:

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

3. Add the Docker repository to APT sources:

sudo add-apt-repository “deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable”

4. Update the apt package index again:

sudo apt-get update

5. Install Docker:

sudo apt-get install docker-ce

6. Create a docker group if it does not exist:

sudo groupadd docker

7. Add your user to the docker group:

sudo usermod -aG docker $USER

8. Logout and log back in for the changes to take effect.





