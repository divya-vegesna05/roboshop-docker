
FROM maven AS build
WORKDIR /opt/shipping
COPY pom.xml /opt/shipping
COPY src /opt/shipping/src
RUN mvn dependency:resolve
RUN mvn clean package
# RUN
FROM openjdk:8-jre-alpine
EXPOSE 8080
WORKDIR /opt/shipping
ENV CART_ENDPOINT=cart:8080
ENV DB_HOST=mysql
COPY --from=build /opt/shipping/target/shipping-1.0.jar shipping.jar
CMD ["java","-jar","shipping.jar"]