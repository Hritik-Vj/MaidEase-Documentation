# **Use Cases**

This document summarizes the main **use cases** for the **MaidEase application** — a simple web-based platform that helps customers find, book, and manage domestic helpers (maids) efficiently.

The system allows **customers** to browse and book maids for various household services and enables **maids** to manage their bookings, schedules, and service status — all within a unified platform.

---

### **1. User Registration and Login**

**Actors:** Customer, Maid

Both customers and maids can create an account on MaidEase by providing basic details such as **name, email, password, phone number, and user role** (maid or customer).

When a user registers, the system validates their inputs to prevent duplicate emails or invalid entries. The data is securely stored in **PostgreSQL**, where passwords are encrypted before saving.

Once registration is complete, users can **log in** using their credentials. Upon successful authentication, the backend generates a **JWT (JSON Web Token)**, which allows users to access role-specific features.

Customers are redirected to a **service browsing dashboard**, while maids access a **booking management dashboard**. Both can also **update their profiles** to change their name, contact details, or password.

This ensures a secure, role-based login mechanism with persistent sessions and clear separation of access permissions between the two roles.

[![](https://mermaid.ink/img/pako:eNpVkElvwjAQhf-KNYeeAsoC2Q6VSsIqTtBSqQ4Hl0wWKbGR40Bb4L83CRQVn-z33sz35BPsRIzgQ1KI4y5jUpHlKuKkOS90rZr3lvR6z2REV5jmlUJJ3iqU22tk1HkB3bAij5lCMuf7Wt3MoDXPnXUmIV2zAxIlSMgU-2QVPqTm_HDNjek6E0cyllL8QcIOMqFLkeb8pk06bUo3KPPkmwQSY-QqZ0V1C0z_w2d0ihxlW3Dx_kqeyArjXOJOPYTvHebXDh3vocmsoy7omMeNAhqkMo_BTxosalCiLFn7hlMbj0BlWGIEfnONMWF1oSKI-KWZ2zP-IUQJvpJ1MylFnWb3PfW-_cowZ6lk5V2VyGOUgai5At90B263BfwTfIFvWG7fdGzH9IaWblqmp8F3kzLtvu0NXcfTB5bheAPnosFPxzX6tqV7huHojuu4hmFdfgGDOJ9g?type=png)](https://mermaid.live/edit#pako:eNpVkElvwjAQhf-KNYeeAsoC2Q6VSsIqTtBSqQ4Hl0wWKbGR40Bb4L83CRQVn-z33sz35BPsRIzgQ1KI4y5jUpHlKuKkOS90rZr3lvR6z2REV5jmlUJJ3iqU22tk1HkB3bAij5lCMuf7Wt3MoDXPnXUmIV2zAxIlSMgU-2QVPqTm_HDNjek6E0cyllL8QcIOMqFLkeb8pk06bUo3KPPkmwQSY-QqZ0V1C0z_w2d0ihxlW3Dx_kqeyArjXOJOPYTvHebXDh3vocmsoy7omMeNAhqkMo_BTxosalCiLFn7hlMbj0BlWGIEfnONMWF1oSKI-KWZ2zP-IUQJvpJ1MylFnWb3PfW-_cowZ6lk5V2VyGOUgai5At90B263BfwTfIFvWG7fdGzH9IaWblqmp8F3kzLtvu0NXcfTB5bheAPnosFPxzX6tqV7huHojuu4hmFdfgGDOJ9g)

---

### **2. Maid Profile Management**

**Actors:** Maid

After registering, maids can build and maintain their service profile. This profile helps customers understand a maid’s background and decide which service provider suits them best.

The maid profile includes details such as:

* Skills (e.g., Cleaning, Laundry, Babysitting)
* Experience (years in service)
* Availability schedule (days and hours)
* Hourly or per-service rate
* Short bio or description

This information is stored in the **Users table** in PostgreSQL and linked to the maid’s user ID.

Maids can update their profiles anytime — for instance, if they gain new experience, change rates, or update availability.
When a customer browses for maids, these details are fetched dynamically and displayed on the frontend.

The Maid Profile Management feature ensures that customer decisions are based on verified and relevant maid information.

[![](https://mermaid.ink/img/pako:eNpVjstuwjAQRX9lNGtAJCnksahECW1TURUVlUWdLlzshEiOjRybPoB_bzABqV555pyZuXtcK8YxwUKor_WGagPz11xC-yZkadr6A_r9W7gjz7RiMFdlA5n8OBt3Dk3Jy5ZLWGhVVILDgpa841PHUzJhDJSGty2jhkPKDa1E0zmpc2ZkRUXlcCa31nRwdoIHhw5wT5Z0x8EoSKmhn7Th_6xM7s7eA1lu1BfMtFa6M-7dkUdyyXhOwmBp12veNIUV4qdTH52akdMNWFVN9SnczaltjKq5vuTOnPdEZpK1HexhqSuGSUFFw3vYijU91bg_6TmaDa95jkn7ZbygVpgcc3ls57ZUvitVY2K0bSe1suXmuse6oGlFS03ra1dzybieKisNJn408t0WTPb4jYkXRAM_HId-PAqGfuDHPfxpLX88GMejKIyHN4EXxjfhsYe_7q43GAfD2PPCYRiFkef50fEPhjOi-A?type=png)](https://mermaid.live/edit#pako:eNpVjstuwjAQRX9lNGtAJCnksahECW1TURUVlUWdLlzshEiOjRybPoB_bzABqV555pyZuXtcK8YxwUKor_WGagPz11xC-yZkadr6A_r9W7gjz7RiMFdlA5n8OBt3Dk3Jy5ZLWGhVVILDgpa841PHUzJhDJSGty2jhkPKDa1E0zmpc2ZkRUXlcCa31nRwdoIHhw5wT5Z0x8EoSKmhn7Th_6xM7s7eA1lu1BfMtFa6M-7dkUdyyXhOwmBp12veNIUV4qdTH52akdMNWFVN9SnczaltjKq5vuTOnPdEZpK1HexhqSuGSUFFw3vYijU91bg_6TmaDa95jkn7ZbygVpgcc3ls57ZUvitVY2K0bSe1suXmuse6oGlFS03ra1dzybieKisNJn408t0WTPb4jYkXRAM_HId-PAqGfuDHPfxpLX88GMejKIyHN4EXxjfhsYe_7q43GAfD2PPCYRiFkef50fEPhjOi-A)

---

### **3. Browse and Search for Maids**

**Actors:** Customer

Customers can view and search for maids directly from their dashboard after logging in.
The system provides a list of available maids along with their:

* Name and skillset
* Experience level
* Hourly rate or service charge
* Availability schedule

Customers can use **filters** to refine their search results. For example:

* By skill type (e.g., Cleaning, Cooking, Babysitting)
* By experience range
* By price range
* By availability date

When a customer applies these filters, the frontend (React.js PWA) sends a request to the FastAPI backend, which retrieves matching maid profiles from the **PostgreSQL database**.

The goal of this use case is to help customers quickly find the right maid for their specific needs, without unnecessary manual searching or contact.

[![](https://mermaid.ink/img/pako:eNpVkE9vozAQxb_KyGcSBWj4d1iJhKTNKqtNk8NKCz24MIBVg1nbtE2jfPc1hFaqL7bHvzfvjS8kFwWSiJRcvOU1lRr2x6wFs-L0pM39CWazH7BK173SokEJe1Ep2LVPN2o1Pq_T3x22kFBVPwsqC5jBSoo3hfCLskJN7HpkkzTuOn6GLeMapYrg9MI4t2Dz3qFk2OZowUGyYYtfKeP0mXGmz1OPZOyxSY9Icw2HPzGcsC0UHPFfj0qDFrClSseH3STYjIJtOlXhsR9cFByE0pXE0-MeSiFNTp3XrK2-Bd6O2ntjpo3m9TaNCSdKxvETuh-hh3TIMQ2Fhcmjeq7VkMeEnNCHEd2lCVMdp-eb14B8fu7E7UbuZ7ppC1MhFqkkK0hUUq7QIoZr6HAnlwHPiK6xwYxE5lhgSY1vRrL2anQdbf8K0ZBIy94opeir-qtP3xVUY8JoJWnzVZVmDJRr0beaRE6w9MYuJLqQdxLZbjB3fM93wqW7cFwntMjZUI4398Jl4IeLO9f2wzv_apGP0deee-4itG1_4Qd-YNtOcP0PqTbCEQ?type=png)](https://mermaid.live/edit#pako:eNpVkE9vozAQxb_KyGcSBWj4d1iJhKTNKqtNk8NKCz24MIBVg1nbtE2jfPc1hFaqL7bHvzfvjS8kFwWSiJRcvOU1lRr2x6wFs-L0pM39CWazH7BK173SokEJe1Ep2LVPN2o1Pq_T3x22kFBVPwsqC5jBSoo3hfCLskJN7HpkkzTuOn6GLeMapYrg9MI4t2Dz3qFk2OZowUGyYYtfKeP0mXGmz1OPZOyxSY9Icw2HPzGcsC0UHPFfj0qDFrClSseH3STYjIJtOlXhsR9cFByE0pXE0-MeSiFNTp3XrK2-Bd6O2ntjpo3m9TaNCSdKxvETuh-hh3TIMQ2Fhcmjeq7VkMeEnNCHEd2lCVMdp-eb14B8fu7E7UbuZ7ppC1MhFqkkK0hUUq7QIoZr6HAnlwHPiK6xwYxE5lhgSY1vRrL2anQdbf8K0ZBIy94opeir-qtP3xVUY8JoJWnzVZVmDJRr0beaRE6w9MYuJLqQdxLZbjB3fM93wqW7cFwntMjZUI4398Jl4IeLO9f2wzv_apGP0deee-4itG1_4Qd-YNtOcP0PqTbCEQ)

---

### **4. Booking a Maid**

**Actors:** Customer, Maid

This is the core use case of the MaidEase platform. Customers can make bookings with available maids for specific services and time slots.

The booking process involves the following steps:

1. The customer selects a maid from the list.
2. The customer chooses a service type (e.g., Cleaning).
3. The customer selects a **date** and **time slot** (e.g., 10 AM to 12 PM).
4. The customer confirms the booking request.

Once submitted, the system creates a new record in the **Bookings table**, containing:

* Customer ID
* Maid ID
* Service ID
* Selected date and time
* Booking status (default = “pending”)

The maid receives this booking request in her dashboard. She can either **accept** or **reject** it.

* If **accepted**, the status changes to **“accepted.”**
* If **rejected**, the status updates to **“canceled.”**

After completion of the service, the maid marks it as **“completed.”**

This entire flow ensures smooth coordination between customer and maid, without needing third-party communication.

[![](https://mermaid.ink/img/pako:eNptkU9z2jAQxb_Kji5cCINNgv_MtB0wkNAAkwnppXYOqrUGtbZEZTlpC3z3yrJNZzr4ZK1-7-3T7pGkkiEJSZbL93RPlYbVcyLAfJN4q835FW5uPsI0jqpSywIVbDHHVJewppwBFcwU1BtP8bWRTS0fxdFeyhJhRjVa6oUXCNtc6paLLDeLIykyrgqYSvmDix08488Ky46aWWoeL2ipJ09LiBQawxI2-G7IVCoGXHTaEl7ot7wLMrfSRdwZm9foqoQP0HtCwUyl14ILC97H9kHGFPmb6XA9z71lH46WnaQpHswkpDLU93oon84N9lBjp_b-BMu4bf7lwEx8BlpCr7lF1sVoNK3RCT5f00RUpGb8F83SxnlsokeyOORYT0fv8b-tPFpwddWzlV1MV5Zd_9t4vT7bYSM1zziyFlxbcBPPRV0hfbJTnJEwo3mJfWKUBa3P5FjjCTGpCkxIaH4ZZrTKdUIScTa6AxVfpSxIqFVllEpWu_3Fp7JZZ5zuFC0uVWV2iCqSldAkdP3x0LqQ8Eh-kdAZ-QPXG3tucDcauiM36JPfhnLHg3Fw53vB8HbkeMGtd-6TP7avMxiPhoHjeEPP93zHcf3zX9Ha-BQ?type=png)](https://mermaid.live/edit#pako:eNptkU9z2jAQxb_Kji5cCINNgv_MtB0wkNAAkwnppXYOqrUGtbZEZTlpC3z3yrJNZzr4ZK1-7-3T7pGkkiEJSZbL93RPlYbVcyLAfJN4q835FW5uPsI0jqpSywIVbDHHVJewppwBFcwU1BtP8bWRTS0fxdFeyhJhRjVa6oUXCNtc6paLLDeLIykyrgqYSvmDix08488Ky46aWWoeL2ipJ09LiBQawxI2-G7IVCoGXHTaEl7ot7wLMrfSRdwZm9foqoQP0HtCwUyl14ILC97H9kHGFPmb6XA9z71lH46WnaQpHswkpDLU93oon84N9lBjp_b-BMu4bf7lwEx8BlpCr7lF1sVoNK3RCT5f00RUpGb8F83SxnlsokeyOORYT0fv8b-tPFpwddWzlV1MV5Zd_9t4vT7bYSM1zziyFlxbcBPPRV0hfbJTnJEwo3mJfWKUBa3P5FjjCTGpCkxIaH4ZZrTKdUIScTa6AxVfpSxIqFVllEpWu_3Fp7JZZ5zuFC0uVWV2iCqSldAkdP3x0LqQ8Eh-kdAZ-QPXG3tucDcauiM36JPfhnLHg3Fw53vB8HbkeMGtd-6TP7avMxiPhoHjeEPP93zHcf3zX9Ha-BQ)

---

### **5. Viewing and Managing Bookings**

**Actors:** Customer, Maid

Both customers and maids can view and manage their respective bookings through their dashboards.

**Customer View:**

* Customers can see all the bookings they have made, along with the service type, date, and status.
* They can also cancel upcoming bookings if needed (before completion).
* Completed bookings remain listed for review and feedback purposes.

**Maid View:**

* Maids see all assigned or pending bookings.
* They can review customer names, addresses (if provided), service types, and time slots.
* They have the ability to accept or reject new requests.

The system retrieves data dynamically from the **Bookings table** in PostgreSQL.
Each booking record is linked to the corresponding user IDs (for both customer and maid), making it easy to filter results and display relevant information per role.

This use case ensures that both parties have full transparency and control over their bookings, minimizing confusion or scheduling conflicts.

[![](https://mermaid.ink/img/pako:eNpNkV2XmjAQhv_KnFyzHgFXPi7a4-fqrm6tdntR9CKFEWghsUnQtup_bwhol6sM8z7zvpOcScwTJCHZF_wUZ1QoWKy3DPQ3iDZK1zt4ePgAw-hNooAFTyXM2a5RDE1rFH06IIMxldl3TkXSNkemOT4bbs0L_HhtGuO6cRlVUvESxQUm0dccTzAoChhy_jNn2mJJE9y9ly9pnlxg2kqlzFOGCXABK2SJRu5oS02M-1N0s4EalKA3UpW0dFiFFmxQHPP4ZvRkkJneRuWcgeIwoizGAt4OMS_febT6qdHPozoarPFoDFoJjFHRvLilmRvpcyMdxDEelKzDr_EHxvq4xl8VStWqZ0b9Ek2pVIPVXPsnOu7_2c0SkDNYcalSgZvPixZ9btCmeDHFIrq_jPbZC5SZnnXKVdYOTurboO2AhWGW0ZDXff10Emb0iPBFUCYPVCBT9xz1lbbY0mCv0YTVz08skoo8IeGeFhItou-_pHVNzrV8S1SGJW5JqI8J7mlVqC3ZsqvmDpR947wkoRKVJgWv0uw-pzJ5xzlNBS3vf3WmBMWIV0yR0PH7PTOFhGfym4S263ccr-85waPbdVwnsMgfrXL6nX7w6HtBt-faXtDzrhb5a3ztTt_tBrbtdT3f823b8a__ABAL-xo?type=png)](https://mermaid.live/edit#pako:eNpNkV2XmjAQhv_KnFyzHgFXPi7a4-fqrm6tdntR9CKFEWghsUnQtup_bwhol6sM8z7zvpOcScwTJCHZF_wUZ1QoWKy3DPQ3iDZK1zt4ePgAw-hNooAFTyXM2a5RDE1rFH06IIMxldl3TkXSNkemOT4bbs0L_HhtGuO6cRlVUvESxQUm0dccTzAoChhy_jNn2mJJE9y9ly9pnlxg2kqlzFOGCXABK2SJRu5oS02M-1N0s4EalKA3UpW0dFiFFmxQHPP4ZvRkkJneRuWcgeIwoizGAt4OMS_febT6qdHPozoarPFoDFoJjFHRvLilmRvpcyMdxDEelKzDr_EHxvq4xl8VStWqZ0b9Ek2pVIPVXPsnOu7_2c0SkDNYcalSgZvPixZ9btCmeDHFIrq_jPbZC5SZnnXKVdYOTurboO2AhWGW0ZDXff10Emb0iPBFUCYPVCBT9xz1lbbY0mCv0YTVz08skoo8IeGeFhItou-_pHVNzrV8S1SGJW5JqI8J7mlVqC3ZsqvmDpR947wkoRKVJgWv0uw-pzJ5xzlNBS3vf3WmBMWIV0yR0PH7PTOFhGfym4S263ccr-85waPbdVwnsMgfrXL6nX7w6HtBt-faXtDzrhb5a3ztTt_tBrbtdT3f823b8a__ABAL-xo)

---

### **6. Booking Acceptance and Completion**

**Actors:** Maid

Once a maid receives a booking request, she can either **accept** or **reject** it based on her availability.

If accepted, the booking status changes to **“accepted,”** and it appears in the maid’s list of confirmed tasks.
If rejected, the booking is marked as **“canceled.”**

After completing the service, the maid updates the booking status to **“completed.”**
This marks the end of the service flow, allowing the customer to submit feedback afterward.

The **status field** in the Bookings table tracks all these changes:

* pending → accepted → completed
* pending → canceled (if rejected or canceled by customer)

This mechanism ensures clear service progression and prevents duplicate bookings during the same time slot.

[![](https://mermaid.ink/img/pako:eNp9j01TwjAQhv9KZi9egKEt9OugA-XLGfUA48WWQ0y2UGkbTFP8AP67IUV0PJhTdt_3eXd3D0xwhBDSXLyxNZWK3M2Tkug3iBdK10vSbl-TYXxPM07myDDbYUWGQmyycqUbrzVWatkgQ-ON9gPGcKuIkFp_QaZujo0enfRDox7IKP5O0YNUXZHHLacKOVGCXDUm5FfL32gTdyDj_9CIlgzzH3Rktpo0F0Si2Oao9AlqjWSBcpcxPBsnxjiNmzDyZ4SJPtOX7KlBZnFUV0oUKMmDUFma6U1Sff0EkT9TtjmbZ8Z8G49LrjvQgpXMOIQpzStsgaYLeqphf7InoBcsMIFQfzmmtM5VAkl51NyWlk9CFBAqWWtSinq1vuTUZvtRRleSFpeuxJKjjERdKght3_VNCoR7eIfQcvyO7bmeHfSdru3YQQs-tMt2O27Q972g23MsL-h5xxZ8mrlWx3W6gWV5Xc_3fMuy_eMXnUy3Xg?type=png)](https://mermaid.live/edit#pako:eNp9j01TwjAQhv9KZi9egKEt9OugA-XLGfUA48WWQ0y2UGkbTFP8AP67IUV0PJhTdt_3eXd3D0xwhBDSXLyxNZWK3M2Tkug3iBdK10vSbl-TYXxPM07myDDbYUWGQmyycqUbrzVWatkgQ-ON9gPGcKuIkFp_QaZujo0enfRDox7IKP5O0YNUXZHHLacKOVGCXDUm5FfL32gTdyDj_9CIlgzzH3Rktpo0F0Si2Oao9AlqjWSBcpcxPBsnxjiNmzDyZ4SJPtOX7KlBZnFUV0oUKMmDUFma6U1Sff0EkT9TtjmbZ8Z8G49LrjvQgpXMOIQpzStsgaYLeqphf7InoBcsMIFQfzmmtM5VAkl51NyWlk9CFBAqWWtSinq1vuTUZvtRRleSFpeuxJKjjERdKght3_VNCoR7eIfQcvyO7bmeHfSdru3YQQs-tMt2O27Q972g23MsL-h5xxZ8mrlWx3W6gWV5Xc_3fMuy_eMXnUy3Xg)

---

### **7. Review and Rating System**

**Actors:** Customer

After a booking is completed, customers can provide feedback to rate their experience with the maid.
This helps improve quality, builds trust, and creates a transparent reputation system for maids.

Each review includes:

* The **rating** (from 1 to 5 stars)
* A **text comment** describing the experience

When a customer submits a review:

1. The system checks if the booking status is **“completed.”**
2. A new record is inserted into the **Reviews table**, linked to:

   * The **Booking ID**
   * The **Customer ID**
   * The **Maid ID**
3. The maid’s overall rating can be averaged based on all received reviews.

These reviews are displayed on the maid’s profile, helping future customers make better decisions.

[![](https://mermaid.ink/img/pako:eNpVkF1vmzAUhv_KkW9yk0YB2vAhdVICaUvXbVXSTdpML9xwAlbBjoxJ1qX57zMuRKqvju3nOee1j2QjcyQR2VbysCmZ0vCwygSYNadrbfbPcHHxBRY0bhsta1TwY4eigVjWuwo15rCQ8pWL4vnDWlg8puv2peYaVkybO2Ai74wahe652HIJvWGNnj-m8ItVPGcam6EfmOm6beAaRudZo15OOvndKu-wpKlo0ARf4Z7jAbjQsq8beGIvFX6yUrH_8G7oupQHWColVQQxE0Kee_zGIefS5rylD1y8Drem_xAyTcZw_plu843x3BS9fWvtO7rCDas2bWUeaIlRA_M9KlZg_0M9f2f5lP7c5QMKj0pueYVw4LqE72Z8b_ZKapV7mvBmV7G3IaMUn-wevrfwV7oUuTkhY1IonpNoy6oGx8S8oWbdnhw7PCO6xBozEpkyxy1rK52RTJyMt2Pij5Q1ibRqjalkW5TnPq1Nn3BWKFafTxWKHFUsW6FJ5Aa-a7uQ6Ej-ksjxgonrz3w3vPKmrueGY_JmKHc2mYVXgR9OLz3HDy_905j8s3Odycybho7jT_3ADxzHDU7_AYf04Nk?type=png)](https://mermaid.live/edit#pako:eNpVkF1vmzAUhv_KkW9yk0YB2vAhdVICaUvXbVXSTdpML9xwAlbBjoxJ1qX57zMuRKqvju3nOee1j2QjcyQR2VbysCmZ0vCwygSYNadrbfbPcHHxBRY0bhsta1TwY4eigVjWuwo15rCQ8pWL4vnDWlg8puv2peYaVkybO2Ai74wahe652HIJvWGNnj-m8ItVPGcam6EfmOm6beAaRudZo15OOvndKu-wpKlo0ARf4Z7jAbjQsq8beGIvFX6yUrH_8G7oupQHWColVQQxE0Kee_zGIefS5rylD1y8Drem_xAyTcZw_plu843x3BS9fWvtO7rCDas2bWUeaIlRA_M9KlZg_0M9f2f5lP7c5QMKj0pueYVw4LqE72Z8b_ZKapV7mvBmV7G3IaMUn-wevrfwV7oUuTkhY1IonpNoy6oGx8S8oWbdnhw7PCO6xBozEpkyxy1rK52RTJyMt2Pij5Q1ibRqjalkW5TnPq1Nn3BWKFafTxWKHFUsW6FJ5Aa-a7uQ6Ej-ksjxgonrz3w3vPKmrueGY_JmKHc2mYVXgR9OLz3HDy_905j8s3Odycybho7jT_3ADxzHDU7_AYf04Nk)

---

### **8. Booking Cancellation**

**Actors:** Customer, Maid

Sometimes, a booking may need to be canceled before completion — for example, if the customer changes plans or the maid becomes unavailable.

**Cancellation Process:**

* Either the **customer** or **maid** can cancel a booking.
* The system validates that the booking is not already completed.
* The booking status changes to **“canceled.”**
* A cancellation timestamp may be recorded for auditing.

This keeps booking data accurate and prevents confusion between active and canceled jobs.

[![](https://mermaid.ink/img/pako:eNpVkF1vmzAUhv_KkW9yk0YB2vAhdVICaUvXbVXSTdpML9xwAlbBjoxJ1qX57zMuRKqvju3nOee1j2QjcyQR2VbysCmZ0vCwygSYNadrbfbPcHHxBRY0bhsta1TwY4eigVjWuwo15rCQ8pWL4vnDWlg8puv2peYaVkybO2Ai74wahe652HIJvWGNnj-m8ItVPGcam6EfmOm6beAaRudZo15OOvndKu-wpKlo0ARf4Z7jAbjQsq8beGIvFX6yUrH_8G7oupQHWColVQQxE0Kee_zGIefS5rylD1y8Drem_xAyTcZw_plu843x3BS9fWvtO7rCDas2bWUeaIlRA_M9KlZg_0M9f2f5lP7c5QMKj0pueYVw4LqE72Z8b_ZKapV7mvBmV7G3IaMUn-wevrfwV7oUuTkhY1IonpNoy6oGx8S8oWbdnhw7PCO6xBozEpkyxy1rK52RTJyMt2Pij5Q1ibRqjalkW5TnPq1Nn3BWKFafTxWKHFUsW6FJ5Aa-a7uQ6Ej-ksjxgonrz3w3vPKmrueGY_JmKHc2mYVXgR9OLz3HDy_905j8s3Odycybho7jT_3ADxzHDU7_AYf04Nk?type=png)](https://mermaid.live/edit#pako:eNpVkF1vmzAUhv_KkW9yk0YB2vAhdVICaUvXbVXSTdpML9xwAlbBjoxJ1qX57zMuRKqvju3nOee1j2QjcyQR2VbysCmZ0vCwygSYNadrbfbPcHHxBRY0bhsta1TwY4eigVjWuwo15rCQ8pWL4vnDWlg8puv2peYaVkybO2Ai74wahe652HIJvWGNnj-m8ItVPGcam6EfmOm6beAaRudZo15OOvndKu-wpKlo0ARf4Z7jAbjQsq8beGIvFX6yUrH_8G7oupQHWColVQQxE0Kee_zGIefS5rylD1y8Drem_xAyTcZw_plu843x3BS9fWvtO7rCDas2bWUeaIlRA_M9KlZg_0M9f2f5lP7c5QMKj0pueYVw4LqE72Z8b_ZKapV7mvBmV7G3IaMUn-wevrfwV7oUuTkhY1IonpNoy6oGx8S8oWbdnhw7PCO6xBozEpkyxy1rK52RTJyMt2Pij5Q1ibRqjalkW5TnPq1Nn3BWKFafTxWKHFUsW6FJ5Aa-a7uQ6Ej-ksjxgonrz3w3vPKmrueGY_JmKHc2mYVXgR9OLz3HDy_905j8s3Odycybho7jT_3ADxzHDU7_AYf04Nk)

---

### **9. System Monitoring and Maintenance**

**Actors:** System (Automated Processes)

Although this version of MaidEase does not have an admin interface, the system itself performs basic background maintenance to ensure smooth operation.

These maintenance activities include:

* **Regular PostgreSQL database backups** to prevent data loss.
* **Error logging and API monitoring** to detect issues in real time.
* **Indexing key columns** (like `email`, `maid_id`, and `status`) to maintain fast performance.
* Periodic cleanup of old or redundant data to improve efficiency.

The backend (FastAPI) uses structured logging to track important actions like login attempts, bookings, and review submissions.
This ensures stability, scalability, and accountability without needing a separate admin module.

[![](https://mermaid.ink/img/pako:eNo90cFuozAQBuBXGfmcRgFaDBxWSkjSRkrVbKK9LPTg4oFYBRsZW202yruv45BywqP5fg_DmVSKI8lI3aqv6si0ge2-lOCeeXEw7vwODw-_YFHMrVEdM8jhcBoMdvCqpDBKC9nAAhshh_ebW3iQFzvUtdId7LGxLdOwU4NpNB5-b2HBqk_b30HuwbIYA2G-28BWNQMwyWGltSvtsVfa3MHSg1WRH7H6hCUz7IMNCBvJ8RtvbLycyQpHtPJoXeQtMgl_enhrOfhobiVn0vigsXntm5-LPVZKc3hlQhqU17TbZELCmg3GTTqCZw9eipUcrMb7itwCP0QrzOn2KXUtKoGyOo3oxaONQ9xVyIQ0WnCS1awdcEI6dPNfz-R8bS-JOWKHJcncK8ea2daUpJQX53om_yrVkcxo66RWtjn-5Nieu9-2FKzRrPupanTb0rmy0pAsTGjsU0h2Jt8kC6JkGtKYhulTNAujMJ2Qk-sK42mcPiU0nT1GAU0f6WVC_vl7g2kczdIgoDOa0CQIwuTyH0KrvMY?type=png)](https://mermaid.live/edit#pako:eNo90cFuozAQBuBXGfmcRgFaDBxWSkjSRkrVbKK9LPTg4oFYBRsZW202yruv45BywqP5fg_DmVSKI8lI3aqv6si0ge2-lOCeeXEw7vwODw-_YFHMrVEdM8jhcBoMdvCqpDBKC9nAAhshh_ebW3iQFzvUtdId7LGxLdOwU4NpNB5-b2HBqk_b30HuwbIYA2G-28BWNQMwyWGltSvtsVfa3MHSg1WRH7H6hCUz7IMNCBvJ8RtvbLycyQpHtPJoXeQtMgl_enhrOfhobiVn0vigsXntm5-LPVZKc3hlQhqU17TbZELCmg3GTTqCZw9eipUcrMb7itwCP0QrzOn2KXUtKoGyOo3oxaONQ9xVyIQ0WnCS1awdcEI6dPNfz-R8bS-JOWKHJcncK8ea2daUpJQX53om_yrVkcxo66RWtjn-5Nieu9-2FKzRrPupanTb0rmy0pAsTGjsU0h2Jt8kC6JkGtKYhulTNAujMJ2Qk-sK42mcPiU0nT1GAU0f6WVC_vl7g2kczdIgoDOa0CQIwuTyH0KrvMY)