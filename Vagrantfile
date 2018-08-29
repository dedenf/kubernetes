# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

$script = <<SCRIPT
  echo I am provisioning...
  sudo yum install vim
SCRIPT

Vagrant.configure("2") do |config|
  
  config.vm.define "master" do |master|
    master.vm.box = "centos7latest"
    master.vm.host_name = 'k8s-master'
    master.vm.network "forwarded_port", guest: 80, host: 8010
    master.vm.network "forwarded_port", guest: 22, host: 2224
    master.vm.network "private_network", ip: "10.10.11.11"
    
    #master.vm.provision "shell", inline: $script # Just install it

    # Increase memory for Virtualbox
    master.vm.provider "virtualbox" do |vb|
        vb.memory = "2048"
    end
  end

  config.vm.define "kube1" do |kube1|
    kube1.vm.box = "centos7latest"
    kube1.vm.host_name = 'kube1'
    kube1.vm.network "forwarded_port", guest: 80, host: 8011
    kube1.vm.network "forwarded_port", guest: 22, host: 2225
    kube1.vm.network "private_network", ip: "10.10.11.12"
    
    #kube1.vm.provision "docker" # Just install it

    # Increase memory for Virtualbox
    kube1.vm.provider "virtualbox" do |vb|
        vb.memory = "2048"
    end
  end

  config.vm.define "kube2" do |kube2|
    kube2.vm.box = "centos7latest"
    kube2.vm.host_name = 'kube2'
    kube2.vm.network "forwarded_port", guest: 80, host: 8012
    kube2.vm.network "forwarded_port", guest: 22, host: 2226
    kube2.vm.network "private_network", ip: "10.10.11.13"
    
    #slave2.vm.provision "docker" # Just install it

    # Increase memory for Virtualbox
    kube2.vm.provider "virtualbox" do |vb|
        vb.memory = "2048"
    end
  end

  config.vm.define "kube3" do |kube3|
    kube3.vm.box = "centos7latest"
    kube3.vm.host_name = 'kube3'
    kube3.vm.network "forwarded_port", guest: 80, host: 8013
    kube3.vm.network "forwarded_port", guest: 22, host: 2227
    kube3.vm.network "private_network", ip: "10.10.11.14"
    
    #slave2.vm.provision "docker" # Just install it

    # Increase memory for Virtualbox
    kube3.vm.provider "virtualbox" do |vb|
        vb.memory = "2048"
    end
  end

end
