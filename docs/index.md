# MaidEase : A Home Services Booking Platform

Welcome to the documentation for **MaidEase**, a web app that makes it easy to book and manage home services like cleaning and laundry all in one place.

---

## Why MaidEase?

Booking home services is often a messy, offline process phone calls, unclear pricing, unreliable timing.  
MaidEase brings everything into a single, transparent digital platform where users can **book, track, and review** services easily, while providers can **find consistent work** and manage schedules confidently.

---

## Key Features

-  **Centralized Booking System** - Find, request, and confirm services in just a few clicks.  
-  **Role-based Dashboards** - Tailored interfaces for Customers and Maids.  
-  **Real-time Updates** - Track your booking from “requested” to “completed.”  
-  **Secure Data Management** - Powered by PostgreSQL and FastAPI.  
-  **Modern UX** - Built as a Progressive Web App (PWA) with a smooth, app-like feel.

---

### **Problem Statement**

Finding reliable and trustworthy home service providers can be a significant challenge. The traditional methods of booking often involve manual communication, a lack of transparency, and no standardized way to track services or provide feedback.

Similarly, service providers often struggle with finding consistent work, managing their schedules, and building a verifiable reputation.

---

### **Proposed Solution**

MaidEase addresses these challenges by providing a simple, centralized digital platform. The key features include:

*   A **centralized booking system** for customers to find and book maids.
*   **Role-based dashboards** for both Customers and Maids.
*   **Real-time status updates** for all bookings.
*   Secure data storage in a **PostgreSQL database**.
*   A clean and user-friendly interface built with **React.js**.

---

### **User Roles and Responsibilities**

The system is designed around two core user roles:

#### 1. **Customer**

*   Registers for an account.
*   Browses available maids and their services.
*   Books services for specific dates and times.
*   Cancels and manages existing bookings.
*   Views a complete history of their bookings.
*   Leaves reviews and ratings after a service is completed.

#### 2. **Maid / Service Provider**

*   Registers and creates a professional profile.
*   Lists offered services and sets availability.
*   Accepts or rejects incoming booking requests.
*   Manages a schedule of all upcoming jobs.
*   Updates the status of a job to "completed" upon finishing the work.