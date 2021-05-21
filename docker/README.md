# Create nginx container with tags
    ansible-playbook nginx.yml --tags create
# Delete nginx container with tags
    ansible-playbook nginx.yml --tags delete
# Create MySql container with tags
    ansible-playbook mysql_tags.yml --tags create
# Delete MySql container with tags
    ansible-playbook mysql_tags.yml --tags remove
# Create MySql container with runtime variable
    ansible-playbook mysql_runtime_variable.yml -e container_state=started
# Delete MySql container with runtime variable
    ansible-playbook mysql_runtime_variable.yml -e container_state=absent
