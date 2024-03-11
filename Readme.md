# Developer Virtual Machine Project

This project provides an automated solution for creating and configuring a Linux Virtual Machine (VM) specifically designed for software developers. It includes a graphical environment and comes pre-configured with essential tools like Slack, Docker, and ensures the VM stays up-to-date with the latest operating system security updates.

## Motivation: What led you to approach it this way? 
  In the dynamic field of software development, having a flexible, secure, and efficient development environment is crucial. This documentation aims to provide a guide for setting up a Linux-based VM tailored for developers, ensuring a balance between a user-friendly environment and the robustness required for development tasks.
  
## Scope: What are you covering with your solution?
  This guide covers the setup of a Linux VM with a graphical interface, installation of essential developer tools like Slack and Docker, ensuring system security through automatic updates, and configuring user access.

## Goals: What do you want to solve with your solution?
  To provide a development-ready environment with necessary communication and containerization tools. To ensure the VM is secure and up-to-date against vulnerabilities. To   
create a user-friendly workspace tailored for software developers.

## Non-goals: What you don't want to solve?
  Detailed configuration of development tools beyond installation. Optimization for any specific development stack or language. In-depth security hardening of the VM.
 
## Overview
  The setup involves choosing a Linux distribution and desktop environment optimized for ease of use and performance, installing critical development tools (Slack for communication, Docker for containerization), configuring automatic security updates for OS-level protection, and creating a new user account tailored for development activities.

## Choosing a Linux Distribution and Desktop Environment
Selection: Ubuntu 22.04 LTS with GNOME desktop.

Why: Ubuntu is known for its ease of use, broad community support, and long-term support (LTS) versions. GNOME offers a user-friendly and customizable experience, making it suitable for developers.

## Features

- **Linux with Graphical Environment**: Choose from various Linux distributions and desktop environments according to your preferences in this case we are using Ubuntu desktop 22.04. 
- **Pre-installed Tools**: Slack and Docker ready to use.
- **Automatic Security Updates**: Configuration for automatically updating the operating system.
- **Custom User**: Instructions for creating a new user on the machine.

## Getting Started

To use this project, you will need:

- VirtualBox or any other compatible virtualization software.
- Internet access to download the chosen Linux distribution and updates.

### Installation and Configuration

1. **Creating the Virtual Machine**: Follow the detailed instructions in [INSTALLATION.md](INSTALLATION.md) to create and set up your virtual machine from scratch.
2. **Installing Tools**: Refer to the installation section in [INSTALLATION.md](INSTALLATION.md) for installing Slack, Docker, and configuring automatic updates.
3. **Creating a New User**: Instructions for creating a new user on your VM can be found in [CONFIGURATION.md](CONFIGURATION.md).

## Documentation

For more details on installing, configuring, and using your virtual machine, please refer to the following documents:

- [Installation and Configuration](INSTALLATION.md)
- [Automation and Scaling](Automation.md)




## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
