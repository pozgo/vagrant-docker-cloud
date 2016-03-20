VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "pozgo/centos7"
  config.vm.define vm_name = "docker-cloud-node"
  ip = "192.168.1.30"
  # Edit bridge to match your own networking name-space (i.e. eth0)
  config.vm.network "public_network", ip: ip, bridge: 'en0: Ethernet'
  config.vm.provider "virtualbox" do |v|
        v.memory = 4096
        v.cpus = 1
  end
  # Run ansible provisioning
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "provision.yml"
  end
end