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

@Autowired

@RestController

@Bean

@EnableAutoConfiguration

## REQUEST HANDLING AND CONTROLLER ANNOTATIONS

@Controller

@RestController
  -   @RestController = @Controller + @ResponseBody 

@RequestMapping

  -  @GetMapping

  -  @PutMapping
  
  -  @PostMapping
    
  -  @PatchMapping
    
  -  @DeleteMapping
    
@RequestParam

@PathVariable

@RequestBody






@ResponseBody
@ModelAttribute
