## application.properties

In Spring Boot, the application.properties (or application.yml) file is used for configuring the application's settings.

It serves as the central location where we can define various properties and configurations related to the application’s behavior, such as database settings, server configuration, logging, and many other aspects of your Spring Boot application.

### Database Configuration

It specifies the URL of the MySQL database that the Spring Boot application will connect to.

``spring.datasource.url=jdbc:mysql://localhost:3306/campus`` 


It specifies the username that will be used to authenticate the connection to the MySQL database.

``spring.datasource.username=root``


It specifies the password for the database user.

``spring.datasource.password=****``

This value tells Hibernate to automatically adjust the database schema to match the application's entity classes. If a new field is added to an entity, Hibernate will add the corresponding column to the database. It does not drop or modify existing columns or tables

``spring.jpa.hibernate.ddl-auto=update``

**HIBERNATE**

Hibernate is an Object-Relational Mapping (ORM) framework for Java.

It allows Java developers to interact with relational databases in an object-oriented way, without needing to write SQL queries for common database operations. 

Essentially, Hibernate maps Java objects (entities) to database tables and provides an abstraction layer that simplifies database interactions.

In Hibernate, a Dialect refers to the specific SQL syntax and behavior used by the underlying database. 

A *Hibernate Dialect* is a class that adapts Hibernate’s query generation to the specific features and syntax of the database you’re using.

For example:

- MySQL8Dialect
- postgreSQLDialect
- Oracle12cDialect
- SQLServerDialect

This dialect is optimized for MySQL 8.x. It ensures that Hibernate generates SQL statements that are compatible with MySQL 8.x's syntax and features.

``spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MYSQL8Dialect``

### Server Configuration

This property sets the port on which the embedded web server (like Tomcat, Jetty, or Undertow) will listen for incoming HTTP requests.

``server.port=8080``

This property sets the context path for the application. The context path is the base URL under which your application is hosted. It is essentially a prefix that is added to the root URL.

``server.servlet.context-path=/myapp``

### spring profiles

This property is used to specify the active Spring Profile for the application. Spring Profiles allows us to define different configurations for different environments (e.g., development, production, testing)

``spring.profiles.active=dev``

### Logging configuration

This property controls the logging level for specific loggers or packages in the application.

``logging.level.org.springframework=INFO``

This property sets the logging level specifically for your application’s package (in this case, com.myapp) to DEBUG

``logging.level.com.myapp=DEBUG``
