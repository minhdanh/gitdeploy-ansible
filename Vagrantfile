# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network "private_network", ip: "192.168.33.11"
    config.vm.provider "virtualbox" do |v|
      v.memory = 512
    end
    config.vm.define "webapp" do |app|
      app.vm.network "forwarded_port", guest: 80, host: 8001
      app.vm.provision :ansible do |ans|
        ans.playbook = "playbook.yml"
      end
    end
end
