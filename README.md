# **Airbnb Clone - Backend API**  

A scalable Django-based backend for an Airbnb-like booking platform, featuring user authentication, property listings, bookings, payments, and reviews. Built with modern web development best practices.  

---

## **📌 Features**  

✅ **User Management** – Registration, authentication, and profile management  
✅ **Property Listings** – Create, update, and search vacation rentals  
✅ **Booking System** – Reserve properties with check-in/check-out dates  
✅ **Payments Integration** – Secure transaction handling  
✅ **Reviews & Ratings** – User feedback system  
✅ **Optimized Database** – PostgreSQL with efficient querying  

---

## **🛠 Tech Stack**  

| Category       | Technologies Used |
|---------------|------------------|
| **Backend**   | Django, Django REST Framework |
| **Database**  | PostgreSQL |
| **API**       | REST + GraphQL |
| **Auth**      | JWT (JSON Web Tokens) |
| **Async Tasks** | Celery (for background jobs) |
| **Caching**   | Redis |
| **DevOps**    | Docker, GitHub Actions (CI/CD) |
| **Docs**      | OpenAPI (Swagger) |

---

## **🚀 Quick Setup**  

### **Prerequisites**  
- Python 3.10+  
- PostgreSQL  
- Docker (optional)  

### **Installation**  

1. **Clone the repository**  
   ```bash
   git clone https://github.com/your-username/airbnb-clone.git
   cd airbnb-clone
   ```

2. **Set up a virtual environment**  
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: `venv\Scripts\activate`
   ```

3. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure environment variables**  
   Rename `.env.example` to `.env` and update PostgreSQL credentials:  
   ```
   DATABASE_URL=postgres://user:password@localhost:5432/airbnb_clone
   SECRET_KEY=your-django-secret-key
   ```

5. **Run migrations**  
   ```bash
   python manage.py migrate
   ```

6. **Start the development server**  
   ```bash
   python manage.py runserver
   ```
   The API will be available at: `http://localhost:8000/api/`

---

## **📚 API Documentation**  

### **GraphQL Playground**  
🔗 Explore queries at: `http://localhost:8000/graphql/`  

### **Key Endpoints**  

| Feature       | Endpoint                | Methods |
|--------------|------------------------|---------|
| **Users**    | `/api/users/`          | GET, POST |
| **Auth**     | `/api/auth/login/`     | POST |
| **Properties** | `/api/properties/`   | GET, POST, PUT, DELETE |
| **Bookings** | `/api/bookings/`       | GET, POST |
| **Payments** | `/api/payments/`       | POST |
| **Reviews**  | `/api/reviews/`        | GET, POST |

---

## **🐳 Docker Setup (Alternative)**  

1. **Build and run containers**  
   ```bash
   docker-compose up --build
   ```
2. **Apply migrations**  
   ```bash
   docker-compose exec web python manage.py migrate
   ```

---

## **👥 Team Roles & Responsibilities**  

This project follows a structured team approach to ensure efficient development and maintenance. Below are the key roles and their responsibilities:  

### **1. Backend Developer**  
- Designs and implements API endpoints using Django REST Framework  
- Develops core business logic for user management, bookings, and payments  
- Integrates authentication (JWT) and authorization systems  
- Collaborates on database schema design  

### **2. Database Administrator (DBA)**  
- Designs and optimizes PostgreSQL database schema  
- Implements indexes and query optimizations  
- Manages data migrations and backups  
- Ensures data integrity and security  

### **3. DevOps Engineer**  
- Configures Docker containers for development and production  
- Implements CI/CD pipelines using GitHub Actions  
- Manages deployment to cloud platforms (AWS/GCP)  
- Sets up monitoring and logging systems  

### **4. QA Engineer**  
- Writes unit and integration tests (PyTest)  
- Conducts API testing (Postman, automated tests)  
- Performs security and performance testing  
- Maintains test coverage reports  

### **5. Technical Lead**  
- Oversees architecture decisions  
- Conducts code reviews  
- Coordinates between team members  
- Manages technical debt and roadmap  

### **6. Product Manager**  
- Defines feature requirements  
- Prioritizes development tasks  
- Gathers user feedback  
- Maintains project documentation  

---

## **🤝 Contributing**  

Contributions are welcome! Follow these steps:  
1. Fork the repository  
2. Create a new branch (`git checkout -b feature/your-feature`)  
3. Commit changes (`git commit -m "Add your feature"`)  
4. Push to the branch (`git push origin feature/your-feature`)  
5. Open a Pull Request  

---

### **📬 Contact**  
For questions or feedback, open an issue or reach out to [ismailouzal@gmail.com].  
