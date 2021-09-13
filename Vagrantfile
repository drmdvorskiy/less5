Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
        v.memory = 1024
        v.cpus = 1
  end

  config.vm.provision "file", source: "key/id_rsa.pub", destination: "/home/vagrant/.ssh/id_rsa.pub"
  config.vm.provision "shell", inline: <<-SHELL
    cat /home/vagrant/.ssh/id_rsa.pub >> /home/vagrant/.ssh/authorized_keys
  SHELL

  config.vm.define "fe1" do |fe1|
    fe1.vm.box = "ubuntu/focal64"
    fe1.vm.hostname = "fe1"
    fe1.vm.network "private_network", ip: "192.168.4.2", hostname: true
    fe1.vm.network "private_network", ip: "192.168.6.2", hostname: true
    fe1.vm.synced_folder ".", "/vagrant", disabled: true
  end

  config.vm.define "fe2" do |fe2|
    fe2.vm.box = "ubuntu/focal64"
    fe2.vm.hostname = "f2"
    fe2.vm.network "private_network", ip: "192.168.4.3", hostname: true
    fe2.vm.network "private_network", ip: "192.168.6.3", hostname: true
    fe2.vm.synced_folder ".", "/vagrant", disabled: true
  end

  config.vm.define "web1" do |web1|
    web1.vm.box = "ubuntu/focal64"
    web1.vm.hostname = "web1"
    web1.vm.network "private_network", ip: "192.168.6.4", hostname: true
    web1.vm.synced_folder ".", "/vagrant", disabled: true
  end

  config.vm.define "web2" do |web2|
    web2.vm.box = "ubuntu/focal64"
    web2.vm.hostname = "web2"
    web2.vm.network "private_network", ip: "192.168.6.5", hostname: true
    web2.vm.synced_folder ".", "/vagrant", disabled: true
  end

  config.vm.define "web3" do |web3|
    web3.vm.box = "ubuntu/focal64"
    web3.vm.hostname = "web3"
    web3.vm.network "private_network", ip: "192.168.6.6", hostname: true
    web3.vm.synced_folder ".", "/vagrant", disabled: true
  end

  config.vm.define "db" do |db|
    db.vm.box = "ubuntu/focal64"
    db.vm.hostname = "db"
    db.vm.network "private_network", ip: "192.168.6.7", hostname: true
    db.vm.synced_folder ".", "/vagrant", disabled: true
  end
end
