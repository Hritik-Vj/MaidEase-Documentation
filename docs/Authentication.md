# **Authentication & Authorization Overview**

---

## **Authentication**

MaidEase uses a **JWT-based authentication system** with both **Access Tokens** and **Refresh Tokens**.  
This ensures secure session handling between the React frontend and the FastAPI backend.

When a user logs in, the backend generates:

- **Access Token** (short lifespan)
- **Refresh Token** (long lifespan)

Both tokens are returned to the frontend and stored in **localStorage**.

All protected API calls must include the Access Token in:

```
Authorization: Bearer <access_token>
```

---

## **Authentication Flow**

1. ### **User Registration**
   Users register with:
   - email  
   - full_name  
   - phone_number  
   - role (**customer** or **maid**)  
   - password  

   Backend stores passwords using **Argon2 hashing**.

2. ### **Login**
   - User submits email + password  
   - Backend verifies credentials  
   - Backend returns:
     - **access_token**
     - **refresh_token**
     - **token_type: bearer**
   - Frontend stores tokens using `setTokens()`.

3. ### **Accessing Protected Routes**
   - Axios interceptor attaches the Access Token automatically  
   - Backend validates token using `python-jose`  
   - User identity is extracted from token payload (`user_id`, `role`)

4. ### **Automatic Token Refresh**
   When Access Token expires:
   - Axios sends request to `/auth/refresh`
   - Backend verifies refresh token  
   - New Access Token is issued  
   - Frontend updates localStorage  

5. ### **Logout**
   - Frontend clears both tokens  
   - User session ends  

---

## **Authentication Flow Diagram**

![Auth Flow Diagram](Auth_flow.png)

---

# **Authorization (RBAC — Role-Based Access Control)**

MaidEase uses **role-based authorization**.  
Users have one of two roles defined in the database:

- **customer**
- **maid**

---

## **Permission Summary**

| **Feature / Action** | **Customer** | **Maid** | 
|-----------------------|:------------:|:--------:
| **Register / Login** | ✅ | ✅ |  |
| **View Maid Profiles** | ✅ | ❌ | 
| **Create / Manage Maid Profile** | ❌ | ✅ | 
| **Create Booking** | ✅ | ❌ | 
| **View Bookings** | ✅ | ✅ | 
| **Accept / Reject Booking** | ❌ | ✅ |
| **Cancel Booking** | ✅ | ✅ | 
| **Mark Booking Completed** | ❌ | ✅ | 
| **Post Review** | ✅ | ❌ | 
| **View Reviews** | ✅ | ❌ | 

