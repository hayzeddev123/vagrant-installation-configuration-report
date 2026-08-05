# Report on the Installation and Configuration of Vagrant

## Introduction

In this practical, I installed and configured Vagrant to create and manage a virtual machine. I also installed Oracle VM VirtualBox, which Vagrant used as the virtualization provider. I used Ubuntu 22.04 (Jammy Jellyfish) as the operating system for the virtual machine.

## Installation Process

1. I downloaded the Oracle VM VirtualBox installer from the official website.

2. I ran the installer and followed the installation wizard to install Oracle VM VirtualBox on my Windows computer.

3. I downloaded the Vagrant installer from the official website.

4. I ran the Vagrant installer and completed the installation.

5. I opened Visual Studio Code and created a new project folder named VagrantLab.

6. I opened the integrated terminal in Visual Studio Code and navigated to the project folder.

7. I initialized a new Vagrant project by running the following command:
   
   ```
   vagrant init
   ```

8. This command created a default Vagrantfile in my project folder.

## Configuration Process

1. I opened the Vagrantfile in Visual Studio Code.

2. I changed the box to:
   
   ```
   config.vm.box = "ubuntu/jammy64"
   ```

3. I configured the VirtualBox provider by assigning 2048 MB of memory and 2 CPUs to the virtual machine.

4. I enabled shell provisioning to automatically install the Apache web server when the virtual machine was created.

5. I saved the Vagrantfile after making the required changes.

## Creating the Virtual Machine

1. I started the virtual machine by running:
   
   ```
   vagrant up
   ```

2. Vagrant downloaded the ubuntu/jammy64 box from Vagrant Cloud because it was the first time I was using it.

3. After the download was complete, Vagrant created and started the virtual machine in Oracle VM VirtualBox.

4. Vagrant mounted the shared folder and automatically ran the provisioning script.

5. The provisioning script updated the package list and installed the Apache web server.

## Connecting to the Virtual Machine

1. After the virtual machine started successfully, I connected to it by running:
   
   ```
   vagrant ssh
   ```

2. I confirmed that the virtual machine was running Ubuntu 22.04.5 LTS (Jammy Jellyfish) by checking the operating system information.

3. I checked the Apache service and confirmed that it was Active (running).

## Destroying the Virtual Machine

1. After completing the practical, I exited the virtual machine by typing:
   
   ```
   exit
   ```

2. I destroyed the virtual machine by running:
   
   ```
   vagrant destroy
   ```

3. I confirmed the operation by typing y when prompted. This removed the virtual machine while keeping the Vagrant project files and the downloaded Ubuntu box.

## Conclusion

Through this practical, I successfully installed Oracle VM VirtualBox and Vagrant, configured a Vagrant environment, created an Ubuntu virtual machine, connected to it using SSH, verified that Apache was running, and destroyed the virtual machine after completing the exercise. This practical helped me understand the basic workflow of using Vagrant to create, configure, and manage virtual machines.