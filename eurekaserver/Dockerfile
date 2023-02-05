FROM maven:3.6.0-jdk-13 as build

WORKDIR /usr/src/app

COPY src /usr/src/app/src
COPY pom.xml /usr/src/app
RUN mvn -f /usr/src/app/pom.xml clean package



FROM openjdk:18-jdk-alpine
WORKDIR /usr/src/app
# ARG JAVA_OPTS
# ENV JAVA_OPTS=$JAVA_OPTS
COPY --from=build /usr/src/app/target/eurekaserver.jar /usr/app/eurekaserver.jar

CMD ["java","-jar","/usr/app/eurekaserver.jar"]


# FROM openjdk:18-jdk-alpine
# VOLUME /tmp
# ARG JAVA_OPTS
# ENV JAVA_OPTS=$JAVA_OPTS
# COPY target/eurekaServer.jar eurekaserver.jar
# EXPOSE 8761
# ENTRYPOINT exec java $JAVA_OPTS -jar eurekaserver.jar

# For Spring-Boot project, use the entrypoint below to reduce Tomcat startup time.
#ENTRYPOINT exec java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar eurekaserver.jar
