# Build stage
FROM maven:3.9.6-eclipse-temurin-17 AS build
WORKDIR /opt/server
COPY pom.xml .
COPY src /opt/server/src
RUN mvn clean package -DskipTests

# Run stage
FROM eclipse-temurin:17-jdk
WORKDIR /opt/server
COPY --from=build /opt/server/target/shipping-1.0.jar shipping.jar
ENV CART_ENDPOINT="cart:8080" \
    DB_HOST="mysql"
CMD ["java", "-jar", "shipping.jar"]
   