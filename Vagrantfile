# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/ubuntu2004"
  config.vm.hostname = "web"
  # Port mapping for server 
  config.vm.network "forwarded_port", guest: 5000, host: 5000
  # Port mapping for client
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  # Port mapping for mongodb
  config.vm.network "forwarded_port", guest: 27017, host: 27017 
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
