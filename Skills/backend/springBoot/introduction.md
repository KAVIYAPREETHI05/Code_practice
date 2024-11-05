## SPRING BOOT

Spring Boot is an open-source framework designed to simplify the development of Java-based applications, particularly those built on the Spring Framework.
It provides a range of features and conveniences that allow developers to create stand-alone, production-grade Spring applications quickly and easily, without needing to configure a lot of boilerplate code.


### Controller

The Controller is part of the presentation layer that handles incoming HTTP requests, processes them, and returns appropriate responses. 

It acts as an intermediary between the client (usually a web front-end) and the service layer.

- Handle Requests: Controllers map HTTP requests to specific handler methods based on the request URL and HTTP method (GET, POST, PUT, DELETE, etc.).
- Process Data: They can also perform data validation and formatting before sending it to the service layer.
- Return Responses: Controllers return the results of operations back to the client, typically in JSON or XML format.
```java
@RestController
@RequestMapping("/api/v1/employees")
public class EmployeeController {

    @Autowired
    private EmployeeService employeeService;

    @GetMapping
    public List<Employee> getAllEmployees() {
        return employeeService.getAllEmployees();
    }
}

```
### Service

The Service layer is responsible for containing the business logic of the application.

It coordinates between the controller and the repository, encapsulating the logic that may involve multiple repository calls or other business rules.

- Business Logic: Services contain the core business logic and validation.
- Transaction Management: They manage transactions, ensuring that a series of operations either complete successfully or roll back.
- Data Processing: Services can also transform data between different formats or structures before sending it to the controller or the repository.

```java
@Service
public class EmployeeService {

    @Autowired
    private EmployeeRepository employeeRepository;

    public List<Employee> getAllEmployees() {
        return employeeRepository.findAll();
    }

    public Employee saveEmployee(Employee employee) {
        return employeeRepository.save(employee);
    }
}

```
### Repository

The Repository is part of the data access layer responsible for interacting with the database. 
It abstracts the data access logic and provides methods to perform CRUD (Create, Read, Update, Delete) operations.

- Data Access: Repositories define methods for accessing data, such as saving an entity, retrieving data by ID, finding all records, and deleting entities.
- Spring Data JPA: Spring provides an easy way to create repositories using Spring Data JPA, which eliminates the need for boilerplate code.

```java
@Repository
public interface EmployeeRepository extends JpaRepository<Employee, Long> {
    List<Employee> findByLastName(String lastName);
}
```

### Model

The Model represents the data of the application. It defines the structure of the data that will be used in the application, often corresponding to database tables.

In Spring, models are usually represented as Java classes annotated with JPA annotations.

- Data Representation: The model encapsulates the data attributes and their relationships.
- Data Validation: It may contain validation rules to ensure data integrity.

```java
@Entity
@Table(name = "employees")
public class Employee {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private long id;

    @Column(name = "first_name")
    private String firstName;

    @Column(name = "last_name")
    private String lastName;

    @Column(name = "email_id")
    private String emailId;

    // Getters and Setters
}

```
Aspect | Model | Controller | Service | Repository|
-------|-------|------------|---------|-------------|
purpose|Represents the application's data structure.|Handles incoming HTTP requests and responses.|Contains business logic and application rules.|Manages data access and CRUD operations.
layer|Data layer (part of MVC)|Presentation layer (part of MVC)|	Service layer (often between Controller and Repository)|Data access layer.	
annotations|@Entity, @Table, @Column, @Id	|@RestController, @Controller, @RequestMapping	|@Service|@Repository	
responsibilities|Defining data attributes and relationships; validates data.|Routing requests to the appropriate service methods and returning responses.		|Coordinating business operations, calling repositories, and processing data.|Interacting with the database; defining query methods.	
example methods|Getters and Setters for data fields.	|@GetMapping, @PostMapping	|	getAllEmployees(), saveEmployee(), etc.|findAll(), save(), deleteById(), etc.
direct interaction|Interacts with the Repository layer (via Service).|Interacts with the Service layer.		|Interacts with both Controller (to receive data) and Repository (to fetch/save data).|Interacts with the database (CRUD operations).	



**JpaRepository** provides built-in methods for performing standard Create, Read, Update, and Delete (CRUD) operations without needing to write boilerplate code. 
