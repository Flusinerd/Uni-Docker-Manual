# Docker Manual
<!-- TOC -->

- [Docker Manual]()
    - [System Requirements](#requirements)
      - [Windows 10 Pro / Enterprise / Education](#windows-10-pro--enterprise--education)
      - [Windows 10 Home](#windows-10-home)
      - [MacOS 10.13 or later](#macos-1013-or-later)
      - [Linux](#linux)
      - [Legacy Sytems (Windows 7, 8, MacOS 64-Bit)](#legacy-sytems-windows-7-8-macos-64-bit)
    - [Installation](#installation)
      - [Windows 10 Pro / Enterprise / Education](#windows-10-pro--enterprise--education-1)
      - [Windows 10 Home](#windows-10-home-1)
      - [MacOS 10.13 or later](#macos-1013-or-later-1)
      - [Linux](#linux-1)
      - [Legacy Sytems (Windows 7, 8, MacOS 64-Bit)](#legacy-sytems-windows-7-8-macos-64-bit-1)
    - [Docker Basics](#docker-basics)
      - [docker run](#docker-run)
      - [docker ps](#docker-ps)
      - [docker stop](#docker-stop-container)
      - [docker start](#docker-start-container)
      - [docker restart](#docker-restart-container)
      - [docker rename](#docker-rename-container-new-name)
      - [docker exec](#docker-exec-container-command-args)
      - [Ports in docker](#lets-have-a-look-at-ports-in-docker)
      - [Cleaning up](#lets-clean-everything-up-again)
    - [Docker Compose](#docker-compose)

<!-- /TOC -->

## Requirements:
- ### Windows 10 Pro / Enterprise / Education:
    - Build 16299 or later
    - Hyper-V and Containers Windows feature
- ### Windows 10 Home:
    - Version 2004 or later
    - [WSL2](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
    - [Linux Kernel Update](https://docs.microsoft.com/windows/wsl/wsl2-kernel)
- ### MacOS 10.13 or later:
    - Installer only
- ### Linux:
    - Depends on distro: Mainly add repo and install with packagemanager (Docker Engine)
- ### Legacy Sytems (Windows 7, 8, MacOS 64-Bit):
    - Virtualization turned on in the BIOS
    - 64-Bit System
## Installation:
- ### Windows 10 Pro / Enterprise / Education:
    - Check that you have **Build 19041** or higher:
      - Press Windows + R
      - type: `winver`
      - Check your windows version:  
      ![Windows Version](https://raw.githubusercontent.com/Flusinerd/Uni-Docker-Manual/master/windows-version.jpg)
    - Open a PowerShell **as administrator**:
      ![Powershell-Admin](https://raw.githubusercontent.com/Flusinerd/Uni-Docker-Manual/master/powershell-admin.jpg)
      - paste these commands: 
        - `dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`
        - `dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`
      - restart your machine
    - [Download](https://hub.docker.com/editions/community/docker-ce-desktop-windows/) Docker Desktop from DockerHub
    - Run the Installer
    - When prompted, ensure the Enable **Hyper-V Windows Features** option is selected on the Configuration page.
- ### Windows 10 Home:
    - Check that you have **Version 2004** or higher:
      - Press Windows + R
      - type: `winver`
      - Check your windows version:
      ![Windows Version](https://raw.githubusercontent.com/Flusinerd/Uni-Docker-Manual/master/windows-version.jpg)
    - Open a PowerShell **as administrator**:
      ![Powershell-Admin](https://raw.githubusercontent.com/Flusinerd/Uni-Docker-Manual/master/powershell-admin.jpg)
      - paste these commands: 
        - `dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`
        - `dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`
      - restart your machine
    - [Download](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi) the Linux Kernel Update and install it
    - [Download](https://hub.docker.com/editions/community/docker-ce-desktop-windows/) Docker Desktop from DockerHub
    - Run the Installer
    - When prompted, ensure the Enable **Hyper-V Windows Features** option is selected on the Configuration page.
- ### MacOS 10.13 or later:
    - [Download](https://hub.docker.com/editions/community/docker-ce-desktop-mac/) the installer from  DockerHub
    - Run the Installer
    - Verify that after the installation the Docker whale is in the statusbar
    ![Status-Bar](https://d1q6f0aelx0por.cloudfront.net/icons/whale-in-menu-bar.png)
- ### Linux:
    - Depends on distro: Mainly add repo and install with packagemanager (Docker Engine)
    - [CentOS](https://docs.docker.com/engine/install/centos/)
    - [Debian](https://docs.docker.com/engine/install/debian/)
    - [Fedora](https://docs.docker.com/engine/install/fedora/)
    - [Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
    - #### Aditional Step:
      - Add your user to ``docker`` group, so you dont have to run docker commands as sudo
- ### Legacy Sytems (Windows 7, 8, MacOS 64-Bit):
    - Check that you have Virtualization enabled in your BIOS-Settings (Windows only) 
    - Download the latest version from [Docker Toolbox Download](https://github.com/docker/toolbox/releases)
    ![Download](https://raw.githubusercontent.com/Flusinerd/Uni-Docker-Manual/master/Docker-Toolbox-Download.jpg) (exe for Windows, pkg for MacOS)
    - If you have Virtual Box installed already, stop Virtualbox.
    - Start the Installer
    - Install Docker Toolbox. If you already have VirtualBox installed, make sure that Virtual Box is unticked in the list.
## Docker Basics
- Lets go over some basic commands first and then have a look, how we can apply them.
- ### ``docker run``
  - To verify your installation you can run a imange named ``hello-world``  
    To run a container you can use the following command in a terminal:  
    ``docker run <image-name>``  
    If everything is installed correctly, you should see a ouput like this:
    ```bash
    jan@DESKTOP-QNT1UI3:~$ docker run hello-world
    Unable to find image 'hello-world:latest' locally
    latest: Pulling from library/hello-world
    0e03bdcc26d7: Pull complete
    Digest: sha256:d58e752213a51785838f9eed2b7a498ffa1cb3aa7f946dda11af39286c3db9a9
    Status: Downloaded newer image for hello-world:latest

    Hello from Docker!
    This message shows that your installation appears to be working correctly.

    To generate this message, Docker took the following steps:
    1. The Docker client contacted the Docker daemon.
    2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
        (amd64)
    3. The Docker daemon created a new container from that image which runs the
        executable that produces the output you are currently reading.
    4. The Docker daemon streamed that output to the Docker client, which sent it
        to your terminal.

    To try something more ambitious, you can run an Ubuntu container with:
    $ docker run -it ubuntu bash

    Share images, automate workflows, and more with a free Docker ID:
    https://hub.docker.com/

    For more examples and ideas, visit:
    https://docs.docker.com/get-started/
    ```
    **This message tells the the following:**  
    - ``Unable to find image <image_name>:<image_tag> locally``  
      - This simply says, that you dont have that image installed locally and it will be pulled from [Docker Hub](https://hub.docker.com/)
    - ``Hello from Docker!...``
      - This is the output of your container you just ran. It tells you that you installed docker successfully.
- ### `docker ps`
  - With ``docker ps`` you can lust your currently running containers:
    - If you run ``docker ps`` now you should not see any containers listed, since the ``hello-world`` container quits after it has printed the message.
    - Lets run a ``nginx`` container and see how this works.
    - Run the command ``docker run -d nginx``
      - This will run a ``nginx`` container in detached mode
      - The ``-d`` flag is responsible for running in detached mode. This means, that your current terminal will not be bound to the terminal of the container and the container will run in the background.
      - You can also give your docker container names with the ``--name <some-name>`` flag. For example: ``docker run --name nginx-container -d nginx``
    - If you run ``docker ps`` again, you should see your nginx container running.
- ### `docker stop <container>`
  - With ``docker stop <container>`` you can stop a running container.
  - Replace ``<container>`` with either the name or the ID of your container.
  - You can partially type the name or the ID of the container as long as it is not ambiguous.
    - For example if the ID of my container is: ``b76c9507a43e``, then I can just type ``b76`` as long as no other containers ID starts with ``b76``.
    - You have to fully type the container names, but you can use the ``tab`` key for autocompletion
  - If you run ``docker ps`` again, you should see, that your nginx container is gone.
  - You can run ``docker ps -a`` to list all containers (including stopped ones).
- ### `docker start <container>`
  - This is the oposite of the stop command and it allows you to start a stopped container again.
- ### ``docker restart <container>``
  - This command allows you to restart a running or stopped container
- ### ``docker rename <container> <new-name>`` 
  - This command allows you to rename a container
- ### ``docker exec <container> <command> <args>``
  - This command runs ``<command>`` with the provided ``<args>`` inside the container. This is usefull for example if you want to open a terminal inside the container:
    - ``docker exec -it <container> bash``
      - This will run a bash shell in the provided container in interactive mode:
      - ``-it`` tells docker to run the command in interactive mode. This can also be used together with ``docker  run``
      - You can exit the containers shell again with ``exit``
- ### Lets have a look at ports in docker
  - In Docker the containers run isolated from your system inside their own network. This means, that you can't access your containers ports, like you would for example if you were running a nginx on your own machine.
  - Docker Containers ``EXPOSE`` ports that can then be mapped to any port on your local machine.
  - To do this we can use the ``-p <local_port>:<container_port>`` flag together with the ``docker run`` command.
  - So lets stop our current nginx container, if it is running and lets start a new one and map the containers port ``80`` to our port ``81``
  - To do this we run this command:
    - ``docker run -d -p 81:80 nginx``
      - Lets go over this command:
        - We run a new container from the ``nginx`` image 
        - We say, that it should run in the background with the ``-d`` flag
        - We want the container port ``80`` to be available as port ``81`` on our machine
  - If you run ``docker ps`` again you should see, that the nginx container is running and that our port ``81`` is mapped to the container port ``80``
  - Now open a browser on your machine and go to ``http://localhost:81``.
  - You should be greeted by the default nginx page.
- ### Lets clean everything up again
  - First let us stop all running containers:
  - List the running containers with ``docker ps``
  - Then stop each container with ``docker stop``
  - Verify that no container is listed, when running ``docker ps``, that means we have no **running** container.
  - Now lets list all containers ``docker ps -a``
  - Now we can remove each container with the command ``docker rm <container>``
    - It is similar to the ``docker stop`` command, but instead of stopping the container, and beeing able to start it later again, it removes the container.
    - @Todo: Possibilty to link commands? eg: Delete all containers at once


## Docker Compose
  @Todo: Add compose if we use compose