# ansible-repo

# Install harshicorp-vault using shell script
    sh hashicorp-vault.sh
# Open port 8200 and check vault in UI
  http://34.229.137.177:8200/
  
  Give 5 and 3 for creating account, will get keys... These keys will be useful for login and get as shown below
  
  ![image](https://user-images.githubusercontent.com/58024415/107338827-03923a00-6ae2-11eb-952f-ce4b0f560b96.png)
  
  
# Create secret here for mysql root password
  Click on "Enable New Engine"
  
  ![image](https://user-images.githubusercontent.com/58024415/107339176-62f04a00-6ae2-11eb-90df-4d3a5ab82b83.png)
  
  Click on "Next"
  
  ![image](https://user-images.githubusercontent.com/58024415/107339211-6be11b80-6ae2-11eb-8f40-5a65d5352d32.png)
  
  Click on "Enable Engine"
  
  ![image](https://user-images.githubusercontent.com/58024415/107339235-78657400-6ae2-11eb-8bf4-00d70416b15e.png)
  
  Click on "Save"
  
  ![image](https://user-images.githubusercontent.com/58024415/107339273-83200900-6ae2-11eb-9c8e-c18e97719195.png)

# Install docker with ansible playbook
    ansible-playbook install-docker.yml
# Run mysql as a container using ansible playbook
    ansible-playbook mysql.yml --tags=create
# Remove Mysql container using ansible playbook
    ansible-playbook mysql.yml --tags=remove
