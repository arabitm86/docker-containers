FROM jboss/base-jdk:7

ADD jboss-eap-6.4.0.zip /tmp/jboss-eap-6.4.0.zip

RUN mkdir -p /opt/jboss

RUN unzip /tmp/jboss-eap-6.4.0.zip -d /opt/jboss

ENV JBOSS_HOME /opt/jboss/jboss-eap-6.4

RUN $JBOSS_HOME/bin/add-user.sh -u tarabi -p 12#Vinson  --silent

RUN echo "JAVA_OPTS=\"\$JAVA_OPTS -Djboss.bind.address=0.0.0.0 -Djboss.bind.address.management=0.0.0.0\"" >> $JBOSS_HOME/bin/standalone.conf

EXPOSE 8080 9990 9999

ENTRYPOINT $JBOSS_HOME/bin/standalone.sh -c standalone-full.xml
