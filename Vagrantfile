#Author : Jagadish Rao
#Objective: Setup a Vagrant Configration Management Development Environment
# Vagrantfile to provision a node and setup ansible


VAGRANTFILE_API_VERSION = "2"

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.define 'node-01' do |node1|
    node1.vm.network "private_network", ip: "192.168.9.9"

    node1.vm.provision "ansible" do |ansible|
      ansible.playbook       = "ansible/main.yml"
      ansible.verbose        = true
      ansible.limit          = "all" # or only "nodes" group, etc.
      ansible.inventory_path = "ansible/hosts"
    end
  end

end
