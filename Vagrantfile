# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/8"

  
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 2
  end
  
  config.vm.define "otus-pam-0" do |vm0|
    vm0.vm.network "private_network", ip: "192.168.50.10", virtualbox__intnet: "net1"
    vm0.vm.hostname = "otus-pam-0"
  end

  config.vm.define "otus-pam-1" do |vm1|
    vm1.vm.network "private_network", ip: "192.168.50.11", virtualbox__intnet: "net1"
    vm1.vm.hostname = "otus-pam-1"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.become = "true"
  end

end
