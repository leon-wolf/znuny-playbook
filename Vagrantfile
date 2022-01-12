# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "otrs" do |otrs|
    otrs.vm.box = "check24-shopping/debian10-arm64"
    otrs.vm.provider :parallels do |v|
      v.name = "otrs"
      v.memory = 4096 
      v.cpus = 4
    end
    otrs.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook_otrs.yml"
    end
    otrs.vm.network "private_network", ip: "192.168.50.4"
  end

  config.vm.define "db" do |db|
    db.vm.box = "check24-shopping/debian10-arm64"
    db.vm.provider :parallels do |v|
      v.name = "db"
      v.memory = 4096
      v.cpus = 4
    end
    db.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook_db.yml"
    end
    db.vm.network "private_network", ip: "192.168.50.5"
  end
  
end
