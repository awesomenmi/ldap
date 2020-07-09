# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
  
  config.vm.box_check_update = false
  config.vbguest.auto_update = false

  config.vm.define "ipaserver" do |ipaserver|
    ipaserver.vm.hostname = "ipaserver.home.local"
    ipaserver.vm.network "private_network", ip: "10.0.10.2"

    ipaserver.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
      vb.cpus = "2"
    end
  end

  config.vm.define "client" do |client|
    client.vm.hostname = "client.home.local"
    client.vm.network "private_network", ip: "10.0.10.3"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision.yml"
  end


end
