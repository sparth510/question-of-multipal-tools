FROM ubuntu:18.04
RUN apt update -y
RUN mkdir pipelines
COPY . /pipelines
RUN apt-get install -y  software-properties-common
RUN apt install -y openjdk-8-jre
RUN add-apt-repository ppa:openjdk-r/ppa
RUN apt update -y 
RUN apt install -y  openjdk-8-jdk
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64
ENV PATH $PATH:$JAVA_HOME/bin
RUN apt install -y wget
RUN wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | apt-key add -
RUN echo deb http://pkg.jenkins-ci.org/debian binary/ > /etc/apt/sources.list.d/jenkins.list
RUN apt update -y
RUN apt install -y jenkins
EXPOSE 8080
ENTRYPOINT ["java","-jar","/usr/share/jenkins/jenkins.war"]




