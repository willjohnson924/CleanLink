# 🧹 CleanLink — Sprint Plan (Single-Agent in Windsurf)

## Project Goal
Build an MVP version of **CleanLink**, an app that connects users with verified local cleaners for booking, payment, and reviews — within 12 weeks.

---

## ⚙️ Development Framework
- **Methodology:** Agile (2-week sprints)
- **Team Composition:** Single Windsurf AI Agent
- **Environment:**  
  - Frontend: React Native + Next.js  
  - Backend: Node.js (Express) + PostgreSQL  
  - Hosting: AWS or Render  
  - Auth: Firebase Auth  
  - Payments: Stripe API  
  - Maps: Google Maps API  

---

## 🗓 Sprint Schedule Overview

| Sprint | Duration | Focus | Outcome |
|--------|-----------|--------|----------|
| Sprint 1 | Weeks 1–2 | Environment setup & base architecture | Working dev environment, base schemas |
| Sprint 2 | Weeks 3–4 | User onboarding & authentication | User signup, login, profile management |
| Sprint 3 | Weeks 5–6 | Cleaner onboarding & discovery | Cleaner registration + geolocation |
| Sprint 4 | Weeks 7–8 | Booking & payment flow | Full booking and payment pipeline |
| Sprint 5 | Weeks 9–10 | Reviews, notifications & messaging | Ratings + push notifications + chat |
| Sprint 6 | Weeks 11–12 | Testing, QA, and deployment | Polished MVP, deployed to app stores |

---

## 🧩 Sprint 1: Environment & Architecture Setup
**Goal:** Establish the full development foundation.

### Tasks
- Initialize Windsurf workspace.
- Configure **Git repo** and environment files.
- Set up **frontend** (React Native + Next.js).
- Set up **backend** with Express + PostgreSQL ORM (Prisma or Sequelize).
- Integrate Firebase for Auth + Messaging.
- Create base **API folder structure**:
  - `/auth`
  - `/users`
  - `/cleaners`
  - `/bookings`
  - `/payments`
- Define **database schema** based on PRD data model.
- Connect database with test migrations.
- Implement sample CRUD endpoints (e.g., `/users`).

### Deliverables
- Running local environment (frontend + backend).
- Connected database with seeded test data.
- API responding to requests (Postman verification).

### Acceptance Criteria
- All core folders and packages set up successfully.
- `.env` configured for API keys.
- Sample endpoint returns 200 OK.

---

## 🧍 Sprint 2: User Onboarding & Authentication
**Goal:** Implement user registration, login, and profile management.

### Tasks
- Build **Signup & Login** UI screens.
- Integrate **Firebase Authentication** (email, Google, Apple).
- Create **User API endpoints**:
  - POST `/users/signup`
  - POST `/users/login`
  - GET `/users/profile`
  - PUT `/users/profile`
- Store user data in PostgreSQL linked to Firebase UID.
- Implement JWT-based session handling.
- Build “Edit Profile” screen.
- Validate inputs and secure password storage.

### Deliverables
- Fully functional login/signup system.
- Profile management working end-to-end.
- Auth middleware on backend.

### Acceptance Criteria
- User can register and log in successfully.
- Token-based session persists on reload.
- Profile edits reflect immediately in DB.

---

## 🧽 Sprint 3: Cleaner Onboarding & Discovery
**Goal:** Allow cleaners to sign up, verify, and appear in location-based searches.

### Tasks
- Extend `Users` model with `Cleaner` fields.
- Create **Cleaner API endpoints**:
  - POST `/cleaners/register`
  - GET `/cleaners/nearby`
  - PUT `/cleaners/availability`
- Integrate **Google Maps API** for geolocation.
- Build **Cleaner Registration Form** (bio, rate, background check flag).
- Implement **Availability Calendar UI**.
- Build **“Find Cleaners Near Me”** screen (location-based list).

### Deliverables
- Cleaners can register and set availability.
- Users can search for nearby cleaners.
- Map-based results display dynamically.

### Acceptance Criteria
- Search returns cleaners sorted by distance.
- Cleaner data syncs correctly between API and UI.

---

## 📅 Sprint 4: Booking & Payment System
**Goal:** Enable users to create, modify, and pay for bookings.

### Tasks
- Create **Booking API**:
  - POST `/bookings`
  - PUT `/bookings/:id`
  - GET `/bookings/:user_id`
- Implement booking status flow (Pending → Confirmed → Completed).
- Integrate **Stripe Payments API**:
  - Create payment intents.
  - Handle success/failure webhooks.
- Add **Booking Summary** screen.
- Add **Payment Checkout** UI with total price calculation.
- Store transactions in `Payments` table.

### Deliverables
- Working booking + payment pipeline.
- End-to-end booking tested (DB + UI).

### Acceptance Criteria
- User can book, pay, and receive confirmation.
- Payments logged in DB.
- Canceled bookings auto-refund (sandbox test).

---

## ⭐ Sprint 5: Reviews, Notifications & Messaging
**Goal:** Add ratings, push notifications, and basic chat.

### Tasks
- Create **Review API**:
  - POST `/reviews`
  - GET `/reviews/:cleaner_id`
- Build review UI on booking completion.
- Integrate **Firebase Cloud Messaging** for push alerts:
  - Booking updates
  - Payment confirmations
  - Cleaner arrival notifications
- Build **In-App Messaging API**:
  - POST `/messages`
  - GET `/messages/:booking_id`
- Add chat UI per booking thread.

### Deliverables
- Working reviews + chat + notifications.
- Messaging stored and synced via Firebase Realtime DB or WebSockets.

### Acceptance Criteria
- Users receive booking confirmation push.
- Review appears instantly on cleaner profile.
- Chat works in real time.

---

## 🚀 Sprint 6: QA, Testing & Deployment
**Goal:** Finalize, test, and deploy MVP.

### Tasks
- Unit testing (Jest) for APIs.
- End-to-end testing (Cypress or Detox for mobile).
- Fix critical bugs from test feedback.
- Optimize database queries and API latency.
- Add basic analytics (Firebase events).
- Prepare Play Store and App Store assets.
- Deploy backend to AWS or Render.
- Deploy frontend to TestFlight + Android Beta.

### Deliverables
- Stable MVP version live for beta testing.
- Working CI/CD pipeline.
- Documented API endpoints in Markdown.

### Acceptance Criteria
- No major functional or security bugs.
- App runs smoothly across devices.
- CleanLink MVP publicly accessible.

---

## 🧠 Post-MVP Enhancements (Optional Sprints)
| Sprint | Focus | Feature |
|--------|--------|----------|
| 7 | Growth | Referral program, loyalty points |
| 8 | Retention | Subscription-based cleanings |
| 9 | Business | Admin dashboard & analytics |
| 10 | Trust | AI cleaner recommendations (smart matching) |

---

## 🧩 Dependencies
- Stripe account + API keys  
- Firebase (Auth, Messaging)  
- Google Maps API key  
- AWS S3 for media storage  
- Domain + SSL certificate  

---

## 📊 Progress Tracking
**Windsurf Commands / Task Stages:**
- `#start <task>` → begins build of feature  
- `#test <feature>` → run unit or integration test  
- `#review <component>` → review UI output or API logs  
- `#deploy staging` → push to test environment  
- `#ship production` → deploy final MVP  

---

## ✅ Definition of Done (DoD)
- Code reviewed by agent’s test suite.  
- 90%+ test coverage for core features.  
- Database schema and API endpoints documented.  
- Deployed, accessible, and tested by end user.  

---

# 🧾 Summary Timeline (12 Weeks)

| Phase | Sprint | Deliverables |
|--------|---------|--------------|
| **Phase 1:** Setup | 1 | Architecture, DB schema, API base |
| **Phase 2:** Users | 2 | Signup, login, profile |
| **Phase 3:** Cleaners | 3 | Cleaner registration, geolocation |
| **Phase 4:** Core System | 4 | Booking + payment |
| **Phase 5:** Engagement | 5 | Ratings, chat, notifications |
| **Phase 6:** Launch | 6 | QA, deployment, analytic

s |
