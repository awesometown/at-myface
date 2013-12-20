Vagrant.configure("2") do |config|
  config.vm.hostname = "myface-berkshelf"
  config.vm.box = "precise64"
  config.omnibus.chef_version = :latest
  config.vm.network :private_network, ip: "33.33.33.10"
  config.vm.boot_timeout = 120
  config.berkshelf.enabled = true

  config.vm.provision :chef_solo do |chef|
    chef.json = {
      :mysql => {
        :server_root_password => 'rootpass',
        :server_debian_password => 'debpass',
        :server_repl_password => 'replpass'
      }
    }
    chef.run_list = [
      "recipe[myface::default]"
    ]
  end
end