## SPRING BOOT ANNOTATIONS

In Spring Boot, annotations are a type of metadata that can be added to Java code, classes, methods, or fields to provide additional information.
They are used for a variety of purposes, such as configuring data sources and marking Spring components.


@getter -  Generates getter methods for all fields in the class 

@setter -  Generates setter methods for all fields

@NoArgsConstructor - Generates a no-argument (default) constructor for the class.

```java
public Example() {
}

```

@AllArgsConstructor - Generates a constructor that includes all fields in the class.

```java
public Example(String name, int age) {
    this.name = name;
    this.age = age;
}

```

### Difference between setter and Constructor

|Constructor   | Setter           |
--------------- | -------------
A constructor is a special method used to create and initialize an object when it is instantiated. | A setter (or mutator) method is used to update the value of a private attribute after the object has been created.
Automatically called when an object is created using the new keyword.| Manually called on an object to change its state.
Has the same name as the class and no return type. | Typically starts with the word "set" followed by the attribute name.
Primarily used to set initial values for the object's attributes. |  Used to change the value of an attribute after the object has been instantiated.



@Table -  It is used with JPA (Java Persistence API) to specify the details of the table that will be used for an entity in the database. I

```java
@Entity
@Table(name = "workers")
public class Worker {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private String email;
    // Other fields and getters/setters
}

```

@Entity - It  is used to specify that a class is an entity and is mapped to a database table. An entity represents a table stored in a database, and each entity instance corresponds to a row in that table.

@Id - It  specifies the primary key of an entity. The primary key is a unique identifier for each entity instance.

  -jakarta.persistence.Id
   When we're working with JPA and Hibernate for ORM (Object-Relational Mapping).(sql)
   
  -org.springframework.data.annotation.Id
   When we're using Spring Data to interact with non-relational databases like MongoDB, Cassandra, etc(nosql)

@GeneratedValue - It is used to specify that the value of a primary key should be automatically generated. 

@GenerationType - It defines the different strategies that @GeneratedValue can use to generate the primary key.

**Strategies**

- AUTO: The default strategy. The persistence provider selects an appropriate generation strategy.

- IDENTITY: The persistence provider must assign primary keys for the entity using a database identity column.

- SEQUENCE: The persistence provider must assign primary keys for the entity using a database sequence.

- TABLE: The persistence provider must assign primary keys for the entity using an underlying database table to ensure uniqueness.

@EntityScan - If our class is in a different package from your Spring Boot main application class, you might need to specify the package for entity scanning.

@RequestStatus - To indicate the HTTP status code that should be returned in the response for a specific handler method or exception.

  
@SpringBootApplication

@SpringBootConfiguration

@EnableAutoConfiguration

@ComponentScan

Auto-Configuration Conditions

  @ConditionalOnClass, and @ConditionalOnMissingClass
  
  @ConditionalOnBean, and @ConditionalOnMissingBean
  
  @ConditionalOnProperty
  
  @ConditionalOnResource
  
  @ConditionalOnWebApplication and @ConditionalOnNotWebApplication
  
  @ConditionalExpression
  
  @Conditional


@PathVariable

@RequestBody

@Autowired - It is used for dependency injection. It allows Spring to automatically resolve and inject collaborating beans (components, services, repositories, etc.) into a class. 

@Qualifier - If there are multiple beans of the same type and you want to specify which one to inject, you can use the @Qualifier annotation along with @Autowired

@RestController 

@Bean

@EnableAutoConfiguration

## REQUEST HANDLING AND CONTROLLER ANNOTATIONS

@Controller - It is used to define a class as a Spring MVC controller. It marks the class as a component that can handle incoming HTTP requests and respond accordingly. They typically return view names (for rendering HTML) rather than raw data.

@ResponseBody - It is used to indicate that the return value of a method should be written directly to the HTTP response body, instead of being interpreted as a view name. This is particularly useful for RESTful services that return data in JSON or XML format.

@RestController
  -   @RestController = @Controller + @ResponseBody
    
  -   It is used to define a controller that handles HTTP requests in a RESTful web service and automatically serializes responses into JSON or XML format based on the client's request.

@RequestMapping

  -  @GetMapping -  It specifically maps HTTP GET requests to a method in a controller class. This is typically used to retrieve data from the server.

  -  @PutMapping
  
  -  @PostMapping
    
  -  @PatchMapping
    
  -  @DeleteMapping
    
@RequestParam

@PathVariable






@Body
@ModelAttribute

``Response Entity`` - a ResponseEntity is a class in the ``org.springframework.http`` package that represents the HTTP response, including the status code, headers, and body.

responseBody: The data returned as the body of the HTTP response.

HttpStatus.OK: The HTTP status code indicating success (200).
