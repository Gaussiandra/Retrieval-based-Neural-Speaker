Диалоговая система, которая на введённое сообщение способна разумным образом подобрать ответ из заданного списка.
##### Пример работы алгоритма, обёрнутого в чат-бот в телеграме
![Снимок](https://user-images.githubusercontent.com/34653515/111865085-fcc6d480-8975-11eb-8fd4-e55828b180b7.PNG)

### Описание
* Модель основана на DSSM архитектуре, где каждый возможный ответ и введёный контекст задается своим вектором. 
* Подходящий ответ определяется благодаря косинусной близости и алгоритму **HNSW**.
* Энкодеры имеют одинаковую архитектуру: **FastText embedding -> LSTM -> mean-max-last pooling -> Linear**. 
* Обучение производится на триплетном лоссе.
* Был использован Hard Negatives Mining как техника для улучшения сходимости.
* Данными для обучения стали телеграм беседы. Спасибо за парсинг [Fulldis](https://github.com/Fulldis).
