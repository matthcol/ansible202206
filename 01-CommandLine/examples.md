# Exemples de commande ansible en ligne de commande

## 1ères connexions avec le module ping

### avec warning sur interprète python:
- ssh avec user courant et mot de passe

ansible -i hosts -k -m ping servers

- ssh avec user et mot de passe

ansible -i hosts -u kali -k -m ping servers

- ssh avec user/mot de passe puis en passant sudo avec mot de passe

ansible -i hosts -u kali -k -b --become_method sudo -K -m ping servers

- ssh avec user/mot de passe puis en passant sudo sans mot de passe

ansible -i hosts -u kali -k -b --become_method sudo -m ping servers

- ssh avec user/mot de passe puis en passant root avec mot de passe

ansible -i hosts -u kali -k -b --become_user root -K -m ping servers

- ssh avec user/key puis en passant sudo sans mot de passe

ansible -i hosts -u kali  -b --become_method sudo -m ping servers

### en donnant l'interprète en variable en ligne de commande :

ansible -e ansible_python_interpreter=/usr/bin/python -i hosts -k -m ping servers

### en donnant l'interprète dans l'inventaire :
ansible -i hostsv -k -m ping servers

### inventaire avec 2 groupes de serveurs :
ansible -i hostsv2 -k -m ping dbservers
ansible -i hostsv2 -k -m ping apiservers
ansible -i hostsv2 -k -m ping all

## module file :

https://docs.ansible.com/ansible/latest/collections/ansible/builtin/file_module.html

NB: création et suppression sont récurisives

- création d'une arborescence en précisant propriétaire et droits

ansible -u kali -i hostsv2 -b --become-method sudo -m file -a "path=/opt/application/v1/bin state=direct
ory owner=kali group=kali mode=0750" apiservers

- suppression d'une arborescence
ansible -u kali -i hostsv2 -b --become-method sudo -m file -a "path=/opt/application state=absent" apise
rvers


