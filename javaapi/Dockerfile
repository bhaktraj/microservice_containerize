FROM openjdk:8 AS first_image
WORKDIR /app
RUN apt update && apt install maven -y
COPY ./ ./app/
RUN mvn install -DskipTests

FROM openjdk:8
WORKDIR /app
COPY --from=first_image /app/target/book-work-0.0.1-SNAPSHOT.jar /app/book-work.jar
EXPOSE 4000
CMD [ "java","-jar","book-work.jar" ]