# Тестовая заглушка

Запуск

````
java -jar sampleMock-0.1.jar
````

Принимает запрос в формате 

````
http://localhost:9093/search?surname=Иванов
````

Проверяет количество пользователей с такой фамилией в БД (инициализируется из файла)

Отдает ответ 

````xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<response>
    <message>Users found: 1</message>
    <date>02.08.2020 22:05:52</date>
</response>
````

Отдает метрики времени обработки запросов по адресу

````
http://localhost:9092/metrics
````

## Настройки

### Параметры командной строки

| Параметр | Тип | Описание |
|:---:|:---:|:---:|
| configFile | String | Путь к файлу конфига |
| metricsPort | int | Порт для метрик, путь `/metrics` |

### Конфигурационный файл

| Параметр | Тип | Описание |
|:---:|:---:|:---:|
| pool | String | Путь к файлу, из которого создается БД |
| searchConfig/port | int | Порт, на котором поднимантся обработчик для поиска |
| searchConfig/path | String | Путь, по которому вызывается обработчик |