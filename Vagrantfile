# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # boxes at https://vagrantcloud.com/search.
  config.vm.define "jenkinshost" do |jenkinshost|
    jenkinshost.vm.box = "myubuntu"
    jenkinshost.vm.network "forwarded_port", guest: 80, host: 2090
    jenkinshost.vm.network "private_network", ip: "192.168.1.4"
    jenkinshost.vm.hostname = "jenkinshost"
  end
  config.vm.define "jenkinsnode" do |jenkinsnode|
    jenkinsnode.vm.box = "myubuntunode"
    jenkinsnode.vm.network "forwarded_port", guest: 80, host: 2089
    jenkinsnode.vm.network "private_network", ip: "192.168.1.3"
    jenkinsnode.vm.hostname = "jenkinsnode"
  end

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
