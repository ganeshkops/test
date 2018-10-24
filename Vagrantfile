Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", 2048]
    vb.customize ["modifyvm", :id, "--cpus", 1]
  end
  config.vm.define "node2" do |node2|
    node2.vm.hostname = "node2"
    node2.vm.network "public_network", bridge: "HostInterfaceNetworking-Intel(R) Dual Band Wireless-AC 8265", ip: "192.168.0.130"
	node2.vm.network "forward_port", host: 10250, guest: 10250
	for i in 30000..32767
		config.vm.network :forwarded_port, guest: i, host: i
	end
	
  end
  config.vm.define "node3" do |node3|
    node3.vm.hostname = "node3"
    node3.vm.network "public_network", bridge: "HostInterfaceNetworking-Intel(R) Dual Band Wireless-AC 8265", ip: "192.168.0.140"
	node3.vm.network "forward_port", host: 10250, guest: 10250
	for i in 30000..32767
		config.vm.network :forwarded_port, guest: i, host: i
	end
  end
  
end
