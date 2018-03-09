# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
    # create master/slave for HA cluster
    # https://docs.vagrantup.com/v2/vagrantfile/tips.html
    config.ssh.password = "vagrant"
    # config.ssh.insert_key = false
    (1..2).each do |i|
        config.vm.define "Linux-HA-PoC-node#{i}" do |node|
            node.vm.box = "metron/centos_base"
            node.vm.hostname = "ha-node#{i}"
            node.vm.network :private_network,ip: "192.168.3.1#{i}"
            node.vm.provider "virtualbox" do |vb|
                vb.memory = 768
                vb.cpus = 1
            end
        end
    end
end
