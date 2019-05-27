# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.network "public_network", bridge: "wlp3s0"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "4096"
    vb.name = "devbox"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/install_python.yml"
    ansible.verbose = "vvv"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.verbose = "vvv"
  end
end
