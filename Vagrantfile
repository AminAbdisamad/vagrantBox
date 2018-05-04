# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
 

  config.vm.box = "ubuntu/trusty64"

  # Provider setting  
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1024
    vb.cpus = 2
 
  end

#Network Setting

  #config.vm.network "forwarded_port", guest: 80, host: 8088
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  config.vm.network "private_network", ip: "192.168.33.10"
  # config.vm.network "public_network"

  #Shared Folder
  config.vm.synced_folder ".", "/var/www/html", :nfs=> { :mount_options => ["dmode=777","fmode=666"]}

 
#Provisions
  config.vm.provision "shell", path: "install.sh"
end
