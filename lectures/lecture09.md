# Accessing Linux File Systems

## Identifying File Systems and Devices

`inodes` - индексные узлы с дополнительной информацией, описывающей файл или директорию  
`df` - показывает точки монтирования  
`df -i` - показывает inodes  
`du` - показывает дисковое пространство  

## Making Links Between Files

`ln BASICFILE HARDLINKFILE` - создание жесткой ссылки  
`ln -s BASICFILE HARDLINKFILE` - создание мягкой ссылки  

## Locating Files on the System

`yum install mlocate`  
`updatedb` - обновить базу файлов и директорий  
`locate passwd` - найдет все файлы и директории, содержащие passwd  в имени  
`locate -i messages` - найдет без учета регистра  

`find / -name passwd` - поиск по имени, начиная с корня  
`find / -iname passwd` - без учета регистра  
`find -user root` - поиск файлов, владельцем которых является пользователь  
`find -gid 1000` - поиск  
`find /home -perm 775` - поиск файлов или папок с определенными разрешениями  
`find -size 1M` - поиск файлов определенного размера  
`find / -mmin 120` - поиск файлов, которые созданы 120 минут назад  

`-type`
`f` - regular file  
`d` - directory  
`l` - soft link  
`b` - block device  

`find /etc -type d` - найдет все директории в etc
