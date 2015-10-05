# docker-container-eap-6.4


Add the JBoss EAP 6.4 Zip File to this directory and run from here:

docker build -t tarabi/jboss-eap-6.4 .

To run the image when the build is complete:

docker run -p 8180:8080 -p 9190:9990 -p 9899:9999 --name IMAGE-NAME -t tarabi/jboss-eap-6.4

All the ports exposed are for the standalone-full profile. The ports list is:
8080 9990 9999 8009 8443 3528 3529 5445 8090 4447 4712 4713
