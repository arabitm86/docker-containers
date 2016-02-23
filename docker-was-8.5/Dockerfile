FROM was-base-arabi

ADD was_part1.zip /tmp/was_part1.zip

RUN cd /tmp && mkdir was && unzip was_part1.zip -d was && rm -rf was_part1.zip 

ADD was_part2.zip /tmp/was_part2.zip

RUN cd /tmp && unzip was_part2.zip -d was && rm -rf was_part2.zip

ADD was_part3.zip /tmp/was_part3.zip

RUN cd /tmp && unzip was_part3.zip -d was && rm -rf was_part3.zip

ADD install_response.xml /tmp/install_response.xml

RUN cd /opt/IBM/InstallationManager/eclipse/tools && ./imcl -acceptLicense input /tmp/install_response.xml -log /tmp/install_log.xml

RUN rm -rf /tmp/was && rm -rf /tmp/install_response.xml

RUN /opt/IBM/was8.5/AppServer/bin/manageprofiles.sh -create -templatePath /opt/IBM/was8.5/AppServer/profileTemplates/default -enableAdminSecurity false -serverName server1 -defaultPorts

EXPOSE 9080 9060 9043 9443 2809

#ADD startWas.sh /opt/startWas.sh

#RUN cd /opt && chown -R wasadmin:wasadmin startWas.sh 

ADD startWas.sh etc/profile.d/startWas.sh

