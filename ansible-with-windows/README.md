# Run ansible playbook from windows

## Pre-Requisites:

1. python
2. pip
3. Ansible
4. Docker desktop

## Install Ansible on windows

Open windows Power shell, run below command to install Ansible

```bash
pip install ansible
```

## Establish SSH between windows machine to Linux machine

1. Generate Public and Private keys

```bash
ssh-keygen                      # Run this command on cmd tool
```

2. Get public key from windows server

```bash
cat ~/.ssh/id_rsa.pub           # Run this on windows powershell
```

3. Copy public key to remote server for specific user

```bash
vi ~/.ssh/authorized_keys
```

## Create inventory file with below content

```bash
# file name as inventory

# content
[remote-server]
<remoteserver-IP> ansible_user=<remote-username> ansible_ssh_private_key_file=~/.ssh/id_rsa ansible_python_interpreter=/usr/bin/python3
```

## Check connectivity from windows to linux

```bash
docker run --rm -it -v "<gitrepo-clone-path>/ansible-repo/ansible-with-windows:/ansible" -v "C:/Users/<username>/.ssh:/root/.ssh" -w /ansible alpine/ansible:2.18.6 sh -c "chmod 600 /root/.ssh/id_rsa && ansible -i inventory -m ping remote-server"
```

## Run Playbooks to setup configuration on remote-server

```bash
docker run --rm -it -v "<gitrepo-clone-path>/ansible-repo/ansible-with-windows:/ansible" -v "C:/Users/<username>/.ssh:/root/.ssh" -w /ansible alpine/ansible:2.18.6 sh -c "chmod 600 /root/.ssh/id_rsa && ansible-playbook playbook.yaml -i inventory"

docker run --rm -it -v "<gitrepo-clone-path>/ansible-repo/ansible-with-windows:/ansible" -v "C:/Users/<username>/.ssh:/root/.ssh" -w /ansible alpine/ansible:2.18.6 sh -c "chmod 600 /root/.ssh/id_rsa && ansible-playbook node-exporter.yaml -i inventory"
```

