# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/bullseye64"

  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.provision "file", source: "~/.ssh/vagrant.pub", destination: "~/.ssh/host.pub"
  config.vm.provision "shell", inline: <<-SHELL
    cat /home/vagrant/.ssh/host.pub >> /home/vagrant/.ssh/authorized_keys
  SHELL

end
