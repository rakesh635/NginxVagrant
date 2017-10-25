ENV['VBOX_INSTALL_PATH'] = ENV['VBOX_MSI_INSTALL_PATH']
Vagrant.configure("2") do |config|
	config.vm.define "Centos7" do |node|
		node.vm.box = "centos/7"
		#node.vm.provider "virtualbox" do |vb|
		#	vb.gui = false
		#end
		#node.vm.synced_folder ".", "/home/vagrant/sync", type: "virtualbox" 
		node.vm.provision "docker", type: "shell", run: "always", inline: <<-SHELL
			sudo su
			yum install -y yum-utils device-mapper-persistent-data lvm2
			yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
			yum install -y docker-ce
			systemctl start docker
			docker ps -a
			yum install -y epel-release
			yum install -y python-pip
			pip install docker-compose
			yum upgrade -y python*
			docker-compose --version
			#if [ -d NginxDocker ] ; then
			#	rm -rf NginxDocker
			#fi
			yum install -y git
			git clone https://github.com/rakesh635/NginxDocker.git
			cd NginxDocker
			#docker stop $(docker ps -a -q)
			#docker rm $(docker ps -a -q)
			docker build -t nginx .
			docker run -d -p 80:80 --name nginxcontainer nginx
			echo "\n127.0.0.1 myfirstpage.com  mysecondpage.com  mythirdpage.com " >> /etc/hosts
		SHELL
	end
end
