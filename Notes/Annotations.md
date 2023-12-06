## Annotations

#### @SpringBootApplication
- This annotation is used to mark the main class of a Spring Boot application.
- It combines three annotations: @Configuration, @EnableAutoConfiguration, and @ComponentScan.

#### 1. Autowired
- In Spring Boot, ```@Autowired``` is used to inject dependencies automatically. 
- This annotation can be applied to fields, methods, or constructors to indicate that Spring should automatically resolve and inject the appropriate beans or components at runtime.

#### 2. @RestController
- This annotation is used to define a controller class. It is a specialization of the @Controller annotation and is typically used in combination with @RequestMapping to handle HTTP requests.

#### 3. @RequestMapping
- This annotation is used to map HTTP requests to specific controller methods. You can use it at the class level and/or method level.

#### 4. @GetMapping, @PostMapping, @PutMapping, @DeleteMapping
- These annotations are shortcuts for @RequestMapping(method = RequestMethod.GET), @RequestMapping(method = RequestMethod.POST), @RequestMapping(method = RequestMethod.PUT), and @RequestMapping(method = RequestMethod.DELETE), respectively.

#### 5. @RequestParam
- This annotation is used to bind a method parameter to a query parameter in the URL.

#### 6. @PathVariable
- This annotation is used to bind a method parameter to a placeholder in the URL.

#### 7. @Entity
- In the context of Spring Data JPA, the @Entity annotation is used to mark a Kotlin class as a JPA entity. JPA (Java Persistence API) is a standard interface for Java objects to interact with relational databases.
- An entity is a lightweight, persistent domain object that represents a table in a relational database. Each instance of the entity corresponds to a row in the table.

#### @Repository:
- The @Repository annotation is used to indicate that a Kotlin class is a Spring Data repository. Spring Data provides a higher-level, more convenient way to interact with data repositories (such as databases).
- Repositories in Spring Data allow you to perform CRUD operations on entities without writing explicit implementations.


#### @Transactional:

- The @Transactional annotation is used to define the scope of a single database transaction. Transactions are crucial for maintaining data consistency in database operations.
- When a method annotated with @Transactional is called, a transaction is started before the method executes, and it's committed if the method completes successfully or rolled back if an exception occurs.