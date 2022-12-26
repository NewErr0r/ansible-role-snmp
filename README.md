<h1 align='center'>Автоматизация развёртывания SNMP V2 и V3  на ОС: CentOS, Debian, VyOS </h1>

<p>
    <strong>Шаг 1.</strong> Создание playbook для запуска роли
</p>
<p><i>Пример:</i></p>

    ---
    - name: Deploy SNMP
      hosts: all 
      become: true 

      roles: 
        - ansible-role-snmpv3
        
<p>
    <strong>Шаг 2.</strong> Склонировать роль в дирректорию с playbook:
</p>

  <pre>git clone https://github.com/NewErr0r/ansible-role-snmpv3.git</pre>

<p>

 <strong>Шаг 3.</strong> Запустить скрипт инициализирующий необходимые переменные для настройки SNMP V2:
</p>
 
 <pre>./ansible-role-moodle/snmp_v2.variables</pre>
 <i>1. Задать community string</i><br>
 <i>2. Задать location</i><br>
 <i>3. Задать cantoct </i><br>
 
  <strong>Шаг 4.</strong> Запустить скрипт инициализирующий необходимые переменные для настройки SNMP V3:
</p>
 
 <pre>./ansible-role-moodle/snmp_v3.variables</pre>
 <i>1. Задать метод RO или RW </i><br>
 <i>2. Задать пароль аутентификации </i><br>
 <i>3. Задать приватный ключ </i><br>
 <i>4. Задать имя пользователя snmp </i><br>
 <i>5. Задать алгоритм хеш-функции MD5 или SHA </i><br>
 <i>6. Задать алгоритм шифрования DES или AES </i><br>
 
<strong>Шаг 4.1</strong> Для настройки SNMP V3 на VyOS запустить скрипт инициализирующий необходимые переменные :
 
  <pre>./ansible-role-moodle/vyos_snmp.variables</pre>
  <i>1. Задать location</i><br>
  <i>2. Задать метод RO или RW </i><br>
  <i>3. Задать пароль аутентификации </i><br>
  <i>4. Задать приватный ключ </i><br>
  <i>5. Задать имя пользователя snmp </i><br>
 
 <p>
    <strong>Шаг 5.</strong> Запустить playbook для развёртывания SNMP V2 V3:
</p>
  
  <pre>ansible-playbook -i inventory playbook.yaml</pre>
 
 
 
 
 
 
 
 
 
 
 
