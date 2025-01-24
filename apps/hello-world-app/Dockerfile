#- Запускаем на образе java
FROM openjdk:8u342-jre-slim as main
#- Создать папку в виртуалке
WORKDIR /app
# Копируем .jar файлы из каталога target в контейнер
COPY target/*.jar /app/
#- Выполняем команду (запуск артефакта)
CMD java -jar my-app-1.0-SNAPSHOT.jar
