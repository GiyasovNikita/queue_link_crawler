# queue_link_crawler

Проект состоит из двух консольных приложений для обработки внутренних ссылок на веб-страницах с использованием RabbitMQ:
### Шаги установки
1. Клонируйте репозиторий или загрузите файлы.

2. Установите необходимые зависимости:
   ```bash
   pip install -r requirements.txt
   ```

3. Создайте файл `.env` в корневом каталоге проекта и добавьте следующие переменные:

   ```.env
   RABBITMQ_HOST=localhost
   RABBITMQ_PORT=5672
   RABBITMQ_USER=user
   RABBITMQ_PASSWORD=password
   QUEUE_NAME=queue_links
   ```

4. Запустите RabbitMQ с помощью Docker
    ```bash
    docker-compose up --build -d
    ```
    
5. Запустите producer (передайте URL в качестве аргумента):
    ```bash
    python producer.py url
    ```


6. Запустите consumer:
    ```bash
    python consumer.py
    ```