FROM jboss/base-jdk:7

ADD jboss-eap-6.4.0.zip /tmp/jboss-eap-6.4.0.zip
ADD jboss-bpmsuite-6.1.0.GA-deployable-eap6.x.zip /tmp/jboss-bpmsuite-6.1.0.GA-deployable-eap6.x.zip
 
RUN mkdir -p /opt/jboss

RUN unzip /tmp/jboss-eap-6.4.0.zip -d /opt/jboss
RUN unzip -o /tmp/jboss-bpmsuite-6.1.0.GA-deployable-eap6.x.zip -d /opt/jboss

ENV JBOSS_HOME /opt/jboss/jboss-eap-6.4

RUN $JBOSS_HOME/bin/add-user.sh -u admin -p admin1234!  --silent
RUN $JBOSS_HOME/bin/add-user.sh -a -u admin -p admin1234! -g admin --silent

RUN echo "JAVA_OPTS=\"\$JAVA_OPTS -Djboss.bind.address=0.0.0.0 -Djboss.bind.address.management=0.0.0.0\"" >> $JBOSS_HOME/bin/standalone.conf

EXPOSE 8080 9990 9999 8009 8443 3528 3529 5445 8090 4447 4712 4713 8001 9418

ENTRYPOINT $JBOSS_HOME/bin/standalone.sh -c standalone-full.xml
