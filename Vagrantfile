# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/vivid64"
  config.vm.network :private_network, ip: "192.168.33.39"
  config.ssh.insert_key = false

  config.vm.provider :virtualbox do |v|
    v.name = "bootstrap.dev"
    v.memory = 1024
    v.vm.synced_folder "./", "/bootstrap", type: "nfs"
  end

  # Enable provisioning with Ansible.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/main.yml"
  end

end
