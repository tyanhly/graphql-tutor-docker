
Vagrant.configure("2") do |config|

    config.vm.box = "ubuntu/xenial64"
    config.vm.network "private_network", ip: "192.10.10.10"


    #config.vm.provider :virtualbox do |v|
    #    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    #    v.customize ["modifyvm", :id, "--memory", 4048]
    #    v.customize ["modifyvm", :id, "--cpus", 2]
    #    v.customize ["setextradata", :id, "--VBoxInternal2/SharedFoldersEnableSymlinksCreate/v-root", "1"]
    #end
    config.vm.synced_folder ".", "/app", mount_options: ["dmode=777", "fmode=777"],owner: 1000, group: 1000

    config.vm.provision "shell", inline: <<-SHELL
        curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
        add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
        apt-get update
        apt-get install -y docker-ce
        curl -o /usr/local/bin/docker-compose -L "https://github.com/docker/compose/releases/download/1.15.0/docker-compose-$(uname -s)-$(uname -m)"

        usermod -aG docker vagrant
        chmod +x /usr/local/bin/docker-compose

        echo 'cd /app' >> /home/vagrant/.bashrc
    SHELL
end
