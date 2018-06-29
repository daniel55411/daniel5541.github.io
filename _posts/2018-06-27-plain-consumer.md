#### [Чек-лист заданий](https://daniel55411.github.io/2018/04/29/check-list/)
#### [Полный список дайджестов](https://daniel55411.github.io/2018/04/29/table-of-contents/)

# Задача - провести perfomance-тест работы просто потребилеля Kafka c Akka и Kafka без Akka

В этом случае был проведено сравнение производительности потребления данных с использованием Akka и без него. Потребление данных в данном случае происходит без коммита, это означает, что происходит просто чтение данных из топика без запоминания информации о том, сколько прочитано данных и сохранением текущей позиции.

### Какие задачи решены?
- Написал классы consumer'ов с использованием Akka (ReactiveKafkaPlainConsumer) и без(KafkaPlainConsumer)
- Рассмотрел коробочные решения, представленные в документации akka для Consumer

### Что планирую сделать дальше?
- Перейти к обработке следующего случая - At-least-once-delivery (потребитель c коммитом прочитанных данных)

### Вывод
```
Benchmark                                     (limit)   Mode  Cnt  Score   Error  Units
Benchmarks.b_kafkaPlainConsumerBench             1000  thrpt    5  5,934 ± 0,731  ops/s
Benchmarks.b_reactiveKafkaPlainConsumerBench     1000  thrpt    5  2,767 ± 0,488  ops/s
```
Таким образом мы видим деградацию производительности в 2 при использовании Akka

### Краткая памятка по найденному материалу
1. Consumer.plainSource (Consumer API), Consumer.plainPartitionedManualOffsetSource предоставляют интерфейс работы простого потребителя.
    
  


