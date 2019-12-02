A basic web application using [quarkus.io](https://quarkus.io/).

1. **Run tests:** `./mvnw test`

2. **Run in Dev mode:** ` ./mvnw compile quarkus:dev`

3. **Web Resources:**

   3.1 Basic: http://0.0.0.0:8080/hello
   
   3.2 Dependency Injection: http://0.0.0.0:8080/hello/greeting/quarkus
   
        3.2.1 Annotate class using, `@ApplicationScoped`
        
        @ApplicationScoped
        public class GreetingService {
        }        
        
        3.2.2 Inject the dependency using, `@Inject`
        
        @Inject
        GreetingService service;
       
   3.3 Async: http://0.0.0.0:8080/hello/async
    
    ```
    public CompletionStage<String> async() {
        return CompletableFuture.supplyAsync(() -> {
            return "hello async";
        });
    }
    ```
   
4. **Package:** `./mvnw package`

5. **Run Jar:** `java -jar target/sample-app-quarkus-1.0.0-SNAPSHOT-runner.jar`
    
    Runner jar is not a uber-jar. Dependencies exists inside `target/lib`.

6. **Metrics:** http://0.0.0.0:8080/metrics (or) http://0.0.0.0:8080/metrics/application for custom metrics.        
    
    6.1 Add dependency
    
    ```
    <dependency>
      <groupId>io.quarkus</groupId>
      <artifactId>quarkus-smallrye-metrics</artifactId>
    </dependency>
    ```
   
    6.2 Add annotations: `@Counted` / `@Timed` / `@Guage`
    
     
        


