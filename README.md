# LDAP. Централизованная авторизация и аутентификация

Запуск стенда:

```
vagrant up
```

Для создания пользователя необходимо выполнить команды:
```
vagrant ssh ipaserver -c 'echo password | kinit admin && ipa user-add --first="User" --last="User" --cn="User User" --password user --shell="/bin/bash"'
vagrant ssh client
su -l user
```

```
[root@localhost homew26]# vagrant ssh ipaserver -c 'echo password | kinit admin && ipa user-add --first="User" --last="User" --cn="User User" --password user --shell="/bin/bash"'
Password for admin@HOME.LOCAL: 
Password: 
Enter Password again to verify: 
-----------------
Added user "user"
-----------------
  User login: user
  First name: User
  Last name: User
  Full name: User User
  Display name: User User
  Initials: UU
  Home directory: /home/user
  GECOS: User User
  Login shell: /bin/bash
  Principal name: user@HOME.LOCAL
  Principal alias: user@HOME.LOCAL
  User password expiration: 20200709113319Z
  Email address: user@home.local
  UID: 1865200001
  GID: 1865200001
  Password: True
  Member of groups: ipausers
  Kerberos keys available: True
Connection to 127.0.0.1 closed.
[root@localhost homew26]# vagrant ssh client
[vagrant@client ~]$ su -l user
Password: 
Password expired. Change your password now.
Current Password: 
New password: 
Retype new password: 
Creating home directory for user.
Last failed login: Thu Jul  9 11:37:04 UTC 2020 on pts/0
[user@client ~]$ 

```

