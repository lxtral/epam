# SSH, Logging, Time

## SSH

`ssh login@host`  

`vim ~/.ssh/known_hosts`  

`ssh-keygen`  
`ssh-copy-id login@host`  
Если не копирует, то проверяем права. Для id_rsa 600, для id_rsa.pub 644  

`ssh -i` для использования другого ключа  

`/etc/ssh/sshd_config` - конфигурация ssh сервера  
`PermitRootLogin no` - отключает удаленный логин под root  
`PubkeyAuthentication yes` - аутентификация по ключам  
`PasswordAuthentication yes` - аутентификация по паролю  

`.ssh/config` - можно прописать хост, логин и ключ для быстрого подключения  

## Logging

`systemd-journal` - собирает информацию  
`rsyslogd` - распределяют логи в соответствии с правилами  

`/var/log/`  

`/etc/rsyslog.conf`  
`logrotate` - настройка логирования  
`logger` - утилита  

`/etc/rsyslog.d/` - директория для пользовательских настроек rsyslog  

`journalctl` хранится в /run/log/  
`journalctl` - все события системы с момента загрузки  
`journalctl -n [число]` - [число] последних записей в журнале  
`journalctl -p [уровень_критичности]` - показать сообщения, начиная с заданного уровня критичности  
`journalctl -f` - смотреть, что добавляется в журнал в режиме реального времени  
`journalctl --since [дата]` - посмотреть события с определенной даты  
`journalctl --until` - посмотреть события до определенной даты  
`journalctl -o verbose` - детальная информация по каждой записи  
`journalctl _SYSTEMD_UNIT=sshd.service` - посмотреть события по сервисам (в данном случае SSH)  
`journalctl _PID=[id]` - посмотреть события по id пользователя  

`/etc/systemd/journald.conf` - конфигурация journalctl  
`/var/log/journal` - если создать такую папку, то журнал будет записываться в данную папку  
`journalctl -b` - показывать записи только с последнего запуска системы  

## Time

`chronyd` - отвечает за синхронизацию времени
`/etc/chrony.conf` - конфигурация со списком серверов для синхронизации времени

`timedatectl` - посмотреть данные по настройкам даты и времени  
`tzselect` - информация по часовому поясу  
`timedatectl set-timezone Europe/Moscow` - установить Московский часовой пояс  
`timedatectl set-ntp false` - отключить синхронизацию времени  
`timedatectl set-time 09:00:00` - установить время  
`chronyc sources` - синхронизирует время принудительно
