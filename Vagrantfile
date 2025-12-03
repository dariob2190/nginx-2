Vagrant.configure("2") do |config|

  config.vm.box = "debian/bullseye64"

  config.vm.hostname = "nginx"

  config.vm.network "private_network", ip: "192.168.2.100"

  config.vm.synced_folder ".", "/vagrant"
end
