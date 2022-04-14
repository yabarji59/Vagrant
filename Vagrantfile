Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2010"
  config.vm.network "private_network", ip: "192.168.56.10"

  # config.vm.synced_folder "../data", "/vagrant_data"
  config.vm.synced_folder ".", "/var/www/project"

   config.vm.provider "virtualbox" do |v|
     v.name = "Devbox-Github"
     # Display the VirtualBox GUI when booting the machine
     v.gui = true

     # Customize the amount of memory on the VM:
     v.memory = "2048"
   endV

  # Enable provisioning with a shell script. Additional provisioners such as
  config.vm.provision "shell", reboot:true, inline: <<-SHELL
    echo $(whoami)
    apt-get update
    apt-get install -y g++
    sudo apt install curl -y

    apt-get install -y --no-install-recommends ubuntu-desktop

    # Mise au clavier français, passage au fuseau horaire de Paris
    sudo setup-keymap fr fr-azerty
    sudo loadkeys fr
    sudo apt-get install console-data (si besoin)
    sudo dpkg-reconfigure console-setup
    sudo loadkeys fr
    sudo dpkg-reconfigure console-data

    localectl set-locale LANG=fr_FR.utf8
    echo "Europe/Paris" | sudo tee /etc/timezone

    sudo apt-get install linux-headers-$(uname -r) open-vm-tools
    sudo vmware-config-tools.pl

    curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
	sudo apt-get install -y nodejs
        echo "node installé"
	node -v
	sudo apt-get install npm
        #npm install -g npm@8.6.0
	npm -v
	apt-get install -y build-essential

    apt-get install -y apt-transport-https ca-certificates curl software-properties-common
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -
    add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
    apt-cache policy docker-ce
    apt-get install docker-ce -y
    usermod -aG docker vagrant
    systemctl enable docker

    #vqsudo apt install cinnamon-desktop-environment

    apt-get install -y chromium-browser

	npm install express
	echo "<userName>  ALL=(ALL:ALL) ALL" | sudo tee --append /etc/sudoers

    su vagrant
    mkdir /home/vagrant/node_modules
    cd /var/www/project
    ln -s /home/vagrant/node_modules/ node_modules
  SHELL
end




https://github.com/wardviaene/docker-demo



