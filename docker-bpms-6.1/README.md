# docker-container-bpms-6.1

Add the jboss-bpmsuite-6.1.0.GA-deployable-eap6.x.zip and  jboss-eap-6.4.0.zip to this directory and run from here:

docker build -t tarabi/jboss-bpms-6.1 .

To run the image when the build is complete:

docker run -p 8180:8080 -p 9190:9990 -p 9899:9999 --name IMAGE-NAME -t tarabi/jboss-bpms-6.1

maybe consider running: docker run --publish-all=true --name IMAGE-NAME -t tarabi/jboss-bpms-6.1 to expose all ports automatically?

This image is pushed to dockerhub with name arabitm86/tarabi-jboss-bpms-6.1 

All the ports exposed are for the standalone-full profile. The ports list is:
8080 9990 9999 8009 8443 3528 3529 5445 8090 4447 4712 4713 8001(git ssh)  9418 (git)
