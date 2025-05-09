# Spring Boot JPA Mappings - College Management System

## Project Description
This project is a Spring Boot application that demonstrates JPA mappings for a College Management System. It covers the implementation of entity relationships using Hibernate and Spring Data JPA. The system consists of four main tables: Admission Records, Students, Professors, and Subjects, showcasing different types of entity mappings such as One-to-One, One-to-Many, and Many-to-Many relationships. The project also includes database schema structure, table structure, and mapping images for reference.

## Entities and Relationships

### 1. Admission Records
- Represents student admission details
- Maintains relationships with Students and Subjects

### 2. Students
- Stores student information
- One-to-Many relationship with Admission Records
- Many-to-Many relationship with Subjects

### 3. Professors
- Stores professor details
- One-to-Many relationship with Subjects

### 4. Subjects
- Represents courses available in the system
- Many-to-Many relationship with Students
- One-to-Many relationship with Professors

## Images Included
- **Database Schema Structure**: Overview of the database design
  
  ![image](https://github.com/user-attachments/assets/4606b2ea-d7a2-4a18-83cc-f0dd3a8e2c41)
  

- **Database Table Structure**: Details of table columns and relationships
  
 ![07 Student_Professor_subject_record(tables)](https://github.com/user-attachments/assets/316ce69e-1e59-4515-b9ab-b360dba567a0)
![08 Student_Professor_subject_record(tables)](https://github.com/user-attachments/assets/685282d9-994b-47a7-9db3-8408a7013d7c)


- **One-to-One Mapping**: One student have one Admission Record
  
 ![03 OneToOne(one student have one admission Record)](https://github.com/user-attachments/assets/bb777f90-f80e-4d24-836e-e30bb59363ae)
 

- **One-to-Many & Many-to-Many Mapping**:
  
**-i)One to Many Mappings  : One Professor teaches many subjects**

 ![04 one to many (one professor teaches many subjects)](https://github.com/user-attachments/assets/05c51504-0550-41df-843c-5706fd494670)


**ii) Many To Many Mappings-**

**a)Many Professors have many Students**

![05 ManyToMany(many professors have many students)](https://github.com/user-attachments/assets/28c10d98-e014-41db-8fc1-3890003b7539)




**b)many students have many subjects**


![06 ManyToMany(many students have many subjects )](https://github.com/user-attachments/assets/682c8223-3140-41bf-af30-7d1d38ce3706)


## How to Run the Project
1. Clone the repository:
   ```bash
   git clone https://github.com/ARONAGENT/College_Management_System.git
   cd college-management-system
   ```
2. Configure database properties in `application.properties`:
   ```properties
   spring.datasource.url=jdbc:mysql://your-cloud-db-url:3306/college_db
   spring.datasource.username=your-username
   spring.datasource.password=your-password
   spring.jpa.hibernate.ddl-auto=update
   ```
3. Build the project using Maven:
   ```bash
   mvn clean install
   ```
4. Run the application:
   ```bash
   mvn spring-boot:run
   ```
5. Access the MySQL database via MySql Shell

## Prerequisites
- Java 21
- Maven
- IntelliJ IDEA
- MySQL Cloud Database
- DBeaver for database management

## Contributing
Feel free to fork this repository and contribute with pull requests to improve the project.

## License
This project is open-source and available under the MIT License.

