# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"

  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.hostname = "mz-server"
    ubuntu.vm.provider "virtualbox" do |vb|
    vb.name = "ubuntu-server"
    vb.cpus = 2
    vb.memory = 2048
    end
    ubuntu.vm.network"public_network"
    ubuntu.vm.network "private_network", ip: "192.168.33.10"
    ubuntu.vm.network "forwarded_port", host: 80, guest: 80
  end
end