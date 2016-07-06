In first step, please run command:

ANSIBLE_CONFIG=ansible.cfg  ansible-galaxy install -r requirements.yml

This command deploy all required roles from repos.

In second step, please run playbook using command:

ANSIBLE_CONFIG=ansible.cfg ansible-playbook -u root -vvvvv -i hosts playbook_stadalone.yml --ask-vault-pass

Vault password in this test enviroment is 111 (three 1)


Known bugs:

####1 nginx handler in wordpress role doesn't work (to install wordpress, please reload nginx manually)

####2 mysql role from Galaxy require sql file to import in DB, if you want to create db.  
####You'll see error:
fatal: [85.10.201.52]: FAILED! => {"failed": true, "msg": "The conditional check 'item.changed and item.item.import_file' failed. The error was: error while evaluating conditional (item.changed and item.item.import_file): 'dict object' has no attribute 'import_file'\n\nThe error appears to have been in '/home/shaggycat/ownCloud/Documents/immigration/codecl/cl/2/cl-galaxy/roles/mjanser.mysql/tasks/databases.yml': line 10, column 3, but may\nbe elsewhere in the file depending on the exact syntax problem.\n\nThe offending line appears to be:\n\n\n- name: import data from backup into databases\n  ^ here\n"}
####ansible playbook failed, just run it again

####3 images by uwsgi server does not serve. It works, if you run the app using command: 
python2.7 manage.py runserver 0.0.0.0:8000

## TODO

####1 complete playbook_move.yml - add promt input, and if/else case to switch to first or second server, andd lock file

####2 fix bugs

