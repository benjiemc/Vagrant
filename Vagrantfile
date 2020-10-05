# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-20.04"
  config.ssh.forward_agent = true


  # Options to setup a public or private network
  # config.vm.network "private_network", ip: "192.168.33.10"
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  config.vm.synced_folder "../Documents/code", "/home/vagrant/code"

  config.vm.provider "virtualbox" do |vb|
      # Customize the amount of memory on the VM:
      vb.memory = "2048"
  end

  # Provisioning a "python" box --> note this is the primary box
  config.vm.define "python", primary: true do |python|
     # Load startup text
     icon = File.open("icons/python-load-icon")
     config.vm.post_up_message = icon.read
     icon.close

     # Port Forwarding
     python.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
     python.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y git
        sudo add-apt-repository -y ppa:deadsnakes/ppa
        sudo apt-get install -y python3
        sudo apt-get install -y python3-pip
      SHELL
   end

   config.vm.provision "shell", inline: <<-SHELL
      apt-get install -y stow
   SHELL

end
