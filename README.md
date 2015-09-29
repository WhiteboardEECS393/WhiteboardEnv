# Whiteboard Environment
The basic development environment we'll be using for Whiteboard.
It uses Vagrant for provisioning and creating the VM that we'll use for consistency in environment.
If you haven't used it before, here's some quick tips to get started.
1. Download VirtualBox from https://www.virtualbox.org/wiki/Downloads Get the most recent version since some past versions have had trouble with Vagrant on some platforms.
2. Download Vagrant from https://www.vagrantup.com/
3. Clone both this repo and the main Whiteboard repo into the same folder. After this, you should have a folder that contains two folders, WhiteboardEnv and whiteboard.
4. Change to the WhiteboardEnv folder and run "vagrant up". Tons of text will probably scroll up the screen, but you probably don't have to worry about it. It's just setting up the VM.
5. After that's done, you can run "vagrant ssh" from the same folder to connect to the VM and perform actions inside.

In general, you should develop your code from the whiteboard folder outside the VM and then use the "vagrant reload" command to allow the changes to propagate through to the VM.

Inside the VM, we are using virutalenv and a requirements.txt to maintain a consistant list of packages we're using in this project. 
If you do install any new packages through pip, make sure you replace the current requirements.txt by doing a "pip freeze > requirements.txt"

Before starting the project's server in the vm, make sure to enter the whiteboard\_env (in the VM) and run "source bin/activate" This will activate the virtual environment and make sure that the right version of Python is being used and the proper packages are loaded.

The virtual machine has port 8000 forwarded to your system's port 8080, so make sure when you run the project's test server, you run it on port 8000.
