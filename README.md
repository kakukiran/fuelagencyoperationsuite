# ⛽ Fuel Agency Operation Suite - Fuel Pro 🚀

## Overview

**Fuel Pro** is a comprehensive software solution designed to streamline and automate the operations of a cylinder distribution agency. This system enhances efficiency in managing customer bookings, cylinder inventory tracking, order processing, supplier coordination, and financial transactions. By integrating various functionalities, the suite ensures smooth operations, reduces manual workload, minimizes errors, and improves customer service.

---
## 💡 Key Features

### 1️⃣ Customer Management Module
- **Customer Registration & ID Generation**: Register new customers with unique Consumer IDs  
-  **Profile Management**: Update customer details (address, contact, service status)  
- **Account Activation/Deactivation**: Easily manage connection status  
-  **Automated Email Notifications**: Send alerts for registration, profile updates, and account changes  


### 2️⃣ Supplier Management Module
-  **Supplier Registration & ID Generation**: Add new suppliers with unique tracking IDs  
-  **Profile Management**: Edit and maintain supplier information  
-  **Deactivation & Removal**: Maintain an up-to-date supplier list  
-  **Automated Notifications**: Email alerts on supplier changes and updates  

### 3️⃣ Cylinder Management Module
-  **Cylinder Registration & Tracking**: Log cylinder details including weight, type, and current status  
-  **Return & Status Updates**: Track returned cylinders and update availability  
-  **Refilling & Restocking**: Monitor cylinder inventory and manage refills  
-  **Stock Monitoring & Alerts**: Automatic low-stock alerts and restocking notifications  


### 4️⃣ Booking Module
- **Booking Rules & Limits**: Enforces 30-day booking gaps and max 6 cylinders/year per customer  
- **Payment Mode Selection**: Allows flexible payment options during booking  
- **Automated Billing**: Generates itemized bills with surcharges for over-limit bookings  


### 5️⃣ Report Management Module
- **Customer Booking Insights**: Identify high-frequency customers for analytics  
- **Stock Monitoring**: Real-time cylinder availability and usage tracking  
- **Cylinder Reports**: Filter reports by cylinder type, availability, and movement  
- **Inactive Customer Reports**: Spot and manage dormant or inactive customer accounts  

---
## 🛠️ Technologies Used

- **Backend**: Java, Spring Boot (Spring Data JPA, RESTful Web Services)  
- **Database**: MySQL  
- **Frontend**: Thymeleaf  
- **Security**: Spring Security  
- **Build Tool**: Maven

  ---

## 🚀 Installation & Configuration

### Step 1: Database Setup
Create the required MySQL database:

```sql
CREATE DATABASE fuel_booking_db;
```

### Step 2: Configure Application

Update your database configuration in `src/main/resources/application.properties`:

```properties
# application.properties
spring.datasource.url=jdbc:mysql://localhost:3306/fuel_pro_db
spring.datasource.username=fueladmin
spring.datasource.password=Secure@123

```

### Step 3: Booking Module Setup

Configure booking rules in your `application.properties`:

```properties
# Special configuration for booking rules
booking.rules.min-days-between=30
booking.rules.yearly-limit=6
booking.rules.surcharge-percentage=20
```

### Step 4: Email Configuration

Set up email notifications by adding the following to your `application.properties`:

```properties
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=your@gmail.com
spring.mail.password=apppassword
spring.mail.properties.mail.smtp.auth=true
spring.mail.properties.mail.smtp.starttls.enable=true
```
### Step 5: Build & Run

To build and run the project, use the following commands:

```bash
mvn clean install
mvn spring-boot:run
```

---

## 🔧 Initial Data Population (Using Postman)

### Create Admin User

Send a `POST` request to create an admin user:

```http
POST http://localhost:8080/api/users
Content-Type: application/json

{
  "firstName": "kiran",
  "lastName": "kaku",
  "email": "kirankaku09@gmail.com",
  "phone": "4394568692",
  "address": "234 Main Street, Malborne",
  "connectionType": "DOMESTIC",
  "connectionStatus": "ACTIVE",
  "role": "ADMIN"
}
```

---

## 🌐 System Workflows

### Customer Journey
- Registration → Email verification → First booking  
- Subsequent bookings with rule validation  
- Payment processing → Delivery tracking  

### Admin Operations
- Inventory management → Supplier coordination  
- Booking approvals → Exception handling  
- Report generation → Business decisions  


