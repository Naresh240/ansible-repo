# ansible-tower

# Pre-Requisites:
	REDHAT OS with 2 CPU's and 8GB memory (t2.large)

# Install Ansible
	yum install wget -y
	yum -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
	yum update -y
	yum install ansible -y
# Install Tower:
	cd /opt
	wget https://releases.ansible.com/ansible-tower/setup/ansible-tower-setup-latest.tar.gz
	tar xvzf ansible-tower-setup-latest.tar.gz
	cd ansible-tower-setup-3.8.4-1
  Need to change Inventory file:
	
	admin_password='password'
	pg_password='password'
  Install:
  
	./setup.sh
# Default Credentials:
	username: admin
	Password: password