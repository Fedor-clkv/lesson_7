FROM ubuntu:22.04
LABEL version="3" maintainer="Fedor Chulkov"
ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
WORKDIR /tmp
RUN apt update -y && apt upgrade -y && apt install wget -y && mkdir /usr/local/tomcat && wget https://archive.apache.org/dist/tomcat/tomcat-10/v10.0.20/bin/apache-tomcat-10.0.20.tar.gz && tar xvfz apache-tomcat-10.0.20.tar.gz && rm -r apache-tomcat-10.0.20.tar.gz && cp -Rv /tmp/apache-tomcat-10.0.20/* /usr/local/tomcat/ && rm -r /tmp/apache-tomcat-10.0.20/ 
ADD cp /opt/vlm/hello-1.0.war /usr/local/tomcat/webapps/
EXPOSE 8080
CMD ["/usr/local/tomcat/bin/catalina.sh", "run"]