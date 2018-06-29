#### [Чек-лист заданий](https://daniel55411.github.io/2018/04/29/check-list/)
#### [Полный список дайджестов](https://daniel55411.github.io/2018/04/29/table-of-contents/)

# Задача - провести perfomance-тест работы потребителя Kafka c Akka и Kafka без Akka
В данном случае потребитель будет непросто вычитывать данные из топика, но и еще запоминать на какой позиции он остановился, чтобы при повторном чтении данных, не получить ту же порцию, что и в прошлый раз.

### Какие задачи решены?
- Изучил сеиантики At-least-once-delivery, Exactly-once, At-most-once-delivery
- Написал классы producer'ов с использованием Akka (ReactiveKafkaAtLeastOnceDeliveryConsumer) и без(KafkaAtLeastOnceDeliveryConsumer)
- Рассмотрел коробочные решения, представленные в документации akka

### Вывод
```
Benchmark                                                   (limit)   Mode  Cnt  Score   Error  Units
Benchmarks.c_kafkaAtLeastOnceDeliveryConsumerBench            10000  thrpt    5  0,266 ± 0,003  ops/s
Benchmarks.c_reactiveKafkaAtLeastOnceDeliveryConsumerBench    10000  thrpt    5  0,051 ± 0,001  ops/s
```
Таким образом мы видим деградацию производительности в 5 при использовании Akka

### Краткая памятка по найденному материалу
1. Akka предоставляет хранение offset'ов из коробки, что может быть удобным для реализации разных техник или стратегий. Очень хороший пример (правда без сипользования Akka) приводится на конференции Backend Conf 2017, рассказчика Артёма Выборнова (Rambler&Co).
2. Akka дает из коробки решения потребления и коммита данных пачками (batch), также Akka дает возможнсть объединять данные не только в пачки, но и в группы, что может дать лучшую производительность для менее активных топиков.
    
  

