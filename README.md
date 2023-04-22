# test_task_in_kafka
В данной проекте реализовано 2 продюсера, которые посылают слова в разные топики; 3 инcтанса кафки (для распределения нагрузки и отказоустойчивости) и 2 консьюмера, каждый из которых считывает количество слов из своего топика.
Структура прописана `docker-compose.yml`

Get started:
```
docker-compose up -d --build
```
Отправка сообщения с первого продюсера: `http://0.0.0.0:5000/api/v1/push/<word>`

Пример:

<img width="465" alt="image" src="https://user-images.githubusercontent.com/38925021/233776492-0ed8af70-3140-4f44-88b3-a54d4b4f6a47.png">

Отправка сообщения со второго продюсера: `http://0.0.0.0:5005/api/v1/push/<word>`

Пример:

<img width="595" alt="image" src="https://user-images.githubusercontent.com/38925021/233776541-fa4b22bc-daf7-4fc9-9a53-651561b1b4c5.png">


Для просмотра количества слов, можно использовать `docker logs <consumer_container_id>`

Пример:

<img width="1120" alt="image" src="https://user-images.githubusercontent.com/38925021/233776591-c61de8b2-c289-4d52-87b2-4201da964a47.png">

После ввода `docker logs test_task_in_kafka_count_words_1`:

<img width="435" alt="image" src="https://user-images.githubusercontent.com/38925021/233776793-f7b16da3-ec3f-4e10-9d36-4fd0f804232f.png">

После ввода `docker logs test_task_in_kafka_count_words_2_1`:

<img width="408" alt="image" src="https://user-images.githubusercontent.com/38925021/233776954-e10cef63-d147-4eb1-bf82-3199124f866d.png">
