# 💰 Money Manager – Full Stack Project

A **personal finance management** web application built using **Java Spring Boot (backend)** and **React + Vite (frontend)**.  
It helps users track income, expenses, categories, and download reports.

---

## 🚀 Tech Stack

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

## 📂 Project Structure

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

## ⚡ Features

- 🔐 User authentication (JWT based login/register)  
- 📊 Track **income & expenses** with categories  
- 🗂️ Category management (Income / Expense categories)  
- 📥 Export reports to **Excel**  
- 📈 Dashboard with summary view  
- 🎨 Responsive UI (Bootstrap + React)  

---

## 🛠️ Setup & Run

### 1. Clone Repository
```bash
git clone https://github.com/your-username/money-manager.git
cd money-manager
```

### 2. Run Backend (Spring Boot)
```bash
cd moneymanager
mvn spring-boot:run
```
Backend runs on: **http://localhost:8080**

### 3. Run Frontend (React + Vite)
```bash
cd moneymanagerwebapp
npm install
npm run dev
```
Frontend runs on: **http://localhost:5173**

---

## 🔗 API Endpoints (Examples)

- `POST /register` → Register new user  
- `POST /login` → Login & get JWT token  
- `GET /profile` → Get user profile  
- `GET /categories/{type}` → Get categories  
- `GET /excel/download/income` → Download income Excel  
- `DELETE /expenses/{id}` → Delete expense  

---

## 📦 Build for Production

### Backend JAR
```bash
cd moneymanager
mvn clean package
java -jar target/moneymanager-0.0.1-SNAPSHOT.jar
```

### Frontend Build
```bash
cd moneymanagerwebapp
npm run build
```
Build output in `dist/` folder.

---

## 🤝 Contribution

1. Fork this repository  
2. Create feature branch (`git checkout -b feature-name`)  
3. Commit changes (`git commit -m "Added new feature"`)  
4. Push branch (`git push origin feature-name`)  
5. Create Pull Request  

---

## 📜 License

This project is licensed under the **MIT License**.

---

## 👨‍💻 Author

Developed with ❤️ by **[Your Name](https://github.com/your-username)**  
Feel free to connect and contribute! 🚀
