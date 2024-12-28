## application.properties

In Spring Boot, the application.properties (or application.yml) file is used for configuring the application's settings.

It serves as the central location where we can define various properties and configurations related to the application’s behavior, such as database settings, server configuration, logging, and many other aspects of your Spring Boot application.

### Database Configuration

``spring.datasource.url=jdbc:mysql://localhost:3306/campus`` 

``spring.datasource.username=root``

``spring.datasource.password=****``

This value tells Hibernate to automatically adjust the database schema to match the application's entity classes. If a new field is added to an entity, Hibernate will add the corresponding column to the database. It does not drop or modify existing columns or tables

``spring.jpa.hibernate.ddl-auto=update``

This dialect is optimized for MySQL 8.x. It ensures that Hibernate generates SQL statements that are compatible with MySQL 8.x's syntax and features.

``spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MYSQL8Dialect``

### Server Configuration

``server.port=8080``

``
In Spring Boot, the application.properties (or application.yml) file is used for configuring the application's settings. It serves as the central location where you can define various properties and configurations related to the application’s behavior, such as database settings, server configuration, logging, and many other aspects of your Spring Boot application.

Key Uses of application.properties:
Configuring Database Connections: You can define the connection details for your database, including the URL, username, password, and other JPA or Hibernate configurations.

Example:

properties
Copy code
spring.datasource.url=jdbc:mysql://localhost:3306/mydb
spring.datasource.username=root
spring.datasource.password=root
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
Server Configuration: You can customize the server’s port, context path, and other web server settings. This is useful for running the application on a different port or customizing the web context.

Example:

properties
Copy code
server.port=8081
server.servlet.context-path=/myapp``
