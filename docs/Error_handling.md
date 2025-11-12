# **Edge Cases and Error Handling**

## **Overview**

This section explains how **MaidEase** handles common user and system issues to ensure smooth functionality for both **customers** and **maids**.  
From login errors to booking conflicts, the system provides clear feedback to users and prevents unexpected behavior.

---

## **1. Login and Access Problems**

- **Problem:** User tries to log in without entering an email or password.  
  **Solution:** The system displays a message saying *“Email and password are required.”*

- **Problem:** User enters an incorrect email or password.  
  **Solution:** The system responds with *“Invalid email or password.”*

- **Problem:** A deactivated or deleted user tries to log in.  
  **Solution:** The system shows *“Your account has been deactivated.”*

- **Problem:** An unauthenticated user tries to access restricted pages (e.g., Bookings or Profile).  
  **Solution:** The system redirects to the login screen with an *“Access denied”* message.

- **Problem:** A customer attempts to access maid-only features (like updating availability).  
  **Solution:** The system shows *“You don’t have permission to perform this action.”*

---

## **2. Booking and Scheduling Issues**

- **Problem:** Customer selects a time slot when the maid is already booked.  
  **Solution:** The system notifies the customer with *“Selected time slot is unavailable. Please choose another.”*

- **Problem:** Customer tries to confirm a booking without selecting a service or time.  
  **Solution:** The system prompts *“Please select a service and time before proceeding.”*

- **Problem:** A maid receives overlapping bookings.  
  **Solution:** The system prevents the new booking and displays *“You already have a booking for this time.”*

- **Problem:** Customer tries to cancel a booking that has already been completed.  
  **Solution:** The system blocks the request with *“Completed bookings cannot be canceled.”*

- **Problem:** Maid tries to accept a booking already confirmed by another maid.  
  **Solution:** The system displays *“This booking is no longer available.”*

---

## **3. Profile and Data Management**

- **Problem:** Maid saves a profile without filling all required fields (like skills or hourly rate).  
  **Solution:** The system highlights missing fields with *“Please complete all required details.”*

- **Problem:** User uploads an unsupported file format or an oversized image.  
  **Solution:** The system shows *“Invalid file format or file size too large.”*

- **Problem:** Maid adds overlapping time slots in availability.  
  **Solution:** The system alerts *“Time slots cannot overlap.”*

- **Problem:** Logged-out user attempts to edit their profile.  
  **Solution:** The system redirects to the login page with a warning message.

---

## **4. Review and Feedback**

- **Problem:** Customer tries to post a review before the booking is completed.  
  **Solution:** The system prevents it and shows *“You can only review completed bookings.”*

- **Problem:** Customer attempts to submit multiple reviews for the same service.  
  **Solution:** The system displays *“You’ve already reviewed this booking.”*

- **Problem:** Maid tries to edit or delete a customer review.  
  **Solution:** The system responds with *“You are not authorized to modify reviews.”*

---

## **5. Notifications and Communication**

- **Problem:** Email or SMS notification fails due to invalid contact information.  
  **Solution:** The system retries once and logs the failure in **CloudWatch** for review.

- **Problem:** User’s device blocks app notifications.  
  **Solution:** The app displays *“Notifications are disabled. Enable them to stay updated.”*

---

## **6. System and Network Issues**

- **Problem:** Network failure or backend downtime occurs.  
  **Solution:** The app shows a friendly message: *“We’re having trouble connecting. Please try again later.”*

- **Problem:** User’s session expires while in use.  
  **Solution:** The system logs the user out and shows *“Session expired. Please log in again.”*

- **Problem:** Unexpected server error (FastAPI internal issue).  
  **Solution:** The system shows *“Something went wrong. Please try again.”* and logs the details for developers.