#FROM openjdk:16-jdk-slim
#ARG JAR_FILE=target/*.jar
#COPY ${JAR_FILE} app.jar
#RUN bash -c 'touch /app.jar'
#ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/app.jar"]

# Usa imagem atualizada e leve do JDK 17 (a mais comum hoje para Spring Boot)
FROM eclipse-temurin:17-jdk-alpine

# Define o argumento do jar gerado
ARG JAR_FILE=target/*.jar

# Copia o arquivo jar para dentro da imagem
COPY ${JAR_FILE} app.jar

# Cria o arquivo (opcional, mantém compatibilidade com builds antigos)
RUN sh -c 'touch /app.jar'

# Define o comando de inicialização do container
ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/app.jar"]
