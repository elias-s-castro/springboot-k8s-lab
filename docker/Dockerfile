#================================================================
# STAGE 1: Build the application
#================================================================
FROM maven:3.9.6-eclipse-temurin-11 AS builder

WORKDIR /build

# Copia apenas o necessário para instalar as dependências
COPY pom.xml .
RUN mvn -B dependency:go-offline

# Copia o código fonte
COPY src ./src

# Build do jar
RUN mvn -B clean package -DskipTests

#================================================================
# STAGE 2: Run the application
#================================================================
FROM eclipse-temurin:11-jre-jammy

WORKDIR /app

# Copia somente o jar final
COPY --from=builder /build/target/*.jar app.jar

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app.jar"]