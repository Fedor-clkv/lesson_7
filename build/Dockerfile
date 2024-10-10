FROM ubuntu:22.04
LABEL version="3" maintainer="Fedor Chulkov"
WORKDIR /opt
ENV PATH /bin/bash:$PATH
RUN apt update -y
RUN apt upgrade -y
RUN apt install default-jdk -y
RUN apt install maven -y
RUN apt install git -y
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
WORKDIR /opt/boxfuse-sample-java-war-hello
RUN mvn package
RUN cp /opt/boxfuse-sample-java-war-hello/target/hello-1.0.war /tmp/shared
EXPOSE 8080
CMD ["/bin/bash"]


#RUN cp /opt/boxfuse-sample-java-war-hello/target/hello-1.0.war /tmp
#ADD ./pom.xml /opt/
#RUN rm /opt/boxfuse-sample-java-war-hello/pom.xml
#RUN cp /opt/pom.xml /opt/boxfuse-sample-java-war-hello/pom.xml 