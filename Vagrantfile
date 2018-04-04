# -- mode: ruby --
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  MASTER_COUNT = 3
  BOX_IMAGE = "centos/7"

  NODE_COUNT = 1
  PROJECT_NAME="k8s-ha"

  (1..MASTER_COUNT).each do |i|
    config.vm.define "master-#{i}" do |subconfig|
      subconfig.vm.box = BOX_IMAGE
      subconfig.vm.hostname = "master-#{i}"
    end

    #if i == MASTER_COUNT
      
    #end

    config.vm.provision :vai do |ansible|
      #ansible.playbook = "playbook.yml"
      #ansible.inventory_filename='vagrant_ansible_inventory'
      #ansible.verbose = "vv"
      #ansible.become = "true"
      ansible.groups = {
        "master" => ["master-1","master-2","master-3"]
      }
      ansible.inventory_dir='./'
      #ansible.config_file = "ansible.cfg"
    end
  end
end