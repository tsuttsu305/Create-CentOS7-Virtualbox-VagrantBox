# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.ssh.private_key_path = "keys/vagrant"
  ## Base Box File
  config.vm.box = "centos/7"

  ## Auto Update Box
  config.vm.box_check_update = false

  ## Networking
  config.vm.network "private_network", ip: "192.168.33.33"
  
  ## Sync Folder
  config.vm.synced_folder ".", "/vagrant", type: nil
  
  config.vm.provider "virtualbox" do |vbox, override|
    vbox.gui = false
    vbox.linked_clone = true
    ## Advanced virtualbox configuration
    vbox.cpus = 2
    vbox.memory = 512
    vbox.customize [
    "modifyvm", :id,
    "--cpus", "2",
    "--memory", "1024",
    "--ostype", "RedHat_64",
    "--cpuexecutioncap", "80",
    "--pae", "on",
    "--hwvirtex", "on",
    "--vtxvpid", "on",
    "--vtxux", "on",
    "--ioapic", "on",
    "--paravirtprovider", "kvm",
    "--nestedpaging", "on",
    "--largepages", "on",
    ]
  end
  config.vm.provision "shell", inline: "sudo ln -s -f /dev/null /etc/udev/rules.d/70-persistent-net.rules"
end
