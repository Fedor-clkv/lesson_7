FROM ubuntu:22.04
LABEL version="3" maintainer="Fedor Chulkov"
ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
WORKDIR /tmp
RUN apt update -y && apt upgrade -y && apt install wget -y
RUN mkdir /usr/local/tomcat
RUN wget https://archive.apache.org/dist/tomcat/tomcat-10/v10.0.20/bin/apache-tomcat-10.0.20.tar.gz
RUN tar xvfz apache-tomcat-10.0.20.tar.gz
RUN rm -r apache-tomcat-10.0.20.tar.gz
RUN cp -Rv /tmp/apache-tomcat-10.0.20/* /usr/local/tomcat/
RUN rm -r /tmp/apache-tomcat-10.0.20/
#RUN cp /opt/hello-1.0.war /usr/local/tomcat/webapps/
EXPOSE 8080
CMD ["/usr/local/tomcat/bin/catalina.sh", "run"]