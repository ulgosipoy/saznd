# Сбор и аналитическая обработка информации о сетевом трафике

## Цель работы

1. Развить практические навыки использования современного стека инструментов сбора и аналитической обработки информации о сетвом трафике
2. Освоить базовые подходы блокировки нежелательного сетевого трафика
3. Закрепить знания о современных сетевых протоколах прикладного уровня

## ️Исходные данные

1. Ноутбук с Windows 10
2. Virtual Box с ОС kali-linux-2023.1-virtualbox-amd64.7z
3. Сетевой анализатор - Wireshark
4. Python 3.11.2

## ️Задание

1. Собрать сетевой трафик (объемом не менее 100 Мб)
2. Выделить метаинформацию сетевого трафика с помощью утилиты Zeek
3. Собрать данные об источниках нежелательного трафика, например – https://github.com/StevenBlack
4. Написать программу на любом удобном языке (python, bash, R …), которая подсчитывает процент нежелательного трафика в собранном на этапе 1.
5. Оформить отчет в соответствии с шаблоном

## Содержание ЛР

### Шаг 1

Собрать сетевой трафик (объемом не менее 100 Мб)

1. Воспользоваться сетевым анализатором – Wireshark
2. Для формирования необходимого объема, после начала записи трафика посерфить Интернет: поискать в поисковых движках, полазить по новостям и т.д. Не рекомендуется формировать весь объем трафика за счет использования одним сервисом – Telegram, Youtube, TikTok и пр. – так как собранный
сетевой профиль будет без характерных черт, которые можно будет затем отобразить и проанализировать на последующих этапах.
![image](https://github.com/ulgosipoy/saznd/assets/133878924/3914ed2a-19b4-4f63-940c-e701d7f066d8)


### Шаг 2

Выделить метаинформацию сетевого трафика с помощью утилиты Zeek:
zeek –C –r traffic.pcapng

Вычленить адреса из dns.log:
awk '/^[^#]/ {print $10}' dns.log >> dns

Полученные файлы:

![image](https://user-images.githubusercontent.com/90778174/230844615-cd2a65eb-e45f-4ae7-ad48-e8a43460baca.png)


### Шаг 3

Собрать данные об источниках нежелательного трафика, в данном случае с github – https://github.com/StevenBlack

С репозитория взяты несколько файлов hosts и объединены в один с помощью команды cat hosts2 >> hosts

Извлечение адресов из hosts:
cat hosts | cut -d " " -f2 >> hosts

### Шаг 4

Написать программу на языке Python 3.11.2, которая подсчитывает процент
нежелательного трафика в собранном на этапе 1:

Код:
```
with open('dns_addr', 'r') as f1, open('hosts', 'r') as f2:
	dns_lines = f1.readlines()		
	dns_l = [line for line in dns_lines if line.strip() and line.strip() != "-"]
	hosts_lines = f2.readlines()
	hosts_l = [line for line in hosts_lines if line.strip() and line.strip() != "-" and line.strip() != "#"]
	dns_set = set(dns_l)
	hosts_set = set(hosts_l)
	common_lines = dns_set.intersection(hosts_set)

print(f"Процент нежелательного трафика: {round(len(common_lines) / len(dns_l) * 100, 2)}%")


```

## ️Оценка результата

Собрано 115 Мб трафика.

Собраны данные об источниках нежелательного трафика.

Проведено их сравнение, найдены нежелательные dns адреса.

Подсчитан процент нежелательного трафика.

Получены результаты:
![image](https://user-images.githubusercontent.com/90778174/230845090-841327c3-e75b-4174-aff2-32a9aaf0c5d2.png)


## ️Вывод 

В результате выполнения лабораторной работы были изучены инструменты сетевого анализа, извлечение необходимой информации о dns адресах с помощью Zeek, а также проведено сравнение и анализ нежелательного трафика.