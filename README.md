## Usage

Get the [license.lic](https://github.com/NuCivic/nuams-vm/blob/1.1/license.lic)

### VMWare
    * OSX (VMWare Fusion)
      - Install VMWare Fusion 6
      -  `$ brew install vagrant`
      -  `$ brew install ansible`
    * OS X (virtualbox)
      - `$ brew cask install virtualbox vagrant`
      - `$ brew install ansible`
  1. Install vmware plugin ``vagrant plugin install vagrant-vmware-fusion``
  2. Install vmware license ``vagrant plugin license vagrant-vmware-fusion license.lic``
  3. Install all the roles required by this playbook with the command `$ ansible-galaxy install -r requirements.txt`
  4. Create a config file based on config.yml.sample
  5. Run! ``vagrant up --provider vmware_fusion`` or ``vagrant up`` on virtual box
  6. You will need to run ``vagrant provision`` an additional time. Ref: https://github.com/NuCivic/ansible-dev-vm/issues/26
  7. When you ``vagrant ssh`` you should see:
```
Welcome to
 ____               __     ____  __      ____    ___
|  _ \  _____   __  \ \   / /  \/  |    |___ \  / _ \
| | | |/ _ \ \ / /___\ \ / /| |\/| |_____ __) || | | |
| |_| |  __/\ V /_____\ V / | |  | |_____/ __/ | |_| |
|____/ \___| \_/       \_/  |_|  |_|    |_____(_)___/

Provided by
 _   _        ____ _
| \ | |_   _ / ___(_)_   _____
|  \| | | | | |   | \ \ / / __|
| |\  | |_| | |___| |\ V / (__
|_| \_|\__,_|\____|_| \_/ \___|
```
  


### VirtualBox
  1. Install [Virtualbox](https://www.virtualbox.org/), [Vagrant](https://www.vagrantup.com/downloads.html), and [Ansible](http://docs.ansible.com/intro_installation.html):
    * Ubuntu
      - `$ sudo aptitude install virtualbox ansible vagrant`
  2. Start at step #3 for VMWare above


#### Vagrant ssh

To start this party:

1) type ``vagrant ssh`` to ssh into new box

#### Using browser

1) type ``ifconfig`` in the vm. Grab the IP number from the eth0. for virtualbox this should just be 33.33.33.33. For VMware it wil be something like 192.168.231.132.
2) add the ip address and site name to the /etc/hosts file. type: "sudo vim /etc/hosts" and enter IP_ADDRESS URL for any sites you use on the vm. 

Example:

```
192.168.231.132 nydmv.local
```

for dmv on VMware

## Configuration tips

At least 4 Gigs seems to be the optimal amount of memory to assign in config.yml. Also, if you experience slow performace, try opening the vmware-fusion app (if that's the provider you're using) and adjust the processor settings. 
