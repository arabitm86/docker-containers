FROM fedora:20

RUN yum install -y unzip 
RUN  groupadd -r wasadmin && useradd -r -g wasadmin wasadmin 

COPY agent.installer.linux.gtk.x86_64_1.6.2000.20130301_2248.zip  /tmp/ 

RUN \ 
	cd /tmp &&  unzip /tmp/agent.installer.linux.gtk.x86_64_1.6.2000.20130301_2248.zip -d /tmp && ./installc -log /opt/im_install.log -acceptLicense && rm -rf * 

RUN cd /opt && chown -R wasadmin:wasadmin IBM
