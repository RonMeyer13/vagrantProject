# -*- mode: ruby -*-
# vi: set ft=ruby :

 
Vagrant.configure("2") do |config|
  config.vm.define "webserver" do |webserver|
   config.vm.synced_folder ".", "/vagrant", type: "smb"
   webserver.vm.box="ubuntu/trusty64"
   webserver.vm.network "private_network",ip: "192.168.0.2"
   webserver.vm.hostname="webserver"
  end
  config.vm.define "ansible" do |ansible|
   config.vm.synced_folder ".", "/vagrant", type: "smb"
   ansible.vm.box="ubuntu/trusty64"
   ansible.vm.network "private_network",ip: "192.168.0.254"
   ansible.vm.hostname="ansible"
  end

  # config.vm.box = "ubuntu/trusty64"

  #
  # config.vm.box_check_update = false
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  # config.vm.network "private_network", ip: "192.168.33.10"
  # config.vm.network "public_network"
  # config.vm.synced_folder "../data", "/vagrant_data"

   config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
    vb.gui = false
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
   end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision "shell", inline: <<-SHELL
     apt-get update
     apt-get install -y apache2
  SHELL
end
