# Create CentOS7 Virtualbox VagrantBox

Using base box is centos/7

## Required
- Virtualbox
- [dotless-de/vagrant-vbguest](https://github.com/dotless-de/vagrant-vbguest)

## Create VirtualBox Guest Additions Software installed Box
```bash
vagrant up
vagrant reload
vagrant halt
vagrant packge --output centos7_vboxadd.box
vagrant destroy --force
# Adding box
vagrant box add --name centos7_vboxadd centos7_vboxadd.box
```

## keys Directory files
- Vagrant Insecure Keypair -> https://github.com/mitchellh/vagrant/tree/master/keys