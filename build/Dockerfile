# Используем образ Maven с OpenJDK
FROM maven:3.8.6-openjdk-17-slim AS build

# Установка рабочей директории
WORKDIR /app

# Копируем файл конфигурации Maven
COPY pom.xml .

# Копируем исходный код приложения
COPY src ./src

# Устанавливаем git
RUN apt-get update && apt-get install -y git

# Клонируем репозиторий
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git /opt/boxfuse-sample-java-war-hello

# Переходим в каталог приложения и собираем его
WORKDIR /opt/boxfuse-sample-java-war-hello
RUN mvn package

# Копируем WAR файл в временную директорию
RUN cp target/hello-1.0.war /tmp

# Указываем команду для запуска (можно изменить на то, что вам нужно)
CMD ["java", "-jar", "/tmp/hello-1.0.war"]





#FROM ubuntu:22.04
#LABEL version="3" maintainer="Fedor Chulkov"
#WORKDIR /opt
#ENV PATH /bin/bash:$PATH
#RUN apt update -y
#RUN apt upgrade -y
#RUN apt install default-jdk -y
#RUN apt install maven -y
#RUN apt install git -y
#RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
#WORKDIR /opt/boxfuse-sample-java-war-hello
#RUN mvn package
#RUN cp /opt/boxfuse-sample-java-war-hello/target/hello-1.0.war /tmp && sleep 300
#EXPOSE 8080
#CMD ["/bin/bash"]


#RUN cp /opt/boxfuse-sample-java-war-hello/target/hello-1.0.war /tmp
#ADD ./pom.xml /opt/
#RUN rm /opt/boxfuse-sample-java-war-hello/pom.xml
#RUN cp /opt/pom.xml /opt/boxfuse-sample-java-war-hello/pom.xml 