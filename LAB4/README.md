# Развертывание Threat intelligence Platform OpenCTI
Калбак Долума БИСО-01-20

## Цель работы

1. Освоить базовые подходы процессов Threat Intelligence
2. Освоить современные инструменты развертывания контейнеризованных приложений
3. Получить навыки поиска информации об угрозах ИБ

## ️Исходные данные

1. ПК с ОС Windows 10
2. Virtual Box с ОС Linux Ubuntu
3. Установленные и настроенные Docker и Elasticsearch

## Ход выполнения работы

### Шаг 1.
Разворачивание системы Threat Intelligence OpenCTI осуществлялось с помощью Docker.

1. Для работы с ElasticSearch требуется увеличить размер виртуальной памяти системы:
```()
sudo sysctl -w vm.max_map_count=1048575
```

2. В новой директории был создан файл .env для хранения параметров окружения

Использованы следующие команды для генерации UUIDv4 и записи их в файл .env:
```()
echo "OPENCTI_ADMIN_TOKEN=$(uuidgen)" >> .env
echo "CONNECTOR_EXPORT_FILE_STIX_ID=$(uuidgen)" >> .env
echo "CONNECTOR_EXPORT_FILE_CSV_ID=$(uuidgen)" >> .env
echo "CONNECTOR_EXPORT_FILE_TXT_ID=$(uuidgen)" >> .env
echo "CONNECTOR_IMPORT_FILE_STIX_ID=$(uuidgen)" >> .env
echo "CONNECTOR_IMPORT_DOCUMENT_ID=$(uuidgen)" >> .env
```

3. В этой же директории создан файл docker-compose.yml

Запуск контейнера с помощью команды:
```()
sudo docker-compose up -d
```
![image](https://github.com/ulgosipoy/saznd/assets/133878924/9737e71b-ae95-43fc-b2db-c012c046babb)

### Шаг 2.

1. Заходим в веб-интерфейс OpenCTI `localhost:8080`

Входим по данным пользователя из файла конфигурации окружения:

![image](https://github.com/ulgosipoy/saznd/assets/133878924/c0b5bb70-1a26-449e-99e8-cb17cc5dd53f)

2. Далее используем данный код через оболочку Python для импорта данных из файла hosts.txt

``` python
import pycti
from stix2 import TLP_GREEN
from datetime import datetime
date = datetime.today().strftime("%Y-%m-%dT%H:%M:%SZ")
api_url = 'http://localhost:8080'
api_token = 'bd78ebc1-d5c8-466f-bbd3-126a9479472c'
client = pycti.OpenCTIApiClient(api_url, api_token)

TLP_GREEN_CTI = client.marking_definition.read(id=TLP_GREEN["id"])
with open('hosts.txt', 'r') as f:
    domains = f.read().splitlines()
k = 1
for domain in domains:
    indicator = client.indicator.create(
    name="Malicious domain {}".format(k),
    description="MPVS hosts",
    pattern_type="stix",
    label="mpvs hosts",
    pattern="[domain-name:value = '{}']".format(domain),
    x_opencti_main_observable_type="IPv4-Addr",
    valid_from=date,
    update=True,
    score=75,
    markingDefinitions=[TLP_GREEN_CTI["id"]],
    )
    print("Создан индикатор:", indicator["id"])
    k += 1
```

3. Импортируем данные

![image](https://github.com/ulgosipoy/saznd/assets/133878924/584d1bcc-d143-452c-8f76-6f402903f230)

![image](https://github.com/ulgosipoy/saznd/assets/133878924/77cf4848-925f-4e2c-89ac-96a3880c11e3)

4. В используемом списке не было найдено хостов

![image](https://github.com/ulgosipoy/saznd/assets/133878924/b50dd762-1720-4544-ae68-fa9a449acab7)


## Оценка результата

С помощью платформы OpenCTI удалось проанализировать трафик на предмет перехода по нежелательным доменам.

## Выводы

Таким образом, были изучены возможности работы с платформой threat intelligence OpenCTI
