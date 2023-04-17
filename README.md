# R2OnlineServer
## Установка
#### Шаг 1: Установка свободно распространяемых пакетов, включающих в себя компоненты и библиотеки DLL, необходимые для запуска различных программ написанных на языке программирования С++ при помощи Visual Studio.
Распаковать Visual-C-Runtimes-All-in-One-Jul-2021.rar и нажать install_all.bat
#### Шаг 2: Установка SQLEXPR_x64_RUS.
Нажать SETUP.exe и выбрать "Новая установка изолированного экземпляра SQL Server или добавление компонентов к существующей установке.

Прочитать лицензионное соглашение и в чекбоксе "Я принимаю условия лицензионного соглашения" кликнуть и убедиться, что галочка проставилась и нажать "Далее".

На данном этапе может возникнуть ошибка напротив правила "Перезагрузите компьютер", для её решения необходимо перезагрузить компьютер.

Если перезагрузка не потребовалась, то нажимаем "Далее" и в выборе компонентов удостоверяемся, что все компоненты выбраны и только после этого нажимаем "Далее".
![1](https://user-images.githubusercontent.com/122387884/225039691-82ef76b9-ea64-4154-8bf9-fd0a6b0bb413.png)

В настройках экземпляра у "Именованный экземпляр" должно быть **SQLExpress** и "Идентификатор экземпляра" должен быть **SQLEXPRESS**, удостоверившись в этом нажимаем "Далее".

![2](https://user-images.githubusercontent.com/122387884/225039743-075ea4d7-3db3-4bc8-b86e-500abfc4a63f.png)

В конфигурации сервера ничего не меняем, нажимаем "Далее".

![3](https://user-images.githubusercontent.com/122387884/225039781-f9393d04-86f8-40bf-b85f-3dc063f137f3.png)

В настройках компонента Database Engine выбираем "Режим проверки подлинности" - "Смешанный режим" и указываем пароль для учетной записи системного администратора SQL Server (sa), например: **Uewy837123ejwhewe** и нажимаем "Далее" и дожидаемся завершения хода выполнения установки.

![4](https://user-images.githubusercontent.com/122387884/225039890-0762cacd-f97d-4920-b13c-b409842d4660.png)

![5](https://user-images.githubusercontent.com/122387884/225039923-4edae038-d67c-4986-b512-d6d91729b9b8.png)

#### Шаг 3: SQLManagementStudio_x64_RUS.
Нажать SETUP.exe и выбрать "Новая установка изолированного экземпляра SQL Server или добавление компонентов к существующей установке.

Нажать "Далее".

В типе установки выбрать "Добавить компоненты в существующий экземпляр SQL Server 2014" и удостовериться, что выбрано **SQLEXPRESS** и нажать "Далее".

![6](https://user-images.githubusercontent.com/122387884/225040028-6f1516b8-b8fc-428b-9d51-2ab1b20fb940.png)

В выборе компонентов нажать "Выделить все" и нажать "Далее" 

![7](https://user-images.githubusercontent.com/122387884/225040122-a76a7a75-4c2f-47be-8602-4c0c6366403c.png)

Дождаться завершения хода выполнения установки.
#### Шаг 4: Настройка SQL Server.
В Панели "Пуск" открываем "Диспетчер конфигурации SQL Server 2014".

![8](https://user-images.githubusercontent.com/122387884/225040217-0a8c1c7e-d60e-4dee-8012-9c474665544a.png)

В разделе "Сетевая конфигурация SQL Server" выбираем "Протоколы для SQLEXPRESS" и выбираем протокол "TCP/IP" и двойным нажатием открываем его свойства и выбираем в "Общие" - "Включено" - меняем на "Да" и переходим в Ip-адреса и во всех "IP-адрес" ставим значение **IPv4** адреса сервера и в **TCP-порт** значение **1433** и нажимаем "Применить".

![9](https://user-images.githubusercontent.com/122387884/225040309-ce00f19e-2dc6-48ab-ad2f-2ee9c72cfdd2.png)

![10](https://user-images.githubusercontent.com/122387884/225041057-92f88871-bec1-41e3-8035-dc32e965a353.png)

![11](https://user-images.githubusercontent.com/122387884/225041128-e7bec0ea-6acb-4ba7-ba45-cbcd03b688c9.png)

Переходим в "Службы SQL Server" и для "SQL Server (SQLEXPRESS)" осуществляем перезапуск.

![12](https://user-images.githubusercontent.com/122387884/225041369-5945fc47-f5d6-4bc9-89f0-5b3a5552bf80.png)

#### Шаг 5: Подключение к SQL серверу.
В Панели "Пуск" открываем SQL Server 2014 Management Studio и нажимаем "Соединить".
![1](https://user-images.githubusercontent.com/122387884/232353438-cb1cbc7a-10f2-4e17-8c52-6f6145301de5.png)


#### Шаг 6: Восстановление баз данных.
Нажимаем правой кнопкой мыши на "Базы данных" и выбираем "Восстановить базу данных".
![2](https://user-images.githubusercontent.com/122387884/232353452-a2bfc584-2b21-4ed8-9ee4-da39b4b02c5c.png)


В источнике выбираем "Устройство" и нажимаем на три точки, нажимаем добавить и выбираем носители резервных копиий(поочерёдно) следующих файлов: **FNLAccount.bak**, **FNLBilling.bak**, **FNLGame2157.bak**, **FNLog.bak**, **FNLParm.bak** и нажимаем "ОК". 
![3](https://user-images.githubusercontent.com/122387884/232353469-ac0113c5-a53a-4a4e-81ba-b9b40f6ead57.png)


#### Шаг 7: Настройка базы.
Открываем базу **FNLParm**, выбираем таблицы и находим **dbo.TblParmSvr** - нажимаем правой кнопкой мыши и выбираем "Изменить первые 200 строк" и для **True** устанавливаем значение **IPv4** адреса.
![image](https://user-images.githubusercontent.com/122387884/232353575-48f423df-8fb0-4ec4-96b7-863de491c191.png)


#### Шаг 8: Добавление информации в реестр Windows.
Нажимаем на .reg файл, чтобы информация добавилась в реестр(Путь к файлам). При желании можно изменить hex код файла, если у Вас будет находиться сервер в другой директории.


#### Шаг 9: Установка языка поддержки сервера.
Панель управления -> Язык и региональные стандарты -> Дополнительно -> Изменить язык системы -> Китайский (упрощенное письмо, Китай). 
![image](https://user-images.githubusercontent.com/122387884/232353937-b2f1a5e2-9da8-4fca-a05b-8159e9acbd31.png)

Перезагрузиться.

#### Шаг 10: Настройка служб сервера.
Переходим в папку D:\r2server\Lib и поочередно запускаем c.bat , f.bat, m.bat от имени администратора.

#### Шаг 11: Редактирование конфигурационных файлов.
Теперь отредактируем все текстовые и конфигурационные файлы сервера \r2server\Auth\DPurpleAuthChanneling\
Меняем ip в PurpleChannelingAuthSvrConfig.xml 

В папке D:\r2server\Data\
Меняем ip и другие данные в Account.dsn, Billing.dsn, Game.dsn, Log.dsn, Parm.dsn чтобы получилось вида

```
[ODBC]
DRIVER=SQL Server
UID=sa
PWD=Uewy837123ejwhewe
Address=127.0.0.1,1433
Network=DBMSSOCN
DATABASE=FNLAccount
APP=Microsoft Data Access Components
SERVER=127.0.0.1
```

Также необходимо изменить ip в D:\r2server\Lib ： C_R2.xml, IpCheck_Dbgw.xml, PurpleAuthForSvrConfig.xml, server.xml

#### Шаг 12: Реверсинг.
В папке lib ищем PorteAuthForSvr_x64.dll и меняем через PorteAuthForSvr_x64_patcher.exe ip в нём на наш.
Начиная с адреса 00028ad0
![image](https://user-images.githubusercontent.com/122387884/232355950-d583dc2a-1459-4c86-9cd7-28c59cb71853.png)

![image](https://user-images.githubusercontent.com/122387884/232356033-e2ad2799-5b12-4217-98d7-d24fa8622c89.png)

#### Шаг 13: Запуск сервера.
Запускаем файлы
D:\r2server\Auth\PurpleAuthBack\PorteAuthBackSvr.exe
D:\r2server\Auth\DPurpleAuthChanneling\PurpleChannelingAuthSvr.exe

Открываем командную строку от имени администратора и пишем поочередно

![image](https://user-images.githubusercontent.com/122387884/232359356-56bb81fe-e32e-4fee-8506-c494062c453b.png)

и net start Fieldw
