FROM maven:3.8.6-openjdk-8

WORKDIR /opt/server

COPY pom.xml .
COPY src ./src

RUN mvn clean package

RUN mv target/*.jar shipping.jar

ENV CART_ENDPOINT="cart:8080" \
    DB_HOST="mysql"

CMD ["java", "-jar", "shipping.jar"]
