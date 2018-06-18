# Ad-Hoc commands:

### ansible all -m ping <br />
ping nodes


### ansible all -m setup <br />

### ansible all -m shell -a "uptime"
command on servers  <br />
ansible <server> -m shell -a <command>

### ansible-playbook roles.yml -k -i inventory -u root <br />
Run roles.yml
