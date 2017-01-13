# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANTFILE_API_VERSION = 2
BOX = "bento/ubuntu-16.04"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Chef Server config
  config.vm.define "chefserver" do |server|
    server.vm.box = BOX
    server.vm.hostname = 'chefserver.abcd.xyz'
    server.vm.network "private_network", ip: "192.168.100.10", virtualbox__hostonly: true
    server.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory", "2048"]
        # vb.gui = true
    end
  end
  # Chef Workstation config
  config.vm.define "chefws" do |ws|
    ws.vm.box = BOX
    ws.vm.hostname = 'chefws.abcd.xyz'
    ws.vm.network "private_network", ip: "192.168.100.12", virtualbox__hostonly: true
    ws.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory", "512"]
        # vb.gui = true
    end
  end
  # Chef node config
  config.vm.define "chefnode" do |node|
    node.vm.box = BOX
    node.vm.hostname = 'chefnode.abcd.xyz'
    node.vm.network "private_network", ip: "192.168.100.11", virtualbox__hostonly: true
    node.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory", "512"]
        # vb.gui = true
    end
  end
    # Chef node config ends here
end
