# LDAP. Централизованная авторизация и аутентификация

Запуск стенда:

```
vagrant up
```

Для создания пользователя необходимо выполнить команду:

```
vagrant ssh ipaserver -c 'echo password | kinit admin && ipa user-add --first="User" --last="User" --cn="User User" --password user --shell="/bin/bash"'
vagrant ssh client
su -l user
```

