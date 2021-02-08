# ansible-repo

# Create vault password for file
    ansible-vault encrypt mysql_pass.yml
# Run playbook
    ansible-playbook mysql.yml --tags=create --ask-vault-password
    ansible-playbook mysql.yml --tags=remove --ask-vault-password
# With vault password file:
    ansible-playbook mysql.yml --tags=create --vault-password-file password.yml
    ansible-playbook mysql.yml --tags=remove --vault-password-file password.yml
