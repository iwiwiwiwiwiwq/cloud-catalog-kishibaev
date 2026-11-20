# Облачный каталог

Учебный каталог на Flask. Записи хранятся в DynamoDB, вложения — в приватном S3. Для доступа к AWS приложение использует роль EC2. Маршрут /health возвращает состояние приложения, а главная страница показывает имя контейнера.

Сборка: docker build -t cloud-app:1.0 .
Запуск: docker run -d --name cloud-app --restart always -p 80:5000 -e AWS_REGION=us-east-1 -e TABLE_NAME=YOUR_TABLE -e BUCKET_NAME=YOUR_BUCKET cloud-app:1.0
