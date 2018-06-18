# Ad-Hoc commands:

### ansible all -m ping <br />
ping nodes <br />
<br />

### ansible all -m setup <br />
<br />

### ansible all -m shell -a "uptime"
command on servers  <br />
ansible <server> -m shell -a <command> <br />
  
### ansible-playbook roles.yml -k -i inventory -u root <br />
Run roles.yml
