VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  #config.vm.customize ["modifyvm", :id, "--memory", 1024]

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end

  config.vm.provision "docker" do |d|
    d.run "scenthound/continuous-delivery",
      args: "-d -p 0.0.0.0:49153:8080"
  end
  config.vm.network :forwarded_port, host: 4567, guest: 49153
end
