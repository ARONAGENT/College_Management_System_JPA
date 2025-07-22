# College Management System

[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen.svg)](https://spring.io/projects/spring-boot)
[![Spring Data JPA](https://img.shields.io/badge/Spring%20Data%20JPA-3.x-green.svg)](https://spring.io/projects/spring-data-jpa)
[![Java](https://img.shields.io/badge/Java-21-orange.svg)](https://www.oracle.com/java/)
[![Hibernate](https://img.shields.io/badge/Hibernate-6.x-blue.svg)](https://hibernate.org/)
[![MySQL](https://img.shields.io/badge/MySQL-8.x-blue.svg)](https://www.mysql.com/)
[![Maven](https://img.shields.io/badge/Maven-3.x-red.svg)](https://maven.apache.org/)

## 📋 Project Overview

This Spring Boot application demonstrates comprehensive JPA mappings for a College Management System. It showcases entity relationships using Hibernate and Spring Data JPA, implementing various mapping types including One-to-One, One-to-Many, and Many-to-Many relationships across four main entities.

## 🏗️ System Architecture

The system is built around four core entities that represent a typical college management structure:

- **Admission Records** - Student enrollment and admission details
- **Students** - Student information and academic records
- **Professors** - Faculty information and teaching assignments
- **Subjects** - Course catalog and curriculum management

## 📊 Entity Relationships

### Database Schema Overview
![Database Schema Structure](https://github.com/user-attachments/assets/4606b2ea-d7a2-4a18-83cc-f0dd3a8e2c41)

### Relationship Mappings

#### 1. One-to-One Mapping
**Student ↔ Admission Record**
- Each student has exactly one admission record
- Bidirectional relationship with foreign key constraint

![One-to-One Mapping](https://github.com/user-attachments/assets/bb777f90-f80e-4d24-836e-e30bb59363ae)

#### 2. One-to-Many Mapping
**Professor → Subjects**
- One professor can teach multiple subjects
- Unidirectional relationship from Professor to Subject

![One-to-Many Mapping](https://github.com/user-attachments/assets/05c51504-0550-41df-843c-5706fd494670)

#### 3. Many-to-Many Mappings

**a) Professors ↔ Students**
- Many professors can teach many students
- Junction table for relationship management

![Many-to-Many: Professors-Students](https://github.com/user-attachments/assets/28c10d98-e014-41db-8fc1-3890003b7539)

**b) Students ↔ Subjects**
- Many students can enroll in many subjects
- Junction table for enrollment tracking

![Many-to-Many: Students-Subjects](https://github.com/user-attachments/assets/682c8223-3140-41bf-af30-7d1d38ce3706)

## 🗄️ Database Structure

### Table Overview
![Database Tables Structure 1](https://github.com/user-attachments/assets/316ce69e-1e59-4515-b9ab-b360dba567a0)
![Database Tables Structure 2](https://github.com/user-attachments/assets/685282d9-994b-47a7-9db3-8408a7013d7c)

### Core Tables
- `students` - Student master data
- `professors` - Faculty information
- `subjects` - Course catalog
- `admission_records` - Enrollment details
- `student_subject` - Many-to-many junction table
- `professor_student` - Many-to-many junction table

## 🚀 Getting Started

### Prerequisites

Before running this application, ensure you have the following installed:

- **Java 21** or higher
- **Maven 3.6+**
- **MySQL 8.0+** (Cloud or Local)
- **IntelliJ IDEA** (recommended IDE)
- **DBeaver** (for database management)

### Installation & Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/ARONAGENT/College_Management_System.git
   cd College_Management_System
   ```

2. **Database Configuration**
   
   Update `src/main/resources/application.properties`:
   ```properties
   # Database Configuration
   spring.datasource.url=jdbc:mysql://your-cloud-db-url:3306/college_db
   spring.datasource.username=your-username
   spring.datasource.password=your-password
   spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
   
   # Hibernate Configuration
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect
   spring.jpa.show-sql=true
   spring.jpa.properties.hibernate.format_sql=true
   
   # Server Configuration
   server.port=8080
   ```

3. **Build the Project**
   ```bash
   mvn clean install
   ```

4. **Run the Application**
   ```bash
   mvn spring-boot:run
   ```
   
   Alternative using Java:
   ```bash
   java -jar target/college-management-system-1.0.0.jar
   ```

5. **Access the Application**
   - Application URL: `http://localhost:8080`
   - Database: Connect via MySQL Shell or DBeaver

## 🛠️ Technology Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| **Spring Boot** | 3.x | Application Framework |
| **Spring Data JPA** | 3.x | Data Access Layer |
| **Hibernate** | 6.x | ORM Framework |
| **MySQL** | 8.x | Database |
| **Maven** | 3.x | Build Tool |
| **Java** | 21 | Programming Language |

## 📁 Project Structure

```
src/
├── main/
│   ├── java/
│   │   └── com/example/collegemanagement/
│   │       ├── entity/           # JPA Entities
│   │       ├── repository/       # Data Access Layer
│   │       ├── service/          # Business Logic
│   │       ├── controller/       # REST Controllers
│   │       └── CollegeManagementApplication.java
│   └── resources/
│       ├── application.properties
│       └── data.sql             # Sample data (optional)
└── test/                        # Unit tests
```

## 🔧 Key Features

- **Comprehensive JPA Mappings**: All major relationship types implemented
- **Hibernate Integration**: Advanced ORM features and optimizations
- **Database Agnostic**: Easily configurable for different databases
- **RESTful Architecture**: Clean API design following REST principles
- **Transaction Management**: Proper transaction handling across operations
- **Error Handling**: Robust exception handling and validation

## 📖 API Documentation

The application exposes REST endpoints for managing:

- `/api/students` - Student management
- `/api/professors` - Professor management  
- `/api/subjects` - Subject management
- `/api/admissions` - Admission record management

## 🧪 Testing

Run the test suite:
```bash
mvn test
```

Run with coverage report:
```bash
mvn test jacoco:report
```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Contribution Guidelines
- Follow Java coding conventions
- Write unit tests for new features
- Update documentation as needed
- Ensure all tests pass before submitting

## 👥 Authors

- **[ARONAGENT](https://github.com/ARONAGENT)** - Initial work and project maintainer

## 🙏 Acknowledgments

- Spring Boot team for the excellent framework
- Hibernate team for the powerful ORM
- MySQL for the reliable database system
- Open source community for continuous inspiration

## 📞 Support

If you encounter any issues or have questions:

1. Check the [Issues](https://github.com/ARONAGENT/College_Management_System/issues) page
2. Create a new issue with detailed information
3. Contact the maintainer via GitHub

---

⭐ **Star this repository if you find it helpful!**
