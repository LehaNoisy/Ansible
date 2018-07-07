# Ad-Hoc commands:
  
<br />

**$ ansible-inventory --graph**       - график инвентори файла <br />
**$ ansible -i hosts.txt all -m ping**    - запустить пинг на все сервера <br />
**$ ansible all -m setup**                - информация о всех серверах <br />
**$ ansible all -m shell -a "uptime"**    - запуск команды bash на сервере <br />
**$ ansible all -m shell -a "ls /etc | grep group"**    - операция grep работает только с командой shell <br />
**$ ansible all -m command -a "ls /etc" <br />**

**$ ansible all -m copy -a "src=hello.txt dest=/home mode=777" -b**      - копировать файл на все сервера под рутом(-b) <br />
**$ ansible all -m file -a "path=/home/hello.txt state=absent" -b**      - удалить файл со всех серверов по указанному пути от рута <br />

**$ ansible all -m get_url -a "url=https://link.com dest=/home" -b**      - скачать файл в указанную директорию от рута <br />
<br />
**_________________________________________________________________________** <br />
**$ ansible all -m yum -a "name=httpd state=installed" -b**         - установить httpd на все сервера от рута <br />
**$ ansible all -m service -a "name=httpd state=started enabled=yes" -b**     - start and enable httpd <br />
**$ ansible all -m yum -a "name=httpd state=removed" -b**      - удалить httpd на всех серверах от рута <br />
**__________________________________________________________________________** <br />
<br />

**$ ansible-playbook roles.yml -k -i inventory -u root**    - run roles.yml <br />

**$ ansible-doc -l**    -  все команды <br />
<br />
**__________________________________________________________________________** <br />
**-m**  - модуль <br />
**-a**  - аргумент <br />
**-i**  - inventory file <br />
**-b**  - root privilegues <br />
<br />
**Ansible variables:** <br />
**message**<br />
<br />
**debug** --> var: (переменная)<br />
debug: var=ansible_os_family<br />
<br />
**handlers** --> notify<br />
handlers:<br />
  - name: Restart Apache<br />
    service: name=httpd state=restarted<br />
<br />
**set facts** --> соединить messages<br />
set_fact: full_message="{{ message1 }} {{ message2 }}"<br />
<br />
**when** ---> условие (запускать если)<br />
when: ansible_os_family == "RedHat"<br />
<br />
**block** --> собирает операции в блоки<br />
