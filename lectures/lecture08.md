# RPM, YUM

## Attaching Systems To Subscriptions For Software Updates
 
`subscription-manager register --username=yoursusername password=yourpassword`  
`subscription-manager register --list`  
 
## YUM
 
`yum repolist` - список репозиториев  
`yum list *yum` - поиск по установленным пакетам  
`yum list installed` - список всех установленных пакетов  
`yum info PACKAGENAME` - информация об установленном пакете  
`yum search KEYWORDS` - поиск пакетов в репозиториях по имени и описанию  
`yum provides PATHNAME` - список пакетов в которых используется эта директория  
`yum update PACKAGENAME` - обновить пакет  
`yum remove PACKAGENAME` - удалить пакет  
 
`yum group list` - список доступных для установки групп пакетов  
`yum grop install 'GROUPNAME'` - установить группу пакетов  
`yum group info 'GROUPNAME'` - посмотреть список пакетов в группе  
`yum group remove 'GROUPNAME'` - удалить группу  
 
`yum history` - посмотреть историю установки пакетов и групп  
`yum history info ID` - посмотреть установленные пакеты  
`yum history undo ID` - удалить пакет или группу пакетов по id из истории  
 
`yum repolist all` - список репозиториев  
`yum install yum-utils`  
`yum-config-manager -list`  
`yum-config-manager -add-repo="REPOLINK"` - установить репозиторий  
`yum-config-manager --disable epel` - отключить репозиторий epel  
`yum-config-manager --enable epel` - подключить репозиторий epel  
`/etc/yum.repos.d`  
 
## Examining RPM Package Files
 
`rpm -q -i NAME` - информация о пакете  
`rpm -q -l NAME` - список файлов в пакете  
`rpm -q -c NAME` - список конфигурационных файлов для пакетов  
`rpm -q -d NAME` - документация для пакета  
`rpm -q --changelog` - список версионных изменений пакета  
`rpm -q --scripts NAME` - скрипт, который выполняется либо до установки пакета, либо после  
`rpm -ivh FILENAME.rpm` - установить пакет
