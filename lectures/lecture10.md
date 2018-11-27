## File System, Mount

`df -h` - свободное дисковое пространство  
`fdisk -l` - список устройств и их тип  
`blkid /dev/sda` - узнать тип загрузочной таблицы  

`fdisk /dev/sdb` - утилита для настройки нового диска (после добавления он получил имя sdb)  
`partprobe` - перечитать таблицу разметки дисковых пространств  

`mount` - показывает все точки монтирования  
`mkfs -t ext4 /dev/sdb1` - форматирование созданного раздела  
`mkdir /archive`  
`mount /dev/sdb1 /archive` - примонтировали sdb1 к созданной папке archive  

`vim /etc/fstab` - конфиг, чтобы созданные разделы монтировались при загрузке  
`mount -a` - монтирует все, что указано в fstab (проверяем перед перезагрузкой, чтобы всё правильно монтировалось и не получить проблем при загрузке)  

## LVM

Physical Volume (PV) -> Volume Group (VG) -> Logical Volume (LV)  

`disk /dev/sdb`  
Выбираем тип `8e (Linux LVM)`  
`partprobe`  
`pvcreate /dev/sdb2` - создание Physical Volume (PV)  
`vgcreate VGNAME /dev/sdb2` - создание группы из PV sdb2  
`lvcreate -n logicalvolume1 -L 200M lec9` - создаем LV с именем logicalvolume1 размером 200 МБ в VG lec9  
`mkfs -t xfs /dev/mapper/lec9-logicalvolume1` - форматируем созданный LV  
`mkdir /logicalvolume1`  
`mount /dev/mapper/lec9-logicalvolume1 /logicalvolume1`
