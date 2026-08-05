# Report on the Installation and Configuration of Vagrant

---

## Introduction

In this practical, I installed and configured **Vagrant** to create and manage a virtual machine. I also installed **Oracle VM VirtualBox**, which Vagrant used as the virtualization provider. I used **Ubuntu 22.04 (Jammy Jellyfish)** as the operating system for the virtual machine.

---

## Installation Process

1. Downloaded the **Oracle VM VirtualBox** installer from the official website.
2. Ran the installer and followed the installation wizard to install Oracle VM VirtualBox on my Windows computer.
3. Downloaded the **Vagrant** installer from the official website.
4. Ran the Vagrant installer and completed the installation.
5. Opened **Visual Studio Code** and created a new project folder named `VagrantLab`.
6. Opened the integrated terminal in Visual Studio Code and navigated to the project folder.
7. Initialized a new Vagrant project by running the following command:

   ```bash
   vagrant init
   ```

8. This command created a default `Vagrantfile` in my project folder.

---

## Configuration Process

1. Opened the `Vagrantfile` in Visual Studio Code.
2. Changed the box to:

   ```ruby
   config.vm.box = "ubuntu/jammy64"
   ```

3. Configured the VirtualBox provider by assigning **2048 MB** of memory and **2 CPUs** to the virtual machine.
4. Enabled **shell provisioning** to automatically install the Apache web server when the virtual machine was created.
5. Saved the `Vagrantfile` after making the required changes.

---

## Creating the Virtual Machine

1. Started the virtual machine by running:

   ```bash
   vagrant up
   ```

2. Vagrant downloaded the `ubuntu/jammy64` box from Vagrant Cloud because it was the first time I was using it.
3. After the download was complete, Vagrant created and started the virtual machine in Oracle VM VirtualBox.
4. Vagrant mounted the shared folder and automatically ran the provisioning script.
5. The provisioning script updated the package list and installed the **Apache** web server.

---

## Connecting to the Virtual Machine

1. After the virtual machine started successfully, I connected to it by running:

   ```bash
   vagrant ssh
   ```

2. Confirmed that the virtual machine was running **Ubuntu 22.04.5 LTS (Jammy Jellyfish)** by checking the operating system information.
3. Checked the Apache service and confirmed that it was **Active (running)**.

---

## Destroying the Virtual Machine

1. After completing the practical, I exited the virtual machine by typing:

   ```bash
   exit
   ```

2. Destroyed the virtual machine by running:

   ```bash
   vagrant destroy
   ```

3. Confirmed the operation by typing `y` when prompted. This removed the virtual machine while keeping the Vagrant project files and the downloaded Ubuntu box.

---

## Conclusion

Through this practical, I successfully:

- Installed Oracle VM VirtualBox and Vagrant
- Configured a Vagrant environment
- Created an Ubuntu virtual machine
- Connected to it using SSH
- Verified that Apache was running
- Destroyed the virtual machine after completing the exercise

This practical helped me understand the basic workflow of using **Vagrant** to create, configure, and manage virtual machines.