# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "otrs" do |otrs|
    otrs.vm.box = "avi0xff/debian10-arm64"
    otrs.vm.provider :parallels do |v|
      v.name = "otrs"
      v.memory = 2048
      v.cpus = 2
    end
    otrs.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook_otrs.yml"
    end
    otrs.vm.network "private_network", ip: "192.168.50.4"
  end

  config.vm.define "db" do |db|
    db.vm.box = "avi0xff/debian10-arm64"
    db.vm.provider :parallels do |v|
      v.name = "db"
      v.memory = 2048
      v.cpus = 2
    end
    db.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook_db.yml"
    end
    db.vm.network "private_network", ip: "192.168.50.5"
  end
  
end