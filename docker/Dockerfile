from ubuntu:14.04
MAINTAINER kjansen
run echo "create HibernateTest container"
run ping -c 1 www.google.com
run echo "Network is oke"
run sudo apt-get update
run apt-get -y install openjdk-7-jdk
run echo 'export JAVA_HOME=/usr/lib/jvm/jre-1.7.0-openjdk.x86_64' > /etc/profile.d/java.sh
run apt-get -y install openssh-server
run apt-get -y install tomcat7
add HibernateTest-0.1.war /var/lib/tomcat7/webapps/HibernateTest-0.1.war

#to make the ubunto config stuff avaible
ENV CATALINA_HOME /usr/share/tomcat7
ENV CATALINA_BASE /var/lib/tomcat7/
# Launch Tomcat on startup
add run.sh /tmp/run.sh
CMD /tmp/run.sh

EXPOSE 8080 22