# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.define "gw" do |gw|
    gw.vm.hostname = "gateway"
    gw.vm.provider "virtualbox" do |vb|
    vb.name = "gateway"
    vb.cpus = 2
    vb.memory = 2048
    end
    gw.vm.network "public_network" # DHCP
    gw.vm.network "private_network", ip: "192.168.33.254", virtualbox__intnet: true

    gw.vm.provision "shell", inline: <<-SCRIPT
     sudo ip route del default via 10.0.2.2 dev enp0s3
     SCRIPT
  end

  config.vm.define "nginx_web" do |nginx_web|
    nginx_web.vm.hostname = "nginx-web-server"
    nginx_web.vm.provider "virtualbox" do |vb|
      vb.name = "nginx-web-server"
      vb.cpus = 2
      vb.memory = 2048
    end
    nginx_web.vm.network "private_network", ip: "192.168.33.10", virtualbox__intnet: true
    
    nginx_web.vm.provision "shell", inline: <<-SCRIPT
    SCRIPT
  end
  config.vm.define "apache_web" do |apache_web|
    apache_web.vm.hostname = "apache-web-server"
    apache_web.vm.provider "virtualbox" do |vb|
      vb.name = "apache-web-server"
      vb.cpus = 2
      vb.memory = 2048
      end
      apache_web.vm.network "private_network", ip: "192.168.33.20", virtualbox__intnet: true

      apache_web.vm.provision "shell", inline: <<-SCRIPT
      SCRIPT
    end
end

