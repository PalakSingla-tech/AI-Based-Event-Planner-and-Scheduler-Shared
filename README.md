# 🌟 AI-Based Event Planner & Schedule

> **An Intelligent Platform for Automated Event Management, Budget Prediction, and Vendor Coordination.**

## 📖 Overview
**AuroraEvents** is a full-stack web application designed to streamline the chaotic process of event planning. By integrating **Google Gemini AI**, the platform offers intelligent venue recommendations and accurate budget predictions based on user inputs. It connects users with professional event planners, automates booking workflows, manages payments via **Razorpay**, and provides real-time analytics for administrators.

This project solves the complexity of manual coordination, lack of price transparency, and vendor tracking issues common in the event industry.

---

## 🚀 Key Features

### 🤖 AI-Powered Assistance
* **Smart Recommendations:** Users describe their event (e.g., "Outdoor wedding in Mumbai for 200 guests"), and the AI suggests the best-matched planners.
* **Budget Predictor:** AI estimates a detailed cost breakdown (Venue, Catering, Decor) based on guest count and theme.
* **Content Generation:** Auto-generates professional descriptions for event listings.

### 👤 User Dashboard
* **Planner Discovery:** Filter planners by City, Specialization (Wedding, Corporate, Birthday), and Rating.
* **Seamless Booking:** Check availability, book specific dates, and track status (Pending -> Confirmed).
* **Payments:** Secure payment integration (Razorpay) with transaction history logs.
* **Review System:** Rate and review planners after event completion.

### 🛡️ Admin Dashboard
* **Analytics Hub:** Visual charts showing Total Revenue, Active Bookings, and User Growth.
* **CRUD Operations:** Manage Users, Planners, and Events directly.
* **Enquiry Management:** Reply to user queries directly from the dashboard.

---

## 🛠️ Technology Stack

| Layer | Technology |
| :--- | :--- |
| **Frontend** | React.js, Tailwind CSS |
| **Backend** | Java (JDK 21+), Spring Boot 3.3.5 |
| **Database** | MySQL (Spring Data JPA) |
| **AI Engine** | Google Gemini API |
| **Security** | BCrypt (Password Hashing) |
| **Payments** | Razorpay (Test Mode) |


---
---

## ⚙️ Installation & Setup

### Prerequisites
* Java JDK 21 or higher
* Node.js & npm
* MySQL Server

### 1. Database Setup
Create a database in MySQL Workbench:
```sql
CREATE DATABASE eventmate;
### 2. Backend Configuration
Navigate to `backend/src/main/resources/application.properties` and paste the following configuration. 

**Note:** You must replace `YOUR_MYSQL_USERNAME`, `YOUR_MYSQL_PASSWORD`, and `YOUR_GOOGLE_AI_KEY` with your actual credentials.

```properties
spring.application.name=AuroraEvents
server.port=8080

# ========== DATABASE CONFIG ==========
spring.datasource.url=jdbc:mysql://localhost:3306/eventMate
# REPLACE THESE WITH YOUR DATABASE CREDENTIALS
spring.datasource.username=YOUR_MYSQL_USERNAME
spring.datasource.password=YOUR_MYSQL_PASSWORD
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# ========== JPA / HIBERNATE CONFIG ==========
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
spring.jpa.properties.hibernate.format_sql=true

# ========== CORS CONFIG (Allow Frontend) ==========
spring.web.cors.allowed-origins=http://localhost:5173
spring.web.cors.allowed-methods=GET,POST,PUT,DELETE,OPTIONS
spring.web.cors.allowed-headers=*
spring.web.cors.allow-credentials=true

# ========== AI CONFIG (Google Gemini) ==========
# REPLACE THIS WITH YOUR GEMINI API KEY
gemini.api.key=YOUR_GOOGLE_AI_KEY

# ========== BOOKING REMINDER CONFIG ==========
booking.reminder.days.advance=7
booking.reminder.cron=0 0 9 * * ?

