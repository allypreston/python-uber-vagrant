# -*- mode: ruby -*-
# vi: set ft=ruby :

#intall plugins needed for vagrant with fetched cookbooks
required_plugins = %w( vagrant-hostsupdater  vagrant-berkshelf )
required_plugins.each do |plugin|
    exec "vagrant plugin install #{plugin}" unless Vagrant.has_plugin? plugin
end


Vagrant.configure("2") do |config|
  config.vm.define "development" do |development|
    development.vm.box = "ubuntu/xenial64"
    development.vm.network "private_network", ip: "192.168.10.100"
    development.hostsupdater.aliases = ["development.local"]
    development.vm.synced_folder "Python-Sample-Application", "/home/ubuntu/Python-sample-application"
    development.vm.provision "chef_solo" do |chef|
      chef.arguments = "--chef-license accept"
      chef.add_recipe "development::default"
      chef.add_recipe "nginx::default"
    end
  end
end
