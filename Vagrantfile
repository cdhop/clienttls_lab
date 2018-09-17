Vagrant.configure("2") do |config|

  config.vm.define "client" do |client|
    client.vm.box = "ubuntu/bionic64"
    client.vm.hostname = "client"

    client.vm.network "private_network", ip: "192.168.2.5", netmask: "255.255.255.0"

    client.vm.provision "ansible" do |ansible|
      ansible.playbook = "client.yml"
    end
  end

  config.vm.define "webserver" do |webserver|
    webserver.vm.box = "ubuntu/bionic64"
    webserver.vm.hostname = "webserver"

    webserver.vm.network "private_network", ip: "192.168.2.10", netmask: "255.255.255.0"

    webserver.vm.provision "ansible" do |ansible|
      ansible.playbook = "webserver.yml"
    end
  end
end
