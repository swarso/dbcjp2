#inicia con la imagen base que contiene Java runtime
FROM openjdk:17-jdk-slim as build

# se agregar el jar del microservicio al contenedor
COPY /config-server-0.0.1-SNAPSHOT.jar config-server-0.0.1-SNAPSHOT.jar
COPY /registry-service-0.0.1-SNAPSHOT.jar registry-service-0.0.1-SNAPSHOT.jar
COPY /api-gateway-0.0.1-SNAPSHOT.jar api-gateway-0.0.1-SNAPSHOT.jar
COPY /auth-service-0.0.1-SNAPSHOT.jar auth-service-0.0.1-SNAPSHOT.jar
COPY /alumno-service-0.0.1-SNAPSHOT.jar alumno-service-0.0.1-SNAPSHOT.jar

COPY commands.sh /commands.sh

RUN ["chmod", "+x", "/commands.sh"]

#se ejecuta el microservicio
#ENTRYPOINT ["java","-jar","/config-server.jar"]
ENTRYPOINT ["/commands.sh"]