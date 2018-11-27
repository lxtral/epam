## Managing Users And Groups

### Users

`useradd` - create users  
`usermod` - modifies existing users  
`userdel` - deletes users  
`id` - displays user information  
`passwd` - sets passwords  

### Groups

`groupadd` - creates groups  
`groupmod` - modifies existing groups  
`groupdel` - deletes a group  
`usermod` - alters group membership  

### Managing User Passwords

`change` - command that helps to implement a password-aging policy  
`/etc/group` - список групп  
  
`ps au` - показывает запущенные процессы  

### Переменные среды

`echo $HOME`  
`echo $PATH`  
  
  
## Controlling Access To Files With Linux File System Permissions

Права делятся на 3 группы и записываются по порядку  
  
| Пользователь (u) | Группа (g) | Все остальные (o) |  
| --- | --- | --- |  
| drwx | rwx | rwx |  
  
`w` - write, запись
`r` - read, чтение
`x` - execute, выполнение
  
`ls -l` - позволяет посмотреть виды прав и к какой группе принадлежит файл  
`chmod` - управление правами для файлов и директорий  
`chmod o+w имяФайла` - устанавливаем права на запись (w) для других пользователей (o)  
`chmod o-r имяФайла` - убирает права на чтение для других пользователей  
`chown пользователь:группа файл` - изменение прав доступа  

`setuid/setgid` - специальные разрешения  
`u+s (suid)`  
`g+s (sgid)`  
`o+t (sticky)`  
Sticky Bit - запрещает удаление файлов и директорий для всех, кроме владельца и суперпользователя  
`umask` - первоначальные разрешения  

### Acces Control Lists (ACLs)  

`getfacl` - показывает настройки ACL для файла или директории  
`setfacl` - устанавливает настройки ACL  
