# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # I use precise64 sorry!
  config.vm.box = "precise64"
  config.vm.network :forwarded_port, guest: 8983, host: 8983
  config.vm.network :forwarded_port, guest: 2181, host: 2181
  config.vm.network :forwarded_port, guest: 8080, host: 8080

  config.vm.synced_folder ".", "/etc/puppet/modules/solr"

  config.vm.provision :puppet do |puppet|
     puppet.manifests_path  = "."
     puppet.manifest_file  = "example.pp"
     puppet.options = ['--verbose']
  end

end
