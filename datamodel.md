# 🧹 CleanLink — Data Model Documentation

## Overview
The CleanLink data model supports users, cleaners, bookings, payments, and reviews.  
It ensures scalability, security, and efficient matching between cleaners and users.

---

## 🧩 Entity Relationship Diagram (ERD Overview)
**Main Entities:**
- `Users`
- `Cleaners`
- `Bookings`
- `Payments`
- `Reviews`
- `Availability`
- `Addresses`
- `Notifications`

---

## 1. Users Table
Stores information about customers who book cleaning services.

| Field | Type | Description |
|-------|------|--------------|
| `user_id` | UUID (PK) | Unique user identifier |
| `full_name` | VARCHAR(100) | User’s full name |
| `email` | VARCHAR(120) | User’s email (unique) |
| `phone_number` | VARCHAR(20) | Contact number |
| `password_hash` | VARCHAR(255) | Encrypted password |
| `profile_photo_url` | TEXT | Optional profile picture |
| `created_at` | TIMESTAMP | Account creation date |
| `updated_at` | TIMESTAMP | Last update time |
| `is_verified` | BOOLEAN | Whether email/phone is verified |
| `preferred_payment_method` | VARCHAR(50) | e.g., “Stripe”, “ApplePay” |

**Relationships:**
- One-to-many with `Bookings`
- One-to-many with `Reviews`
- One-to-one with `Addresses`

---

## 2. Cleaners Table
Holds cleaner profiles and professional details.

| Field | Type | Description |
|-------|------|--------------|
| `cleaner_id` | UUID (PK) | Unique cleaner identifier |
| `user_id` | UUID (FK) | References `Users.user_id` |
| `bio` | TEXT | Short intro about cleaner |
| `hourly_rate` | DECIMAL(6,2) | Price per hour |
| `rating_average` | DECIMAL(2,1) | Average rating (1–5) |
| `jobs_completed` | INTEGER | Count of completed jobs |
| `is_verified` | BOOLEAN | Passed background check |
| `background_check_status` | VARCHAR(50) | Pending, Passed, Failed |
| `availability_status` | VARCHAR(20) | Online, Offline, Busy |
| `created_at` | TIMESTAMP | Profile creation date |
| `updated_at` | TIMESTAMP | Last updated date |

**Relationships:**
- One-to-many with `Bookings`
- One-to-many with `Reviews`
- One-to-many with `Availability`

---

## 3. Addresses Table
Stores user and cleaner addresses for service coordination.

| Field | Type | Description |
|-------|------|--------------|
| `address_id` | UUID (PK) | Unique address identifier |
| `user_id` | UUID (FK) | References `Users.user_id` |
| `street_address` | VARCHAR(255) | Street name & number |
| `city` | VARCHAR(100) | City name |
| `state` | VARCHAR(50) | State or region |
| `postal_code` | VARCHAR(20) | ZIP or postal code |
| `latitude` | DECIMAL(10,8) | Geolocation latitude |
| `longitude` | DECIMAL(11,8) | Geolocation longitude |
| `created_at` | TIMESTAMP | Created date |
| `updated_at` | TIMESTAMP | Updated date |

---

## 4. Bookings Table
Handles all service booking information.

| Field | Type | Description |
|-------|------|--------------|
| `booking_id` | UUID (PK) | Unique booking identifier |
| `user_id` | UUID (FK) | References `Users.user_id` |
| `cleaner_id` | UUID (FK) | References `Cleaners.cleaner_id` |
| `address_id` | UUID (FK) | Service location |
| `booking_type` | VARCHAR(50) | e.g., Standard, Deep, Move-out |
| `scheduled_date` | DATE | Date of service |
| `start_time` | TIME | Start time |
| `end_time` | TIME | End time |
| `duration_hours` | DECIMAL(3,1) | Length of job |
| `price_total` | DECIMAL(8,2) | Final price |
| `status` | VARCHAR(30) | Pending, Confirmed, Completed, Canceled |
| `notes` | TEXT | Optional user notes |
| `created_at` | TIMESTAMP | Created time |
| `updated_at` | TIMESTAMP | Updated time |

**Relationships:**
- One-to-one with `Payments`
- One-to-one with `Reviews`

---

## 5. Payments Table
Tracks all financial transactions.

| Field | Type | Description |
|-------|------|--------------|
| `payment_id` | UUID (PK) | Unique transaction ID |
| `booking_id` | UUID (FK) | References `Bookings.booking_id` |
| `user_id` | UUID (FK) | References `Users.user_id` |
| `cleaner_id` | UUID (FK) | References `Cleaners.cleaner_id` |
| `amount` | DECIMAL(8,2) | Payment amount |
| `payment_method` | VARCHAR(50) | e.g., Stripe, ApplePay |
| `payment_status` | VARCHAR(20) | Pending, Paid, Refunded |
| `transaction_ref` | VARCHAR(255) | External gateway reference |
| `created_at` | TIMESTAMP | Payment time |

---

## 6. Reviews Table
Stores ratings and written feedback from users about cleaners.

| Field | Type | Description |
|-------|------|--------------|
| `review_id` | UUID (PK) | Unique review identifier |
| `booking_id` | UUID (FK) | References `Bookings.booking_id` |
| `user_id` | UUID (FK) | References `Users.user_id` |
| `cleaner_id` | UUID (FK) | References `Cleaners.cleaner_id` |
| `rating` | DECIMAL(2,1) | Score (1–5) |
| `comment` | TEXT | Written feedback |
| `created_at` | TIMESTAMP | Review date |

---

## 7. Availability Table
Tracks cleaner schedules and availability.

| Field | Type | Description |
|-------|------|--------------|
| `availability_id` | UUID (PK) | Unique availability record |
| `cleaner_id` | UUID (FK) | References `Cleaners.cleaner_id` |
| `day_of_week` | VARCHAR(10) | e.g., Monday, Tuesday |
| `start_time` | TIME | Available from |
| `end_time` | TIME | Available until |
| `is_available` | BOOLEAN | True if active |
| `created_at` | TIMESTAMP | Created date |

---

## 8. Notifications Table
Handles system notifications for both users and cleaners.

| Field | Type | Description |
|-------|------|--------------|
| `notification_id` | UUID (PK) | Unique identifier |
| `user_id` | UUID (FK) | Recipient user |
| `title` | VARCHAR(100) | Notification title |
| `message` | TEXT | Notification body |
| `is_read` | BOOLEAN | True if read |
| `created_at` | TIMESTAMP | Sent time |
| `type` | VARCHAR(30) | e.g., BookingUpdate, PaymentSuccess |

---

## 🔗 Relationships Summary
- **Users ↔ Cleaners:** One-to-one (a cleaner is also a user)  
- **Users ↔ Bookings:** One-to-many  
- **Cleaners ↔ Bookings:** One-to-many  
- **Bookings ↔ Payments:** One-to-one  
- **Bookings ↔ Reviews:** One-to-one  
- **Cleaners ↔ Availability:** One-to-many  
- **Users ↔ Notifications:** One-to-many  

---

## ⚙️ Indexing & Performance
- Index on `user_id`, `cleaner_id`, and `booking_id` for faster joins.  
- Use **PostGIS** or **geospatial indexes** on latitude/longitude fields for efficient location search.  
- Enable **caching** for cleaner search results via Redis.  

---

## 🔐 Security Notes
- All passwords hashed using bcrypt or Argon2.  
- Sensitive data (payments, addresses) encrypted at rest.  
- Use role-based access control (RBAC) for admin and cleaner dashboards.  
- Audit logs for payments and status changes.  

---

## 🧠 Future Data Extensions
- `SubscriptionPlans` table for recurring cleanings.  
- `PromoCodes` table for discounts.
- CleanerCertifications` for credentials and training verification.  
- `ChatMessages` for cleaner-user communication.  
- `CleanerCertifications` for credentials and training verification.  
- `ChatMessages` for cleaner-user communication.  
