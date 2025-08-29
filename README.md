# BFH Java Qualifier – Auto Submit App

This Spring Boot app runs **automatically on startup** to:

1. Call the **Generate Webhook** API with your name, regNo, and email.
2. Pick the correct **final SQL query** based on the last two digits of the `regNo` (Odd → Q1, Even → Q2).
3. POST the `{"finalQuery":"…"}` JSON to the returned **webhook URL** using the provided **JWT** in the `Authorization` header.

## Configure
Edit `src/main/resources/application.properties` with your details.

## Build
```bash
mvn clean package
```

## Run
```bash
java -jar target/bfh-java-qualifier-1.0.0.jar
```

## Replace the SQL if needed
- **Q2** SQL is implemented at `SqlQueries.finalQueryQ2()`.
- **Q1** currently uses a placeholder. Update `SqlQueries.finalQueryQ1Placeholder()` if needed.
