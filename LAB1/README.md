---
title: "практическая работа 1"
author: Калбак Долума
format: 
    md:
        output-file: README.md
engine: knitr
---

### Системы аутентификации и защиты от несанкционированного доступа

Лабораторная работа №1

### Цель

Вывести информацию о системе

### Исходные данные

1.  ОС Windows 10
2.  RStudio Desktop
3.  Интерпретатор языка R 4.3.0

### План

1.  Выполнить команду system2("systeminfo", stdout = TRUE)
2.  Выполнить команду system("wmic cpu get name")
3.  Выполнить команду system("powershell.exe Get-EventLog -LogName System -Newest 30")

### Шаги

1\. Используя команду system2("systeminfo", stdout = TRUE), выводим информацию о системе

```{r}
system2("systeminfo", stdout = TRUE)
```

2\. Далее применяем команду system("wmic cpu get name") для вывода информации о процессоре

```{r}
system2("cmd", args = c("/c", "wmic cpu get name"), stdout = TRUE)
```

3\. Также выполним команду system("powershell.exe Get-EventLog -LogName System -Newest 30") для вывода логов

```{r}
system2("powershell.exe", args = c("Get-EventLog", "-LogName", "System", "-Newest", "30"), stdout = TRUE)
```

### Оценка результата

В результате лабораторной работы, получили основную информацию об операционной системе, процессоре и логи системы.

### Вывод

Таким образом, мы научились работать с базовыми командами командой строки и получать информацию об операционной системе.
