# **MaidEase: Use Cases**

---

## **UC-01: User Registers (Customer or Maid)**
**Actor:** New User  
**Goal:** Create an account on MaidEase.

### **Flow**
1. User opens the **Register** page.  
2. Selects role: **customer** or **maid**.  
3. Enters details: email, full name, phone number, password.  
4. System checks the data and makes sure the email is not already used.  
5. System saves the new user in the database with the selected role.  
6. User is now ready to log in.

### **If Something Goes Wrong**
- Email already exists or data is invalid, so the system shows a clear error message.

---

## **UC-02: User Logs In**
**Actor:** Customer or Maid  
**Goal:** Log in and access the app.

### **Flow**
1. User opens the **Login** page.  
2. Enters email and password.  
3. System checks if the user exists and the password is correct.  
4. If correct, the system creates an access token and a refresh token.  
5. Tokens are returned to the frontend and stored.  
6. User is redirected to their dashboard.

### **If Something Goes Wrong**
- Wrong email or password, so the system shows an error and does not log the user in.

---

## **UC-03: Customer Browses Maids**
**Actor:** Customer  
**Goal:** Find a suitable maid.

### **Flow**
1. Customer goes to the **Browse Maids** page.  
2. Frontend calls the backend to get the list of maids.  
3. System returns maids with basic info like name, city, skills, hourly rate, and rating.  
4. Customer can use filters such as city or skills.  
5. Customer clicks on a maid to open the **Maid Detail** page.

### **If No Maids Are Found**
- System returns an empty list, and the UI shows a friendly message to the user.

---

## **UC-04: Customer Creates a Booking**
**Actor:** Customer  
**Goal:** Book a maid for a specific date and time.

### **Flow**
1. Customer opens a maid’s detail page and clicks **Book Now**.  
2. Customer fills the booking form with:  
   - service_type  
   - booking_date  
   - time_slot  
   - notes (optional)  
3. Frontend validates the form and sends the booking data to the backend.  
4. System creates a new record in the `bookings` table with status **pending**.  
5. System returns the created booking to the frontend.  
6. Booking appears in the customer’s **My Bookings** list.

### **If Something Goes Wrong**
- Data is invalid or missing, so the system returns a validation error and the booking is not created.

---

## **UC-05: Maid Manages Booking Requests**
**Actor:** Maid  
**Goal:** Accept, reject, or complete bookings.

### **Flow**
1. Maid goes to the **My Bookings** page.  
2. Frontend requests bookings where this maid is assigned.  
3. System returns a list of bookings with status (pending, accepted, completed, canceled).  
4. For a **pending** booking, maid can:  
   - Accept the booking (status becomes **accepted**)  
   - Reject or cancel the booking (status becomes **canceled**)  
5. After the work is done, maid marks the booking as **completed**.  
6. System updates the booking status in the database.

### **If Something Goes Wrong**
- If someone who is not the assigned maid tries to update the booking, the system rejects the request.

---

## **UC-06: Customer Writes a Review**
**Actor:** Customer  
**Goal:** Share feedback about a completed booking.

### **Flow**
1. Customer opens the **My Bookings** page and looks at completed bookings.  
2. For a completed booking, customer clicks **Write Review**.  
3. Customer enters:  
   - rating (1 to 5)  
   - comment (optional)  
4. Frontend validates the data and sends it to the backend.  
5. System creates a new review linked to the booking, customer, and maid.  
6. System recalculates and updates the maid’s average rating.  

### **If Something Goes Wrong**
- If the booking is not completed or already has a review, the system does not allow a new review.

---

## **UC-07: User Updates Their Profile**
**Actor:** Customer or Maid  
**Goal:** Update personal details and, for maids, service-related details.

### **Flow**
1. User opens the **User Profile** page.  
2. Frontend loads current profile data from the backend.  
3. User edits fields like full name, phone number, city, and for maids, bio, skills, experience, and hourly rate.  
4. Frontend passes the updated data through the payload validator so only allowed fields are sent.  
5. Backend updates the user in the database.  
6. Frontend shows the updated profile to the user.

### **If Something Goes Wrong**
- If data is invalid or a restricted field (like email) is sent, the system returns a validation error and does not update the profile.

---
