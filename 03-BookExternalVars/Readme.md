# Ansible Playbook with external vars

https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html

## Execute playbook with variable default values

ansible-playbook -i hostsv2 -u kali book.yml

## Execute playbook overwriting default values (-e opt)
NB: alt. you can generate automatically var files before CD stage

ansible-playbook -i hostsv2 -u kali -e "appli_version=v3 db_package=mariadb-server-10.6 db_service=mariadb" book.yml
