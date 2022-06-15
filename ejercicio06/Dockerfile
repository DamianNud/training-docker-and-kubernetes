FROM registry.access.redhat.com/redhat-openjdk-18/openjdk18-openshift:1.12-1.1652304483

ADD passwordapi.jar /usr/bin

WORKDIR /usr/bin

CMD ["java", "-jar", "passwordapi.jar"]
