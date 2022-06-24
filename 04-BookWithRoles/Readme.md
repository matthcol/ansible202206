# Play an ansible playbook
Quelques exemple de lancement de la commande ansible-playbook

- ansible-playbook -i hosts -u kali -e book.yml
- ansible-playbook -i hosts -u kali -e "appli_version=v3" book.yml
- ansible-playbook -i hosts -u kali -t api book.yml
- ansible-playbook -i hosts -u kali -t db book.yml
- ansible-playbook -i hosts -u kali -t install book.yml
- ansible-playbook -i hosts -u kali -t learn book.yml
- ansible-playbook -i hosts -u kali -skip-tags db,api book.yml
- ansible-playbook -i hosts -u kali --start-at-task "Debug DB Content" book.yml
- ansible-playbook -i hosts --syntax-check book.yml
