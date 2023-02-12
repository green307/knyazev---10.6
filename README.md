# Домашнее задание к занятию 10.6 «Disaster recovery»



Задание 1
В чём разница между DRaaS, BaaS, Active-Active, Active-Passive?

Приведите ответ в свободной форме.

Ответ:

DRaaS - это услуга по аварийному восстановлению всей инфраструктуры и имеющихся данных в случае форс-мажорных ситуаций (пожар, наводнение, аварии на ЦОД, отключение электроснабжения, физическое повреждение сервера) (как понимаю данные бэкапятся в облако и от туда восстанавливаются, переносит сервер в облако и позволяет конторе бесперебойно продолжать работать)

BaaS - Резервное копирование данных в облако

Active-Active - клиентские ПК подключаются к балансировщику нагрузки, который распределяет ресурсы между несколькими активными серверами.

Active-Passive - клиентские ПК подключаются к главному серверу, который полностью управляет ресурсами. Резервный сервер находится в режиме ожидания и активируется только в случае сбоя главного сервера.




Задание 2

Компании нужно составить план восстановления в случае Disaster recovery. Сервер состоит из системного диска и диска с данными. Требуется копировать два логических диска на один физический:

системный диск (C:) (20 гигабайт);
диск с данными (D:) (256 гигабайт).
В требованиях говорится:

данные критичны в течение 24 часов после аварии;
сеть критична к большим потокам данных в рабочее время;
рабочее время с 9.00 до 18.00, пять дней (понедельник – пятница);
план резервирования должен быть реализован для диска C и для диска D. В случае Linux-систем /dev/sda1, /dev/sda4 или /dev/sdb1-данные;
считается, что для этой задачи может быть: 1) поставлен второй сервер или 2) выбрана облачная инфраструктура с определённой услугой;
компания готова платить за 10 терабайт места как в одном, так и в другом случае.
Приведите ответ в форме плана востановления с выбранным механизмом и получившейся топологией.

Ответ:

Поступил бы следующим образом, снимал бы бэкапы дисков с помощью акроникса каждый день после 20:00, данные бы полностью обнавлялись в течении месяца (данные которые хранятся больше месяца будут перезаписанны), организовал бы это все следующим образом либо поставил второй сервер на котором стояли бы диски общим обьемом 10тр. и с помощью акроникса делал бы бэкапы либо приобрел бы услугу облачного резервирования данных у того же к примеру Акроникса выбрал из того что было бы выгодней в финансовом плане. В случии какой либо чрезвучайной ситуации всегда можно востановится на день раньше, либо перенести сервак в облако и продолжать работу сервера.
