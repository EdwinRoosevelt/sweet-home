FROM openjdk:18-jdk-alpine
VOLUME /tmp
ARG JAVA_OPTS
ENV JAVA_OPTS=$JAVA_OPTS
COPY target/notificationservice.jar notificationservice.jar
EXPOSE 8083
ENTRYPOINT exec java $JAVA_OPTS -jar notificationservice.jar

# For Spring-Boot project, use the entrypoint below to reduce Tomcat startup time.
#ENTRYPOINT exec java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar eurekaserver.jar
