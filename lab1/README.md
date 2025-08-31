Лабораторная работа. Базовая настройка коммутатора 

	Топология
![] (https://vscode.dev/github/Vadim716670/labs/blob/main/010.JPG "Заголовок1")

# Таблица адресации

| Устройство | Интерфейс | IP-адрес / префикс |
| --- | --- | --- |
| S1  | VLAN 1 | 192.168.1.2 /24 |

| PC-A | NIC | 192.168.1.10 /24 |

######Задачи



Проверка конфигурации коммутатора по умолчанию
Создание сети и настройка основных параметров устройства
•	Настройте базовые параметры коммутатора.


•	Настройте IP-адрес для ПК.
 Проверка сетевых подключений


•	Отобразите конфигурацию устройства.


•	Протестируйте сквозное соединение, отправив эхо-запрос.


•	Протестируйте возможности удаленного управления с помощью Telnet.



####Подключимся консольным кабелем к коммутатором и настроим основные параметры



[]
(https://vscode.dev/github/Vadim716670/labs/blob/main/01.JPG "Заголовок2")

line con 0
 password 7 00071A150754
 logging synchronous
 login

line vty 0 4

 password 7 121A0C041104
 login

line vty 5 15

 password 7 121A0C041104
 login




no ip domain-lookup

hostname S1

service password-encryption

enable secret class

banner motd #
Unauthorized access is strictly prohibited. #



interface Vlan1

 ip address 192.168.1.2 255.255.255.0


ip default-gateway 192.168.1.1



####Настроим ip адрес на хосте



[] (https://vscode.dev/github/Vadim716670/labs/blob/main/101.JPG "Заголовок3")




