#Задача - научиться ипользовать Apache Zookeeper для хранения настроек приложения

## Какую задачу решил - Сохранение настроек и их получение

### Что использовал?
Для решения этой задачи использовались следующие инструменты:
1. `Apache Curator Framework` - высоко уровенвая API-библиотека, упрощаяющая работу с Apache Zookeeper.
2. `Typesafe Config` - библиотка для прасинга конфигов из файла в форматах JSON, CONF, PROPERTIES

### Структура

- `zookeepeer.example`
  - `flow`
    - `ConfigLoader` - наследуется от ZKClient, отвечает за выгрузку конфигов по указанным узлам
    - `PropertiesConverter` - преобразует конфиги с точечной нотацией в пространство имен zookeeper
    - `PropertiesParser` - парсер конфигов из строки
    - `Runner` - запуск площадки
    - `SettingsReader` - наследуется от ZKClient, отвечает за получение конфигов из указанных узлов
  - `ZKClient` - создает клиента curator framework для упрощенной работы с zookeeper
  
Весь код доступен в [репозитории](https://github.com/daniel55411/test-akka-with-kafka/tree/master/src/main/java/examples/kafka/zookeeper/example)
