
## Creating a New User

If you need to create additional users on your VM, you can do so by running:
sudo adduser newusername

Replace `newusername` with the desired username. Follow the on-screen prompts to set up the new user.

If you want to add admin privilages to thta user type:

usermod -aG sudo newusername

## Conclusion

Your Linux VM is now set up with a graphical environment, Slack, Docker, and configured for automatic security updates. , refer to [AUTOMATION.md](docs/AUTOMATION.md).
