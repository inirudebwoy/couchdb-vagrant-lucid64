# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "lucid64"
  config.vm.network "forwarded_port", guest: 5984, host: 5984
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y python-software-properties curl
    sudo add-apt-repository ppa:longsleep/couchdb
    sudo apt-get update
    sudo apt-get install -y couchdb
    sudo sed -i.bak "s/;bind_address = 127.0.0.1/bind_address=0.0.0.0/g" /etc/couchdb/local.ini
    sudo reboot
  SHELL
end
