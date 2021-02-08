# ansible-repo

# Create vault password for file
    ansible-vault encrypt mysql_pass.yml
# Run playbook
    ansible-playbook mysql.yml --tags=create --ask-vault-password
