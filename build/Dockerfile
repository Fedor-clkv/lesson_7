FROM ubuntu:22.04
LABEL LABEL version="3" maintainer="Fedor Chulkov"
WORKDIR /opt
ENV PATH /bin/bash:$PATH
RUN apt update -y && apt upgrade -y && apt install default-jdk -y && apt install maven -y && apt install git -y 
#RUN mkdir /opt/vlm
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
WORKDIR /opt/boxfuse-sample-java-war-hello
RUN mvn package
WORKDIR /opt/test
#RUN cp /opt/boxfuse-sample-java-war-hello/target/hello-1.0.war /opt
EXPOSE 8080
CMD ["/bin/bash"]


#ADD ./pom.xml /opt/
#RUN rm /opt/boxfuse-sample-java-war-hello/pom.xml
#RUN cp /opt/pom.xml /opt/boxfuse-sample-java-war-hello/pom.xml 