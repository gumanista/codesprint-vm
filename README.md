## Accounts:
### MySQL
user: root
password: root

### Virtual machine
- vagrant ssh
- user: vagrant, password: vagrant

### Drupal
user: admin
password: test

## Installation

### 1 - Install dependencies (VirtualBox and Vagrant)

  1. Download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) (Drupal VM also works with Parallels or VMware, if you have the [Vagrant VMware integration plugin](http://www.vagrantup.com/vmware)).
  2. Download and install [Vagrant](http://www.vagrantup.com/downloads.html).

Note for Faster Provisioning (Mac/Linux only): *[Install Ansible](http://docs.ansible.com/intro_installation.html) on your host machine, so Drupal VM can run the provisioning steps locally instead of inside the VM.*

Note for Linux users: *If NFS is not already installed on your host, you will need to install it to use the default NFS synced folder configuration. See guides for [Debian/Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-nfs-mount-on-ubuntu-14-04), [Arch](https://wiki.archlinux.org/index.php/NFS#Installation), and [RHEL/CentOS](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-nfs-mount-on-centos-6).*

Note on versions: *Please make sure you're running the latest stable version of Vagrant, VirtualBox, and Ansible, as the current version of Drupal VM is tested with the latest releases. As of August 2015: Vagrant 1.7.4, VirtualBox 5.0.2, and Ansible 1.9.2.*

### 3 - Configure your host machine to access the VM.

Add the line `192.168.44.45  codesprint.dev

### 4 - Prepare environment variables

  1. go to vagrant folder
  2. Update vagrant_synced_folders variable in config.yml
  2. run ansible-playbook install -r provisioning/requirements.txt -p provisioning/roles

### 5 - Start vagrant

  vagrant up

## Directories structure:

  - .build           # holds built drupal installations (if any)
  - vagrant          # vagrant installation

