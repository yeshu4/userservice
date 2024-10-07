UserService API
Overview
The UserService is a simple RESTful API built using Spring Boot, MySQL, and Hibernate. It allows basic CRUD operations (Create, Read, Update, Delete) on user data. The API provides endpoints to manage users and retrieve information from the MySQL database.

Features
Add New Users: POST endpoint to add new users to the system.
Get Users: GET endpoints to fetch users by ID and list all users.
Update Users: PUT endpoint to modify existing user information.
Delete Users: DELETE endpoint to remove users by ID.
Unit Testing: Includes test cases for each of the CRUD operations using Spring’s testing framework.
Technologies Used
Java (JDK 17)
Spring Boot 2.5.4
Hibernate ORM 5.4.32
MySQL
Maven (build management)
JUnit 5 (for testing)
H2 Database (for testing purposes)
Prerequisites
Java 17 (or later)
Maven (for build automation)
MySQL (for database management)
Setup Instructions
Clone the repository:

bash
Copy code
git clone https://github.com/yeshu4/userservice.git
Configure MySQL Database:

Update the MySQL connection details in application.properties:
properties
Copy code
spring.datasource.url=jdbc:mysql://localhost:3306/test
spring.datasource.username=root
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL5Dialect
Build the project:

bash
Copy code
mvn clean install
Run the application:

bash
Copy code
mvn spring-boot:run
Access the API:

The API will be available at http://localhost:8080/api/users.
Use the following endpoints:
GET /api/users - Get a list of all users.
GET /api/users/{id} - Get a user by their ID.
POST /api/users - Create a new user (pass user data in JSON format).
PUT /api/users/{id} - Update user details.
DELETE /api/users/{id} - Delete a user by their ID.
Sample API Calls
Create a User:

bash
Copy code
curl -X POST "http://localhost:8080/api/users" -H "Content-Type: application/json" -d '{"name": "John", "email": "john.doe@example.com"}'
Get User by ID:

bash
Copy code
curl -X GET "http://localhost:8080/api/users/1"
Update a User:

bash
Copy code
curl -X PUT "http://localhost:8080/api/users/1" -H "Content-Type: application/json" -d '{"name": "John Updated", "email": "john.updated@example.com"}'
Delete a User:

bash
Copy code
curl -X DELETE "http://localhost:8080/api/users/1"
Running Tests
The project includes unit tests that can be run using Maven:

bash
Copy code
mvn test
License
This project is licensed under the MIT License.

