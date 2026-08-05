# Report on the Installation and Configuration of Vagrant

## Installation and Configuration Report

This project documents the installation and configuration of **Vagrant** (with Oracle VM VirtualBox as the provider) to create and manage a virtual machine on a Windows system.

**This documentation is written as a step-by-step tutorial guide** so that someone else (or your future self) can easily follow and replicate the exact same setup.

---

### 1. Installing Oracle VM VirtualBox and Vagrant

**Installation Steps**

1. Downloaded the **Oracle VM VirtualBox** installer from the official website.
2. Ran the installer and followed the installation wizard to install Oracle VM VirtualBox on my Windows computer.
3. Downloaded the **Vagrant** installer from the official HashiCorp website.
4. Ran the Vagrant installer and completed the installation.
5. Opened **Visual Studio Code** and created a new project folder named `VagrantLab`.
6. Opened the integrated terminal in Visual Studio Code and navigated to the project folder.
7. Initialized a new Vagrant project by running:

   ```bash
   vagrant init
   ```

8. This command created a default `Vagrantfile` in the project folder.

---

### 2. Configuring the Vagrantfile

**Configuration Steps**

1. Opened the `Vagrantfile` in Visual Studio Code.
2. Changed the box to Ubuntu 22.04 (Jammy Jellyfish):

   ```ruby
   config.vm.box = "ubuntu/jammy64"
   ```

3. Configured the VirtualBox provider by assigning **2048 MB** of memory and **2 CPUs** to the virtual machine.
4. Enabled **shell provisioning** to automatically install the Apache web server when the virtual machine is created.
5. Saved the `Vagrantfile` after making the required changes.

![Vagrantfile showing config.vm.box = "ubuntu/jammy64" and terminal session](images/Screenshot%202026-08-05%20171236.png)

---

### 3. Creating and Starting the Virtual Machine

**Steps**

1. Started the virtual machine by running:

   ```bash
   vagrant up
   ```

2. Vagrant downloaded the `ubuntu/jammy64` box from Vagrant Cloud (first time use).
3. After the download completed, Vagrant created and started the virtual machine in Oracle VM VirtualBox.
4. Vagrant mounted the shared folder and automatically ran the provisioning script.
5. The provisioning script updated the package list and installed the **Apache** web server.

---

### 4. Connecting to the Virtual Machine

**Steps**

1. After the virtual machine started successfully, I connected to it by running:

   ```bash
   vagrant ssh
   ```

2. Confirmed that the virtual machine was running **Ubuntu 22.04.5 LTS (Jammy Jellyfish)**.
3. Checked the Apache service and confirmed that it was **Active (running)**.

---

### 5. Destroying the Virtual Machine

**Steps**

1. After completing the practical, I exited the virtual machine by typing:

   ```bash
   exit
   ```

2. Destroyed the virtual machine by running the following command **from the host** (PowerShell):

   ```bash
   vagrant destroy
   ```

3. Confirmed the operation by typing `y` when prompted. This removed the virtual machine while keeping the Vagrant project files and the downloaded Ubuntu box.

**Note:** Running `vagrant` commands *inside* the guest VM fails with “command not found” because Vagrant is installed on the host, not inside the virtual machine. This is expected behavior (as shown in the screenshot above).

---

### 6. Official Vagrant Documentation Reference

For complete and up-to-date information, always refer to the official HashiCorp Vagrant documentation:

![HashiCorp Developer Vagrant landing page – Development Environments Made Easy](images/Screenshot%202026-08-05%20171559.png)

- Official site: [https://developer.hashicorp.com/vagrant](https://developer.hashicorp.com/vagrant)
- Installation guide: [https://developer.hashicorp.com/vagrant/docs/installation](https://developer.hashicorp.com/vagrant/docs/installation)

---

## Conclusion

I successfully:

- Installed Oracle VM VirtualBox and Vagrant
- Configured a Vagrant environment with the `ubuntu/jammy64` box
- Created an Ubuntu 22.04 virtual machine
- Connected to it using SSH
- Verified that Apache was running
- Destroyed the virtual machine after completing the exercise

This practical helped me understand the basic workflow of using **Vagrant** to create, configure, and manage virtual machines.

All screenshots referenced above are stored in the `images/` folder of this repository and are embedded using standard Markdown image syntax so they display correctly on GitHub.

---

## How the screenshots are referenced (for future reference)

In Markdown, images are referenced with the following syntax:

```markdown
![Descriptive alt text](relative/path/to/image.jpg)
```

- The `!` makes it an image instead of a normal link.
- The text inside `[]` is the **alt text** (important for accessibility and when the image cannot load).
- The path inside `()` is relative to the Markdown file. Spaces in filenames are encoded as `%20`.

Example used in this document:

```markdown
![Vagrantfile showing config.vm.box = "ubuntu/jammy64" and terminal session](images/Screenshot%202026-08-05%20171236.png)
```
