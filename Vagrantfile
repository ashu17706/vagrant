Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"

  config.vm.box_check_update = false

  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.network "private_network", ip: "192.168.1.200"

  config.vm.synced_folder "../web", "/vagrant_data", create: true

  config.vm.provider "virtualbox" do |v|
    v.name = "serverVM"
    v.memory = 1024
    v.cpus = 2
  end

  config.vm.provision "shell", inline: <<-SHELL
     sudo apt-get update
     sudo apt-get install git
   SHELL

end
