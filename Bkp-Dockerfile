FROM registry.access.redhat.com/rhel7/rhel
#FROM registry.redhat.io/rhel7.4
RUN useradd webuser
RUN mkdir /apps
RUN mkdir /apps/apache-tomcat-9.0.30
RUN mkdir /apps/zulu8.46.0.19-ca-jdk8.0.252-linux_x64
ADD apache-tomcat-9.0.30 /apps/apache-tomcat-9.0.30
ADD zulu8.46.0.19-ca-jdk8.0.252-linux_x64 /apps/zulu8.46.0.19-ca-jdk8.0.252-linux_x64

RUN chown -R webuser:webuser /apps/
USER webuser
RUN chmod -R 777 /apps/apache-tomcat-9.0.30/bin
ENV JAVA_HOME /apps/zulu8.46.0.19-ca-jdk8.0.252-linux_x64
ENV PATH /apps/zulu8.46.0.19-ca-jdk8.0.252-linux_x64/bin:$PATH
WORKDIR /apps/apache-tomcat-9.0.30/bin
#EXPOSE 8059
EXPOSE 8989
CMD ["/apps/apache-tomcat-9.0.30/bin/catalina.sh", "run"]

#WORKDIR /apps/jboss/apache/bin
#ENV PATH /apps/jboss/apache/bin:$PATH
#RUN chmod -R 775 /apps/jboss/apache/bin
#EXPOSE 9090
##CMD apachectl -D FOREGROUND
