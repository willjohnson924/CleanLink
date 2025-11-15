# 🧹 CleanLink — Product Requirements Document (PRD)

## 1. Overview
**Purpose:**  
CleanLink is a mobile and web app that connects users with trusted, local cleaners for home cleaning services. It allows users to book, pay, and rate cleaners in one place.

**Vision:**  
Make finding reliable cleaning help as easy as ordering a ride.

**Goals:**  
- Help users book a verified cleaner in under 5 minutes.  
- Provide cleaners with consistent, local job opportunities.  
- Maintain transparency in pricing, scheduling, and communication.

**Target Users:**  
- Busy professionals and families.  
- Airbnb and rental property owners.  
- Local cleaning professionals.

---

## 2. Key Features

### 2.1. For Users (Customers)
- **User Registration & Login**  
  - Sign up via email, phone, Google, or Apple.  
- **Location-Based Cleaner Search**  
  - Detects location or allows manual address entry.  
  - Displays nearby cleaners with ratings and hourly rates.  
- **Instant Booking**  
  - Choose cleaning type (standard, deep, move-out).  
  - Select date, time, and duration.  
- **Real-Time Availability**  
  - See which cleaners are currently available.  
- **Secure Payment**  
  - Pay in-app via Stripe (credit, debit, or Apple Pay/Google Pay).  
- **Ratings & Reviews**  
  - Rate cleaners and leave feedback after the service.  
- **Job History**  
  - View past and upcoming bookings.  

---

### 2.2. For Cleaners (Service Providers)
- **Profile Setup**  
  - Upload ID, profile photo, and experience details.  
  - Background verification process.  
- **Job Listings Dashboard**  
  - Accept or decline cleaning jobs nearby.  
- **Earnings Tracking**  
  - Weekly payout summaries and balance dashboard.  
- **Schedule Management**  
  - Set available working days and hours.  
- **In-App Messaging**  
  - Chat with clients to clarify job details.  

---

## 3. Technical Requirements

### 3.1. Platform
- **Mobile App:** iOS and Android (React Native recommended).  
- **Web App:** Responsive web platform using React or Next.js.  

### 3.2. Backend
- **Server:** Node.js with Express or NestJS.  
- **Database:** PostgreSQL for structured data (users, bookings, payments).  
- **Hosting:** AWS or Google Cloud Platform.  
- **Payment System:** Stripe for payments and escrow protection.  
- **Location Services:** Google Maps API for address detection and route distance.  
- **Notifications:** Firebase Cloud Messaging for push notifications and SMS updates.  

---

## 4. Design Requirements

### 4.1. User Experience (UX)
- Intuitive 3-step booking process.  
- Clean, modern interface with icons and minimal text.  
- Onboarding walkthrough for first-time users.  

### 4.2. Visual Style (UI)
- Colors: Teal (#00BFA6), White (#FFFFFF), Gray (#F7F7F7).  
- Font: Inter or Poppins.  
- Rounded buttons with clear action text (“Book Now,” “Pay,” “Contact Cleaner”).  

---

## 5. Metrics for Success
| Metric | Target |
|--------|--------|
| Average booking time | < 5 minutes |
| Cleaner acceptance rate | > 85% |
| User satisfaction (rating) | ≥ 4.5 / 5 |
| Repeat bookings | ≥ 30% within 30 days |
| Payment completion rate | 100% secured via Stripe |

---

## 6. Competitive Advantages
- Verified, local-only cleaners (trust-focused).  
- Transparent pricing and rating system.  
- Real-time location-based availability.  
- User loyalty and referral programs.  

---

## 7. Risks & Mitigation
| Risk | Impact | Mitigation |
|------|---------|-------------|
| Cleaner cancellations | High | Add penalties and replacement system |
| Payment issues | Medium | Use escrow and automatic refund policy |
| Low cleaner supply | High | Offer sign-up bonuses and training |
| User trust concerns | High | Require background checks and display verification badge |

---

## 8. Future Enhancements
- Subscription cleaning packages.  
- AI-based cleaner matching (based on ratings, distance, and preferences).  
- Integration with smart locks for keyless entry.  
- Group or corporate cleaning plans.  

---

## 9. Timeline (MVP Plan)
| Phase | Duration | Deliverables |
|-------|-----------|--------------|
| **1. Research & Planning** | 2 weeks | Requirements, user interviews |
| **2. Design** | 3 weeks | UI/UX prototypes |
| **3. Development (MVP)** | 6 weeks | Core features, payment, booking |
| **4. Testing & QA** | 2 weeks | User testing, bug fixes |
| **5. Launch** | 1 week | App Store & Play Store release |
