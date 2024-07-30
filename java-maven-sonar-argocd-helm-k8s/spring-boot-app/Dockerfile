FROM techiescamp/jdk-17:1.0.0 AS base

# Simply the artifact path
#ARG artifact=target/spring-boot-web.jar
WORKDIR /app
COPY . .
RUN mvn clean package

FROM gcr.io/distroless/java17-debian12

COPY --from=base /app/target/spring-boot-web.jar ./app.jar
# This should not be changed
ENTRYPOINT ["java","-jar","app.jar"]



