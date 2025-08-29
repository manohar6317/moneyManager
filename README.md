#  Money Manager –  Java Full Stack Project

A Java Spring Boot + React full-stack web app for personal finance management. Features include secure login (JWT), income & expense tracking, category management, REST API integration, MySQL database, and Excel report generation. Built with Spring Boot, Hibernate, React.js, Vite, Maven, and Bootstrap, this project demonstrates end-to-end full-stack development with a modern tech stack.

---


## Screenshots

**SignUp page**

![Signup Page Screenshot](images/signup.png)

**Login Page**

![Login Page Screenshot](images/login.png)

**Home Page**

![Home Page Screenshot](images/home.png)

**Browse Page**

![Browse Page Screenshot](images/browse.png)

##  Tech Stack

### Backend (Spring Boot)
- **Java 17** – Core backend language  
- **Spring Boot 3** – REST APIs  
- **Spring Security + JWT** – Authentication & authorization  
- **Spring Data JPA (Hibernate)** – ORM for MySQL  
- **MySQL** – Relational database  
- **Maven** – Dependency management & build tool  

### Frontend (React + Vite)
- **React 18** – UI framework  
- **Vite** – Fast development build tool  
- **Axios** – API communication  
- **Bootstrap / CSS** – UI styling  

---

##  Project Structure

```
MoneyManager/
│
├── moneymanager/               # Backend (Spring Boot)
│   ├── src/main/java/...       # Controllers, Services, Entities, Repositories
│   ├── src/main/resources/     # Configs & properties
│   └── pom.xml                 # Maven build file
│
├── moneymanagerwebapp/         # Frontend (React + Vite)
│   ├── src/                    # Components, Pages, Services
│   ├── public/                 # Static assets
│   └── package.json            # Node.js dependencies
│
└── README.md                   # Project documentation
```

---

##  Features

-  User authentication (JWT based login/register)  
-  Track **income & expenses** with categories  
-  Category management (Income / Expense categories)  
-  Export reports to **Excel**  
-  Dashboard with summary view  
-  Responsive UI (Bootstrap + React)  

---

##  Run Guide

This guide will help you run the **backend (Spring Boot + MySQL)** and **frontend (React + Vite)** locally.

---

###  1. Prerequisites

Make sure you have these installed:

- **Java 17+** → [Download](https://adoptium.net/)  
- **Maven 3.8+** → [Download](https://maven.apache.org/)  
- **MySQL 8+** → [Download](https://dev.mysql.com/downloads/)  
- **Node.js 18+** (includes npm) → [Download](https://nodejs.org/)  

Verify installation:
```bash
java -version
mvn -v
mysql --version
node -v
npm -v
```

---

###  2. Database Setup (MySQL)

1. Open MySQL shell / Workbench.
2. Create a new database:
   ```sql
   CREATE DATABASE money_manager;
   ```
3. Create a user (optional, or use `root`):
   ```sql
   CREATE USER 'money_user'@'localhost' IDENTIFIED BY 'password123';
   GRANT ALL PRIVILEGES ON money_manager.* TO 'money_user'@'localhost';
   FLUSH PRIVILEGES;
   ```
4. Update **`moneymanager/src/main/resources/application.properties`**:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/money_manager
   spring.datasource.username=money_user
   spring.datasource.password=password123
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.show-sql=true
   spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
   ```

---

###  3. Run Backend (Spring Boot)

From project root:
```bash
cd moneymanager
mvn spring-boot:run
```

 Backend will start at: **http://localhost:8080**

Logs:
```
Tomcat started on port(s): 8080
Started MoneyManagerApplication in 5.123 seconds
```

---

###  4. Run Frontend (React + Vite)

From project root:
```bash
cd moneymanagerwebapp
npm install   # only first time
npm run dev
```

 Frontend will start at: **http://localhost:5173**

---

###  5. Frontend ↔ Backend Connection

Frontend communicates with backend via **Axios**.  
Update base URL in **`moneymanagerwebapp/src/services/api.js`**:

```javascript
const API_BASE_URL = "http://localhost:8080";
```

---

###  6. Build for Production

#### Backend JAR
```bash
cd moneymanager
mvn clean package
java -jar target/moneymanager-0.0.1-SNAPSHOT.jar
```

#### Frontend Build
```bash
cd moneymanagerwebapp
npm run build
```
Output in `dist/` folder (can be served via Nginx/Apache or linked into backend).

---

###  7. API Endpoints

- `POST /register` → Register new user  
- `POST /login` → Login (JWT auth)  
- `GET /profile` → Get user profile  
- `GET /categories/{type}` → Fetch categories  
- `GET /excel/download/income` → Download income report (Excel)  
- `DELETE /expenses/{id}` → Delete expense  

---

###  8. Common Issues & Fixes

- ❌ **Error: mvn not recognized** → Install Maven and add to PATH.  
- ❌ **MySQL connection refused** → Check DB is running, user/pass correct.  
- ❌ **CORS errors (frontend)** → Enable CORS in backend `config/WebConfig.java`.  
- ❌ **Port already in use** → Kill process on 8080 or change port in `application.properties`:
  ```properties
  server.port=9090
  ```

---

##  Contribution

1. Fork this repository  
2. Create feature branch (`git checkout -b feature-name`)  
3. Commit changes (`git commit -m "Added new feature"`)  
4. Push branch (`git push origin feature-name`)  
5. Create Pull Request  

---

##  License

This project is licensed under the **MIT License**.

---

##  Author

Developed with ❤️ by **[Manohar Draipalli](https://github.com/manohar6317)**  
Feel free to connect and contribute! 
