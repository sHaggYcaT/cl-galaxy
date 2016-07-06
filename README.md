In first step, please run command

ANSIBLE_CONFIG=ansible.cfg  ansible-galaxy install -r requirements.yml

In second step, please run playbook using command:

ANSIBLE_CONFIG=ansible.cfg  ansible-playbook -u root -vvvvv -i hosts playbook_stadalone.yml


