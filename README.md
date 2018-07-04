# Ad-Hoc commands:

### $ ansible-inventory --graph  <br />
график инвентори файла <br />
<br />
### $ ansible -i hosts.txt all -m ping <br />
запустить пинг на все сервера <br />

### ansible all -m ping <br />
ping nodes <br />
<br />

### ansible all -m setup <br />
<br />

### ansible all -m shell -a "uptime"
command on servers  <br />
ansible <server> -m shell -a <command> <br />
ansible all -m shell -a "ls -la /home" <br />
  
### ansible-playbook roles.yml -k -i inventory -u root <br />
Run roles.yml
