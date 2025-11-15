# 🧹 CleanLink — Product Backlog

## Overview
This backlog defines all major **Epics**, **User Stories**, and **Acceptance Criteria** for the CleanLink app MVP and post-MVP roadmap.  
It covers both customer and cleaner experiences, along with admin and backend functionality.

---

## 🧩 EPIC 1: User Onboarding & Authentication

### User Story 1.1 — Account Creation
**As a** new user  
**I want to** create an account using email, phone, or Google/Apple login  
**So that** I can access the platform securely.  

**Acceptance Criteria:**  
- Users can register with email and password.  
- Users can verify phone number or email.  
- Passwords are stored securely (hashed).  
- Social logins via Google and Apple are supported.  

---

### User Story 1.2 — Login & Logout
**As a** registered user  
**I want to** log in and log out easily  
**So that** I can control my session securely.  

**Acceptance Criteria:**  
- Login supports email/password and social options.  
- Failed login attempts trigger error messages.  
- Successful login redirects to home dashboard.  
- Logout clears session tokens.  

---

### User Story 1.3 — Profile Management
**As a** user  
**I want to** edit my personal info and upload a photo  
**So that** my cleaner knows who they are meeting.  

**Acceptance Criteria:**  
- Users can update name, phone, and photo.  
- Changes are reflected instantly.  
- Validation on email and phone format.  

---

## 🧭 EPIC 2: Location & Cleaner Discovery

### User Story 2.1 — Location Detection
**As a** user  
**I want to** use my current GPS location  
**So that** I can find cleaners near me.  

**Acceptance Criteria:**  
- App requests permission for location access.  
- Automatically shows nearest available cleaners.  
- Users can manually enter an address if needed.  

---

### User Story 2.2 — View Available Cleaners
**As a** user  
**I want to** browse a list of available cleaners  
**So that** I can choose based on price and reviews.  

**Acceptance Criteria:**  
- Cleaners displayed by proximity, price, and rating.  
- Search filters for availability, type of service, and price range.  
- Cleaner cards show name, photo, rate, and star rating.  

---

### User Story 2.3 — Cleaner Profile View
**As a** user  
**I want to** view detailed cleaner profiles  
**So that** I can make an informed choice.  

**Acceptance Criteria:**  
- Cleaner profile includes bio, hourly rate, experience, and reviews.  
- “Book Now” button from profile view.  

---

## 📅 EPIC 3: Booking & Scheduling

### User Story 3.1 — Create Booking
**As a** user  
**I want to** schedule a cleaning service  
**So that** I can have my house cleaned at a convenient time.  

**Acceptance Criteria:**  
- Users can select cleaning type (Standard, Deep, Move-out).  
- Pick date and start time from calendar.  
- Total cost auto-calculates based on hours × rate.  
- Confirmation screen before payment.  

---

### User Story 3.2 — Modify or Cancel Booking
**As a** user  
**I want to** update or cancel my booking  
**So that** I can handle changes in my schedule.  

**Acceptance Criteria:**  
- Users can cancel up to 24 hours before service.  
- Update date/time if cleaner is available.  
- Cleaner notified of changes immediately.  

---

### User Story 3.3 — Cleaner Availability Management
**As a** cleaner  
**I want to** set my work hours and days  
**So that** I only get bookings when I’m available.  

**Acceptance Criteria:**  
- Calendar interface for setting available days.  
- Can block off unavailable dates.  
- Status updates to “Available/Unavailable” in real time.  

---

## 💳 EPIC 4: Payments & Transactions

### User Story 4.1 — Payment Processing
**As a** user  
**I want to** pay securely for my booking  
**So that** I can complete the transaction safely.  

**Acceptance Criteria:**  
- Integrated Stripe payment gateway.  
- Accepts credit/debit and Apple/Google Pay.  
- Displays receipt after successful payment.  
- Refunds processed automatically for canceled jobs.  

---

### User Story 4.2 — Cleaner Earnings
**As a** cleaner  
**I want to** track my completed jobs and earnings  
**So that** I can see my income clearly.  

**Acceptance Criteria:**  
- Dashboard shows total earnings and pending payments.  
- Weekly payout summaries available.  
- History of payments downloadable as CSV.  

---

### User Story 4.3 — Admin Payment Oversight
**As an** admin  
**I want to** monitor all payments and disputes  
**So that** I can ensure accurate records.  

**Acceptance Criteria:**  
- Admin dashboard lists all completed payments.  
- Flags failed or disputed transactions.  

---

## ⭐ EPIC 5: Ratings & Reviews

### User Story 5.1 — Submit Review
**As a** user  
**I want to** rate my cleaner and leave feedback  
**So that** others can see their performance.  

**Acceptance Criteria:**  
- 1–5 star rating system.  
- Optional text comment.  
- Only available after booking completion.  

---

### User Story 5.2 — View Reviews
**As a** user or cleaner  
**I want to** view past reviews  
**So that** I can see reliability and performance.  

**Acceptance Criteria:**  
- Cleaners can see user feedback (read-only).  
- Users can view cleaner ratings before booking.  

---

## 🔔 EPIC 6: Notifications & Messaging

### User Story 6.1 — Booking Alerts
**As a** user  
**I want to** receive notifications for booking updates  
**So that** I stay informed about cleaner arrival.  

**Acceptance Criteria:**  
- Notifications for booking confirmation, cleaner arrival, and completion.  
- Push + SMS support.  

---

### User Story 6.2 — In-App Messaging
**As a** user or cleaner  
**I want to** chat securely about job details  
**So that** we can coordinate easily.  

**Acceptance Criteria:**  
- Real-time messaging within app.  
- Messages stored securely with timestamps.  
- Users cannot share personal contact info for safety.  

---

## 🧼 EPIC 7: Cleaner Onboarding & Verification

### User Story 7.1 — Cleaner Application
**As a** cleaner  
**I want to** apply for a profile and get verified  
**So that** I can start receiving jobs.  

**Acceptance Criteria:**  
- Cleaner form collects ID, photo, experience, rate.  
- Background check process integration (third-party API).  
- Status shown as Pending/Approved/Rejected.  

---

### User Story 7.2 — Cleaner Dashboard
**As a** cleaner  
**I want to** manage my jobs and availability  
**So that** I can stay organized.  

**Acceptance Criteria:**  
- List of accepted, pending, and completed jobs.  
- Option to mark job as completed.  
- Ability to message client directly.  

---

## ⚙️ EPIC 8: Admin Portal & System Management

### User Story 8.1 — Admin Dashboard
**As an** admin  
**I want to** view all users, cleaners, and bookings  
**So that** I can manage the platform efficiently.  

**Acceptance Criteria:**  
- Overview stats: total users, bookings, revenue.  
- CRUD access for user and cleaner profiles.  
- Search and filter capabilities.  

---

### User Story 8.2 — Dispute Handling
**As an** admin  
**I want to** resolve payment and service disputes  
**So that** I can maintain fairness.  

**Acceptance Criteria:**  
- Track flagged bookings.  
- Chat and refund management tools.  
- Record of all dispute resolutions.  

---

## 🔐 EPIC 9: Security & Compliance

### User Story 9.1 — Data Protection
**As a** platform owner  
**I want to** store user data securely  
**So that** the system complies with privacy laws.  

**Acceptance Criteria:**  
- All passwords hashed (bcrypt or Argon2).  
- Payment data stored via Stripe (PCI compliant).  
- Data encryption at rest and in transit.  

---

### User Story 9.2 — Role-Based Access
**As an** admin  
**I want to** control access by roles  
**So that** only authorized users perform sensitive actions.  

**Acceptance Criteria:**  
- Roles: User, Cleaner, Admin.  
- Role-based permissions for CRUD operations.  

---

## 🚀 EPIC 10: Growth & Engagement (Post-MVP)

### User Story 10.1 — Referral Program
**As a** user  
**I want to** refer friends and earn rewards  
**So that** I can get discounts and help the app grow.  

**Acceptance Criteria:**  
- Referral link generation.  
- Rewards automatically applied after referral’s first booking.  

---

### User Story 10.2 — Subscription Cleaning Plans
**As a** user  
**I want to** schedule recurring weekly or monthly cleanings  
**So that** I don’t have to rebook manually.  

**Acceptance Criteria:**  
- Choose plan type (weekly, bi-weekly, monthly).  
- Auto-billing setup.  
- Easy cancellation anytime.  

---

### User Story 10.3 — Loyalty Points
**As a** frequent user  
**I want to** earn points for each booking  
**So that** I can redeem them for discounts.  

**Acceptance Criteria:**  
- Points tracked per booking.  
- Redeemable at checkout.  

---

# ✅ Summary of Epics
| Epic ID | Epic Title | Goal |
|----------|-------------|------|
| 1 | User Onboarding & Authentication | Register, login, and manage profiles |
| 2 | Location & Cleaner Discovery | Find cleaners nearby |
| 3 | Booking & Scheduling | Book and manage cleanings |
| 4 | Payments & Transactions | Secure payments and payouts |
| 5 | Ratings & Reviews | Maintain trust and quality |
| 6 | Notifications & Messaging | Real-time updates and communication |
| 7 | Cleaner Onboarding & Verification | Approve qualified cleaners |
| 8 | Admin Portal & System Management | Internal control and oversight |
 9 | Security & Compliance | Protect data and enforce roles |
| 10 | Growth & Engagement | Encourage retention and referrals |
| 9 | Security & Compliance | Protect data and enforce roles |
| 10 | Growth & Engagement | Encourage retention and referrals |
