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

$ ansible-inventory --graph           - график инвентори файла
$ ansible -i hosts.txt all -m ping    - запустить пинг на все сервера
$ ansible all -m setup                - информация о всех серверах
$ ansible all -m shell -a "uptime"    - запуск команды bash на сервере
$ ansible all -m shell -a "ls /etc | grep group"    - операция grep работает только с командой shell
$ ansible all -m command -a "ls /etc"

$ ansible all -m copy -a "src=hello.txt dest=/home mode=777" -b      - копировать файл на все сервера под рутом(-b)
$ ansible all -m file -a "path=/home/hello.txt state=absent" -b      - удалить файл со всех серверов по указанному пути от рута

$ ansible all -m get_url -a "url=https://link.com dest=/home" -b      - скачать файл в указанную директорию от рута
_______________________________________
$ ansible all -m yum -a "name=httpd state=installed" -b         - установить httpd на все сервера от рута
$ ansible all -m service -a "name=httpd state=started enabled=yes" -b     - start and enable httpd
$ ansible all -m yum -a "name=httpd state=removed" -b         - удалить httpd на всех серверах от рута
________________________________________

$ ansible-doc -l    -  все команды

-m  - модуль
-a  - аргумент
-i  - inventory file
-b  - root privilegues
