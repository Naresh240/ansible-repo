# ansible-repo

# Install docker using below command
    ansible-playbook install-docker.yml
# Create AWS Secret with plain text
  ![image](https://user-images.githubusercontent.com/58024415/107236523-cc714980-6a4b-11eb-9e44-71367cbc6417.png)
# Run mysql container by using aws secrets
    ansible-playbook mysql-aws-secrets.yml --tags create
# Remove mysql container
    ansible-playbook mysql-aws-secrets.yml --tags remove
