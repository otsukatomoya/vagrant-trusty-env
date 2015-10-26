Vagrant.configure(2) do |config|

  config.vm.box = "trusty"
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.synced_folder '../../develop', '/home/vagrant/develop', type: 'nfs'

  config.vm.provider 'virtualbox' do |v|
    v.memory = 2048
    v.cpus = 2
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "./provision/site.yml"
    ansible.host_key_checking = false
  end
end
