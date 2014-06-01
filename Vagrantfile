# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "precise64"

  config.vm.define "web1" do |web1|
    web1.vm.network "forwarded_port", guest: 80, host: 8080
    web1.vm.network "private_network", ip: "192.168.33.10"
  end

  config.vm.define "web2" do |web2|
    web2.vm.network "forwarded_port", guest: 80, host: 8081
    web2.vm.network "private_network", ip: "192.168.33.11"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/site.yml"
    ansible.inventory_path = "provision/inventory.ini"
    ansible.sudo = "true"
    ansible.sudo_user = "root"
    ansible.host_key_checking = "false"
  end

end
