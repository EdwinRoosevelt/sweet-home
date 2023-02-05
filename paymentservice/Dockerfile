FROM openjdk:18-jdk-alpine
VOLUME /tmp
ARG JAVA_OPTS
ENV JAVA_OPTS=$JAVA_OPTS
COPY target/paymentService.jar paymentService.jar
EXPOSE 8082
ENTRYPOINT exec java $JAVA_OPTS -jar paymentService.jar

# For Spring-Boot project, use the entrypoint below to reduce Tomcat startup time.
#ENTRYPOINT exec java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar eurekaserver.jar
