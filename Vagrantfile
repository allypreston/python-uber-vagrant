# -*- mode: ruby -*-
# vi: set ft=ruby :

#intall plugins needed for vagrant with fetched cookbooks
required_plugins = %w( vagrant-hostsupdater  vagrant-berkshelf )
required_plugins.each do |plugin|
    exec "vagrant plugin install #{plugin}" unless Vagrant.has_plugin? plugin
end

Vagrant.configure("2") do |config|
  config.vm.define "app" do |app|
    app.vm.box = "ubuntu/xenial64"
    app.vm.network "private_network", ip: "192.168.10.100"
    app.hostsupdater.aliases = ["development.local"]
      app.vm.synced_folder "Python-Sample-Application", "/home/ubuntu/Python-sample-application"
  end
end
