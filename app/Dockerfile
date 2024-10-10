# Используем базовый образ Ubuntu
FROM ubuntu:22.04

# Указываем метаданные образа
LABEL version="3" maintainer="Fedor Chulkov"

# Установка переменных окружения
ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH

# Установка рабочего каталога
WORKDIR /tmp

# Обновление и установка необходимых пакетов
RUN apt-get update -y && apt-get upgrade -y && apt-get install -y wget

# Создаем каталог Tomcat, если он еще не существует
RUN mkdir -p /usr/local/tomcat

# Скачиваем и распаковываем Tomcat
RUN wget https://archive.apache.org/dist/tomcat/tomcat-10/v10.0.20/bin/apache-tomcat-10.0.20.tar.gz && \
    tar xvfz apache-tomcat-10.0.20.tar.gz && \
    rm -r apache-tomcat-10.0.20.tar.gz && \
    cp -Rv /tmp/apache-tomcat-10.0.20/* /usr/local/tomcat/ && \
    rm -r /tmp/apache-tomcat-10.0.20/

# Копируем WAR-файл в веб-приложения Tomcat
COPY hello-1.0.war /usr/local/tomcat/webapps/

# Открываем порт для Tomcat
EXPOSE 8080

# Команда запуска Tomcat
CMD ["catalina.sh", "run"]


#FROM ubuntu:22.04
#LABEL version="3" maintainer="Fedor Chulkov"
#ENV CATALINA_HOME /usr/local/tomcat
#ENV PATH $CATALINA_HOME/bin:$PATH
#WORKDIR /tmp
#RUN apt update -y && apt upgrade -y && apt install wget -y
#RUN mkdir -p /usr/local/tomcat
#RUN wget https://archive.apache.org/dist/tomcat/tomcat-10/v10.0.20/bin/apache-tomcat-10.0.20.tar.gz
#RUN tar xvfz apache-tomcat-10.0.20.tar.gz
#RUN rm -r apache-tomcat-10.0.20.tar.gz
#RUN cp -Rv /tmp/apache-tomcat-10.0.20/* /usr/local/tomcat/
#RUN rm -r /tmp/apache-tomcat-10.0.20/
#RUN cp /tmp/hello-1.0.war /usr/local/tomcat/webapps/
#EXPOSE 8080
#CMD ["/usr/local/tomcat/bin/catalina.sh", "run"]