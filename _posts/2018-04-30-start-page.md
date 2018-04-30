
[Полный список дайджестов](https://daniel55411.github.io/2018/04/29/table-of-contents/)

## Исселодовательская задача: Kafka with akka 

### Что необходимо?

Основная задача этого проекта - понять, даст ли прирост эффективности к `kafka` тулкит `akka`.
В ходе проекта будет изучено, в каких случаях удобно использовать framework `akka` для решения задач `kafka`

Основной план, задачи и мини-итоги будут выкладываться [здесь](https://docs.google.com/document/d/1qd69gX6A2TS92iku7WMLVMAAUL2VxFbzU7IZF_pa7-8/edit?usp=sharing)

В отдельности план будет представлен [здесь](https://docs.google.com/document/d/1o-ZEmnEIEVolPPbffB3VhU3yOAm83UOy6mMxOoNM9uI/edit)

Кратко. Основные задачи и возможные случаи - рассмотреть работу kafka вместе с akka в трех случаях:
1. Использовать kafka-with-akka в качестве data's `sink`. Source - http-server
2. Использовать kafka-with-akka в качестве data's `source`. Sink - http-server
3. Использовать kafka-with-akka в качестве data's `sink` и `source`. То есть data's `flow`

Весь код проекта будет находиться [здесь](https://github.com/daniel55411/test-akka-with-kafka)

Поехали!

Полезные ссылки:
- [Managing configuration of a distributed system with Apache ZooKeeper](https://sysgears.com/articles/managing-configuration-of-distributed-system-with-apache-zookeeper/)
