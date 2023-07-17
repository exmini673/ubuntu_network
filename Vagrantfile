# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.define "host1" do |host1|
    host1.vm.hostname = "host1"
    host1.vm.provider "virtualbox" do |vb|
    vb.name = "host1"
    vb.cpus = 2
    vb.memory = 2048
    end
    host1.vm.network "public_network"
    host1.vm.network "private_network", ip: "192.168.0.2"

    host1.vm.provision "shell", inline: <<-SCRIPT
     sudo ip route del default via 10.0.2.2 dev enp0s3
     SCRIPT
  end

  config.vm.define "host2" do |host2|
    host2.vm.hostname = "host2"
    host2.vm.provider "virtualbox" do |vb|
      vb.name = "host2"
      vb.cpus = 2
      vb.memory = 2048
    end
    host2.vm.network "private_network", ip: "192.168.0.3"
    
    host2.vm.provision "shell", inline: <<-SCRIPT
      sudo ip route del default via 10.0.2.2 dev enp0s3
    SCRIPT
  end
  config.vm.define "host3" do |host3|
      host3.vm.hostname = "host3"
      host3.vm.provider "virtualbox" do |vb|
      vb.name = "host3"
      vb.cpus = 2
      vb.memory = 2048
      end
      host3.vm.network "private_network", ip: "192.168.0.4"

      host3.vm.provision "shell", inline: <<-SCRIPT
       sudo ip route del default via 10.0.2.2 dev enp0s3
       SCRIPT
    end
end

