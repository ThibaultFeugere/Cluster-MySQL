Vagrant.configure("2") do |config|
    config.vm.box = "centos/7"
    # Désactive les updates auto qui peuvent ralentir le lancement de la machine
    config.vm.box_check_update = false 
    # La ligne suivante permet de désactiver le montage d'un dossier partagé (ne marche pas tout le temps directement suivant vos OS, versions d'OS, etc.)
    config.vm.synced_folder ".", "/vagrant", disabled: true
  
    config.vm.provider "virtualbox" do |vb|
      vb.gui = true
    end
  
    # Config une première VM "mgm_node"
    config.vm.define "mgm_node" do |mgm_node|
      mgm_node.vm.network "private_network", ip: "10.0.0.11"
      mgm_node.vm.provision "shell",
        inline: "sudo hostnamectl set-hostname mgm_node"
    end
  
    # Config une  VM "sql_node"
    config.vm.define "sql_node" do |sql_node|
      sql_node.vm.network "private_network", ip: "10.0.0.12"
      sql_node.vm.provision "shell",
        inline: "sudo hostnamectl set-hostname sql_node"
    end
    # Config une  VM "sql_node2"
    config.vm.define "sql_node2" do |sql_node2|
      sql_node2.vm.network "private_network", ip: "10.0.0.13"
      sql_node2.vm.provision "shell",
        inline: "sudo hostnamectl set-hostname sql_node2"
    end
    
    # Config une  VM "data_node1"
    config.vm.define "data_node1" do |data_node1|
      data_node1.vm.network "private_network", ip: "10.0.0.21"
      data_node1.vm.provision "shell",
        inline: "sudo hostnamectl set-hostname data_node1"
    end
  
    # Config une  VM "data_node2"
    config.vm.define "data_node2" do |data_node2|
      data_node2.vm.network "private_network", ip: "10.0.0.22"
      data_node2.vm.provision "shell",
        inline: "sudo hostnamectl set-hostname data_node2"
    end
  end
  