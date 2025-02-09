# Product Details Showing System - Spring Boot REST API

# Description
This project is a Spring Boot REST API for managing Categories and Products with CRUD operations. It follows Spring Data JPA for database interactions and supports pagination and sorting for product retrieval. The API is designed to be scalable, efficient, and follows best practices in RESTful API development.ent.

# Features
- ✔️ Category Management (Create, Read, Update, Delete)
- ✔️ Product Management (Create, Read, Update, Delete)
- ✔️ One-to-Many Relationship (Category → Products)
- ✔️ Pagination & Sorting for fetching products
- ✔️ Spring Data JPA with MySQL for persistence
- ✔️ Annotation-based Configuration (No XML)

# Tech Stack
- Spring Boot (Backend framework)
- Spring Web (REST API development)
- Spring Data JPA & Hibernate (ORM for database interaction)
- MySQL (Relational database)
- Lombok (Reduces boilerplate code)
- Postman (For API testing)

# Project Setup & Installation
## 1. Clone the Repository
```sh
git clone https://github.com/nikhip1/Nimap_MachineTest.git
cd Nimap_MachineTest
```




## 2. Configure Database
- Update application.properties with your MySQL credentials:
```properties
spring.application.name=machineTest

# Spring Datasource Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/machinetest_db
spring.datasource.username=root
spring.datasource.password=
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# Hibernate Properties
spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

## 3. Build & Run the Application
- Using Maven:
```sh
mvn spring-boot:run
```


# API Endpoints
## Category APIs
| Method | Endpoint             | Description          |
|--------|----------------------|----------------------|
| POST   | /api/categories      | Add a new category   |
| GET    | /api/categories      | Get all categories   |
| GET    | /api/categories/{id} | Get category by ID   |
| PUT    | /api/categories/{id} | Update category      |
| DELETE | /api/categories/{id} | Delete category      |


## Product APIs
| Method | Endpoint                            | Description              |
|--------|-------------------------------------|--------------------------|
| POST	 | /api/products	                   | Add a new product        |
| GET	 | /api/products	                   | Get all products         |
| GET	 | /api/products/{id}	               | Get product by ID        |
| PUT    | /api/products/{id}	               | Update product           |
| DELETE | /api/products/{id}                  | Delete product           | 

# Pagination & Sorting
To fetch products with pagination & sorting, use query parameters:

```sh
GET /api/products?page=0&size=7&sort=price,asc
```

- page → Page number (default: 0)
- size → Number of items per page (default: 7)
- sort → Sorting criteria (e.g., price, asc for ascending order)

# Database Schema
## Category Table
| Column | Type   | Constraints                 |
|--------|--------|-----------------------------|
| id	 | Long	  | Primary Key, Auto Increment |
| name   | String | Not Null                    |
	
## Product Table
| Column	  | Type   | Constraints                       |
|-------------|--------|-----------------------------------|
| id	      | Long   | Primary Key, Auto Increment       |
| name	      | String | Not Null                          |
| description | String |	                               |
| price	      | Double | Not Null                          |
| category_id | Long   | Foreign Key (References Category) |

# Testing the API
- 1.Use Postman to test the endpoints.
- 2.Import the Postman collection (if provided).
- 3.Send requests to verify all functionalities.

# Contributing
  Contributions are welcome! Feel free to fork the repository and submit a pull request.

