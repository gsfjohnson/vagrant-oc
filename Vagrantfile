# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "gsfjohnson/centos71"

  config.vm.define "oc" do |v|
    v.vm.network "forwarded_port", guest: 80, host: 8080
    v.vm.network "forwarded_port", guest: 443, host: 8443
    v.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
    v.vm.hostname = "oc"

    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
    end
  end

end
