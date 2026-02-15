# 🎬 Book My Ticket

<p align="center">
  <strong>A Full-Stack Movie Ticket Booking Application built with Java and Spring Boot</strong>
</p>

<p align="center">
  A complete movie booking platform with user authentication, OTP verification,
  movie and theatre management, seat selection, online payments and QR-based tickets.
</p>

<p align="center">
  <a href="https://github.com/shravyasrao/Book-My-Ticket">
    <img src="https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github" alt="GitHub Repository">
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Java-17-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java 17">
  <img src="https://img.shields.io/badge/Spring%20Boot-4.0.0-6DB33F?style=for-the-badge&logo=springboot&logoColor=white" alt="Spring Boot">
  <img src="https://img.shields.io/badge/Spring%20MVC-6DB33F?style=for-the-badge&logo=spring&logoColor=white" alt="Spring MVC">
  <img src="https://img.shields.io/badge/Thymeleaf-005F0F?style=for-the-badge&logo=thymeleaf&logoColor=white" alt="Thymeleaf">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL">
  <img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" alt="Redis">
  <img src="https://img.shields.io/badge/Hibernate-59666C?style=for-the-badge&logo=hibernate&logoColor=white" alt="Hibernate">
  <img src="https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white" alt="Maven">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Razorpay-Payment%20Gateway-0C2451?style=for-the-badge&logo=razorpay&logoColor=white" alt="Razorpay">
  <img src="https://img.shields.io/badge/Cloudinary-Image%20Storage-3448C5?style=for-the-badge&logo=cloudinary&logoColor=white" alt="Cloudinary">
  <img src="https://img.shields.io/badge/ZXing-QR%20Code-000000?style=for-the-badge" alt="ZXing">
  <img src="https://img.shields.io/badge/JavaMail-Email%20Service-0078D4?style=for-the-badge" alt="JavaMail">
</p>

---

## 📌 Overview

**Book My Ticket** is a full-stack movie ticket booking web application developed using **Java 17, Spring Boot, Thymeleaf, MySQL and Redis**.

The application provides separate workflows for **Users and Administrators**.

Users can register, verify their email using OTP, browse movies, select theatres and shows, choose available seats, make online payments through Razorpay and receive QR-based booking tickets.

Administrators can manage movies, theatres, screens, seats, shows and users through the administrative functionality of the application.

The backend follows a layered architecture using **Controllers, Services and Repositories**, with **Spring Data JPA and Hibernate** handling database persistence.

---

## ✨ Features

### 👤 User Features

- 🔐 User registration and authentication
- 📧 Email-based OTP verification
- 🎬 Browse movies
- 🏢 Browse theatres
- 🕐 View available shows
- 💺 Real-time seat selection
- 🎟️ Movie ticket booking
- 💳 Razorpay online payment integration
- 📱 QR-code ticket generation for entry validation
- 📩 Email notifications via JavaMailSender

### 🛠️ Admin Features

- 🔑 Admin authentication
- 🎬 Movie management
- 🏢 Theatre management
- 🖥️ Screen management
- 💺 Seat layout management
- 🕐 Show and show-time management
- 👥 User management
- 🚫 User blocking/unblocking
- 🖼️ Movie and theatre image management (Cloudinary)

---

## 🏗️ Application Architecture

```text
                         ┌─────────────────────────┐
                         │        Web Browser       │
                         │      HTML / CSS / UI     │
                         └────────────┬────────────┘
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │      Thymeleaf View     │
                         │    Server-Side UI       │
                         └────────────┬────────────┘
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │    Controller Layer     │
                         │   Request Handling      │
                         └────────────┬────────────┘
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │      Service Layer      │
                         │    Business Logic       │
                         └────────────┬────────────┘
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │    Repository Layer     │
                         │     Spring Data JPA     │
                         └────────────┬────────────┘
                                      │
                         ┌────────────┴────────────┐
                         ▼                         ▼
                  ┌───────────────┐         ┌───────────────┐
                  │     MySQL     │         │     Redis     │
                  │   Database    │         │ Data / Cache  │
                  └───────────────┘         └───────────────┘
```

### 🔗 External Services & Integrations

```text
                    ┌─────────────────────────┐
                    │   Spring Boot Backend   │
                    └────────────┬────────────┘
                                 │
          ┌──────────────────────┼──────────────────────┐
          │                      │                      │
          ▼                      ▼                      ▼
    ┌────────────┐         ┌────────────┐        ┌─────────────┐
    │  Razorpay  │         │ Cloudinary │        │ JavaMail /  │
    │  Payments  │         │   Images   │        │    SMTP     │
    └─────┬──────┘         └────────────┘        └─────────────┘
          │
          ▼
    Online Payment
          │
          ▼
    ┌──────────┐
    │   ZXing  │
    │ QR Codes │
    └──────────┘
```

### 🎟️ Booking Workflow

```text
 
┌──────────────────┐
│ User Registration│
└────────┬─────────┘
         ▼
┌──────────────────┐
│  OTP Verification│
└────────┬─────────┘
         ▼
┌──────────────────┐
│      Login       │
└────────┬─────────┘
         ▼
┌──────────────────┐
│  Browse Movies   │
└────────┬─────────┘
         ▼
┌──────────────────┐
│ Select Theatre   │
└────────┬─────────┘
         ▼
┌──────────────────┐
│   Select Show    │
└────────┬─────────┘
         ▼
┌──────────────────┐
│   Select Seats   │
└────────┬─────────┘
         ▼
┌──────────────────┐
│      Booking     │
└────────┬─────────┘
         ▼
┌──────────────────┐
│ Razorpay Payment │
└────────┬─────────┘
         ▼
┌──────────────────┐
│ Payment Verify   │
└────────┬─────────┘
         ▼
┌──────────────────┐
│ Booking Confirmed│
└────────┬─────────┘
         ▼
┌──────────────────┐
│   QR Ticket      │
└──────────────────┘
```

### 📧 OTP Verification

User registration includes email-based OTP verification, sent using `JavaMailSender`.

```text
User Registration → Generate OTP → Send OTP via Email
       → User Enters OTP → Verify OTP
       → Email Verified → Account Activated
```

### 💳 Razorpay Payment Integration

```text
User Selects Seats → Create Booking → Create Payment Order
       → Razorpay Checkout → Payment Completed → Verify Payment
       → Confirm Booking → Generate Ticket
```

> ⚠️ Never commit Razorpay API keys, database passwords, SMTP passwords or other secrets to the repository.

### 📱 QR Ticket Generation

QR codes are generated with **ZXing** for fast entry validation.

```text
Successful Booking → Generate Ticket Information → Create QR Code
       → Attach QR to Ticket → Ticket Verification
```

### ☁️ Cloudinary Image Management

Movie and theatre images are uploaded to Cloudinary to keep them off the application server.

```text
Admin → Upload Movie / Theatre Image → Cloudinary
       → Image URL → Application → Display Image
```

### 🧩 Core Domain Model

```text
                         ┌──────────────┐
                         │     User     │
                         └──────┬───────┘
                                ▼
                         ┌──────────────┐
                         │   Booking    │
                         └──────┬───────┘
                    ┌───────────┼───────────┐
                    ▼                       ▼
              ┌───────────┐           ┌───────────┐
              │   Show    │           │  Payment  │
              └─────┬─────┘           └───────────┘
             ┌──────┴───────┐
             ▼              ▼
        ┌─────────┐    ┌─────────┐
        │  Movie  │    │ Screen  │
        └─────────┘    └────┬────┘
                            ▼
                       ┌─────────┐
                       │ Theatre │
                       └────┬────┘
                            ▼
                         ┌──────┐
                         │ Seat │
                         └──────┘
```

---

## 🛠️ Technology Stack

### 💻 Backend

| Technology | Purpose |
|---|---|
| Java 17 | Core programming language |
| Spring Boot 4.0.0 | Application framework |
| Spring MVC | Web request handling |
| Spring Data JPA | Database access |
| Hibernate | ORM |
| Spring Validation | Input validation |
| Spring Mail | Email / OTP functionality |
| Spring Data Redis | Redis integration |

### 🎨 Frontend

| Technology | Purpose |
|---|---|
| Thymeleaf | Server-side rendering |
| HTML5 | Page structure |
| CSS3 | Styling |
| Bootstrap | UI components / responsive styling |

### 🗄️ Database & Storage

| Technology | Purpose |
|---|---|
| MySQL | Relational database |
| Hibernate | ORM / persistence |
| Redis | Data / caching layer |
| Cloudinary | Cloud image storage |

### 🔌 Integrations

| Technology | Purpose |
|---|---|
| Razorpay | Online payments |
| JavaMailSender | Email / OTP delivery |
| ZXing | QR-code generation |
| Cloudinary | Movie/theatre image hosting |

### 🔧 Development Tools

- Git & GitHub
- Maven (with Maven Wrapper)
- Lombok

---

## 📂 Project Structure

```text
Book-My-Ticket/
│
├── .mvn/
│   └── wrapper/
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── jsp/
│   │   │           └── book/
│   │   │
│   │   └── resources/
│   │       ├── static/
│   │       ├── templates/
│   │       └── application.properties
│   │
│   └── test/
│
├── .gitattributes
├── .gitignore
├── bmt-expl.txt
├── mvnw
├── mvnw.cmd
├── pom.xml
└── README.md
```

---

## ⚙️ Prerequisites

Before running the project, install:

- Java 17
- MySQL 8.x
- Redis
- Git
- Maven (or use the bundled Maven Wrapper)

You'll also need accounts / credentials for:

- Razorpay (payment gateway)
- Cloudinary (image storage)
- An SMTP / email provider (for OTP delivery)

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/shravyasrao/Book-My-Ticket.git
cd Book-My-Ticket
```

### 2. Configure MySQL

Create the required MySQL database and set your connection details in `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/book_my_ticket
spring.datasource.username=YOUR_USERNAME
spring.datasource.password=YOUR_PASSWORD
```

### 3. Configure Redis

Make sure Redis is running locally, or point the app at your Redis instance:

```properties
spring.data.redis.host=localhost
spring.data.redis.port=6379
```

### 4. Configure Email (OTP)

Set your SMTP credentials for OTP delivery via JavaMailSender:

```properties
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=YOUR_EMAIL
spring.mail.password=YOUR_APP_PASSWORD
```

### 5. Configure Razorpay

Add your Razorpay key ID and secret (as environment variables or application properties) — never hardcode these.

### 6. Configure Cloudinary

Add your Cloudinary cloud name, API key and API secret for movie/theatre image uploads.

> 🔒 Never commit SMTP passwords, Razorpay keys, Cloudinary secrets, or any other credentials to `application.properties`, source code, README files, or Git history.

---

## ▶️ Run the Application

**macOS / Linux**
```bash
./mvnw spring-boot:run
```

**Windows**
```bash
mvnw.cmd spring-boot:run
```

**Using a system-installed Maven**
```bash
mvn spring-boot:run
```

---

## 🔨 Build the Application

```bash
./mvnw clean package
```

Windows:
```bash
mvnw.cmd clean package
```

Or with system Maven:
```bash
mvn clean package
```

---

## 🧪 Testing

```bash
./mvnw test
```

Windows:
```bash
mvnw.cmd test
```

---

## 🔐 Security Considerations

The project includes several application-level mechanisms:

- Role-based Admin/User functionality
- OTP-based email verification
- Input validation via Spring Validation
- Server-side payment verification (Razorpay signature check)
- Persistence via JPA/Hibernate
- External media storage via Cloudinary

### Recommended Production Hardening

- 🔑 Strong password hashing (e.g. BCrypt)
- 🛡️ CSRF protection
- 🔒 Secure session management
- ⏱️ OTP expiration
- 🚦 OTP rate limiting
- 🔐 Centralized secrets management
- 🌐 HTTPS everywhere
- 🧱 Secure HTTP headers
- 💳 Payment webhook verification
- 💺 Concurrency-safe seat locking
- 📝 Centralized logging
- 📊 Monitoring and alerting
- 🔍 Regular security testing

---

## 🧠 Key Technical Concepts Demonstrated

- Object-oriented design in Java
- Spring Boot layered architecture (Controller → Service → Repository)
- Spring Data JPA & Hibernate ORM
- MySQL relational modeling
- Redis for caching/session data
- Thymeleaf server-side rendering
- Email/OTP verification flows
- Payment gateway integration (Razorpay)
- QR code generation (ZXing)
- Cloud-based image storage (Cloudinary)
- Maven-based build and dependency management

---

## 📈 Development Highlights

**Backend**
- Designed a layered Spring Boot application
- Implemented controller-service-repository separation
- Integrated Spring Data JPA, Hibernate, MySQL and Redis

**Authentication**
- User registration with email OTP verification
- Admin/User role separation

**Booking System**
- Movie browsing, theatre selection, show selection, seat selection, and booking processing

**Payments**
- Razorpay order creation, checkout, and signature verification

**Ticketing**
- QR-code generation for booking confirmation

**Media**
- Cloudinary integration for movie/theatre images

---

## 🔮 Future Improvements

- [ ] REST API layer
- [ ] React.js frontend
- [ ] JWT authentication
- [ ] Refresh-token based auth
- [ ] Advanced seat-locking mechanism
- [ ] Automatic seat-reservation expiry
- [ ] Booking cancellation & refunds
- [ ] Razorpay payment webhooks
- [ ] Unit & integration testing
- [ ] CI/CD pipeline
- [ ] Docker containerization
- [ ] Cloud deployment (AWS/Azure/GCP)
- [ ] Application monitoring & centralized logging
- [ ] API documentation with Swagger / OpenAPI

---

## 📖 Documentation

Additional project explanation and implementation notes are available in [`bmt-expl.txt`](./bmt-expl.txt).

---

## 👩‍💻 Author

**Shravya S Rao**
Full-Stack Developer

Core interests: Java · Spring Boot · React.js · Full-Stack Development · SQL · Cloud Technologies · Software Engineering

- GitHub: [github.com/shravyasrao](https://github.com/shravyasrao)
- Project Repository: [github.com/shravyasrao/Book-My-Ticket](https://github.com/shravyasrao/Book-My-Ticket)

---

## ⭐ Support

If you found this project useful or interesting, consider giving the repository a ⭐.
