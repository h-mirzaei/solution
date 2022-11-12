FROM openjdk:8-jre-alpine

ENV SPRING_OUTPUT_ANSI_ENABLED=ALWAYS \
    APP_SLEEP=0 \
    JAVA_OPTS=""

# add directly the jar
ADD ${WORKSPACE}/target/*.jar*.jar /jb-hello-world-maven-0.2.0.jar

EXPOSE 9292
CMD echo "The application will start in ${APP_SLEEP}s..." && \
    sleep ${APP_SLEEP} && \
    java ${JAVA_OPTS} -Djava.security.egd=file:/dev/./urandom -jar /jb-hello-world-maven-0.2.0.jar

