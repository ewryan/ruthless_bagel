$script = <<SCRIPT

apt-get install -y software-properties-common
add-apt-repository -y ppa:ethereum/ethereum
add-apt-repository -y ppa:ethereum/ethereum-dev
apt-get update -y 
apt-get install -y ethereum solc

date > /etc/vagrant_provisioned_at

SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provider "virtualbox" do |vb|
    vb.gui = true
    vb.memory = "1024"
  end
  config.vm.provision "shell", inline: $script
end
