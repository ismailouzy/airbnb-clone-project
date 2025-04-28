# **Airbnb Clone - Backend API**  

A scalable Django-based backend for an Airbnb-like booking platform, featuring user authentication, property listings, bookings, payments, and reviews. Built with modern web development best practices.  

---

## **📌 Feature Breakdown**  

✅ **User Management** – Registration, authentication, and profile management  
✅ **Property Listings** – Create, update, and search vacation rentals  
✅ **Booking System** – Reserve properties with check-in/check-out dates  
✅ **Payments Integration** – Secure transaction handling  
✅ **Reviews & Ratings** – User feedback system  
✅ **Optimized Database** – PostgreSQL with efficient querying  

---

## **🛠 Technology Stack**  

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

## **🗄 Database Design**  

### **🔑 Key Entities**  

#### **1. Users**  
- `id` (Primary Key)  
- `username` (Unique identifier)  
- `email` (Verified, unique)  
- `password` (Encrypted)  
- `role` (Host/Guest)  

**Relationships**:  
- One-to-Many with **Properties** (A user can list multiple properties)  
- One-to-Many with **Bookings** (A user can make multiple bookings)  

---

#### **2. Properties**  
- `id` (Primary Key)  
- `title` (Property name)  
- `price_per_night` (Decimal)  
- `host_id` (Foreign Key → Users)  
- `location` (Geo-coordinates)  

**Relationships**:  
- Many-to-One with **Users** (Each property belongs to one host)  
- One-to-Many with **Bookings** (A property can have multiple bookings)  
- One-to-Many with **Reviews** (A property can receive multiple reviews)  

---

#### **3. Bookings**  
- `id` (Primary Key)  
- `property_id` (Foreign Key → Properties)  
- `guest_id` (Foreign Key → Users)  
- `check_in` / `check_out` (Dates)  
- `total_price` (Calculated field)  

**Relationships**:  
- Many-to-One with **Users** (Each booking belongs to one guest)  
- Many-to-One with **Properties** (Each booking references one property)  
- One-to-One with **Payments** (Each booking has one payment)  

---

#### **4. Reviews**  
- `id` (Primary Key)  
- `property_id` (Foreign Key → Properties)  
- `author_id` (Foreign Key → Users)  
- `rating` (1-5 scale)  
- `comment` (Text)  

**Relationships**:  
- Many-to-One with **Users** (Each review written by one user)  
- Many-to-One with **Properties** (Each review belongs to one property)  

---

#### **5. Payments**  
- `id` (Primary Key)  
- `booking_id` (Foreign Key → Bookings)  
- `amount` (Decimal)  
- `status` (Pending/Completed/Refunded)  
- `payment_method` (Stripe/PayPal/etc.)  

**Relationships**:  
- One-to-One with **Bookings** (Each payment processes one booking)  

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

## **📚 API Security**  

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
## **📚 CI/CD Pipeline**  

## **🐳 Docker Setup**  

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
