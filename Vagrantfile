# -*- mode: ruby -*-
# vi: set ft=ruby :
required_plugins = ["vagrant-hostsupdater"]

required_plugins.each do |plugin|
  exec "vagrant plugin install #{plugin}" unless Vagrant.has_plugin? plugin
end


Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.provision "shell", path: "provision.sh"
  config.vm.network "private_network", ip: "192.168.10.100"
  config.hostsupdater.aliases = ["jenkins.local"]

end
