# **Functional Flow & Use Cases**

---

### **Functional Overview**

The MaidEase platform uses a simple, role-based model to define user interactions. The experience is tailored to the two main roles, **Customer** and **Maid**, with each having a specific set of actions available to them. The entire workflow is designed to be intuitive, centering around the core tasks of booking and managing home services.

---

### **Customer Functional Flow**

1.  **Registration and Login:** New users sign up with a name, email, and password, and select the "Customer" role. After logging in, they are directed to their personal dashboard.

2.  **Browsing for Maids:** Customers can browse a list of available maids, viewing their profiles, skills, and rates to find the right fit for their needs.

3.  **Booking a Service:** The customer selects a maid, a service, and an available date and time. A booking request is then created and sent to the maid.

4.  **Managing Bookings:** The customer dashboard displays the status of all bookings (e.g., "Pending," "Accepted," "Completed"). Bookings can also be canceled from this dashboard.

5.  **Leaving a Review:** Once a job is marked as "Completed," the customer has the option to leave a rating and a review for the service provider.

[![](https://mermaid.ink/img/pako:eNpdj0tPwzAQhP-KtQdOaXGTtnkckEj64AASohUHnB6sZJNaTezKcVqg6n_HNQUkfPJ6vpkdn6BQJUICVaOOxZZrQ9ZpLok992xl7Lwhg8EdSdmjqoUkt-QFa9EZ1IR3JOs7o1rUm29H6tCMpVodOyRPXJQduSGvAo_kWatKNNhd0cyhM7bCBgvjUEumSu3ICvVBFHgFZw6cs7Xmxc4BQtbENjP9T9bcIQuWqXbfoMF_CQsnL9kj8gPa-gdb5yotnfTA5rK0L-BBrUUJScWbDj2wH2v5ZYbTBc_BbLHFHBJ7LbHifWNyyOXZ-vZcvinVQmJ0b51a9fX2N6ffl9zgTPBa8z8EZYk6U700kPh06jIgOcE7JIHvD8f-ZBqHYRDGcRB58AHJKBrSMQ3oKAjpaBJOfP_swafbSodRHNGI-tNgTGkQR9PzF1b_jyk?type=png)](https://mermaid.live/edit#pako:eNpdj0tPwzAQhP-KtQdOaXGTtnkckEj64AASohUHnB6sZJNaTezKcVqg6n_HNQUkfPJ6vpkdn6BQJUICVaOOxZZrQ9ZpLok992xl7Lwhg8EdSdmjqoUkt-QFa9EZ1IR3JOs7o1rUm29H6tCMpVodOyRPXJQduSGvAo_kWatKNNhd0cyhM7bCBgvjUEumSu3ICvVBFHgFZw6cs7Xmxc4BQtbENjP9T9bcIQuWqXbfoMF_CQsnL9kj8gPa-gdb5yotnfTA5rK0L-BBrUUJScWbDj2wH2v5ZYbTBc_BbLHFHBJ7LbHifWNyyOXZ-vZcvinVQmJ0b51a9fX2N6ffl9zgTPBa8z8EZYk6U700kPh06jIgOcE7JIHvD8f-ZBqHYRDGcRB58AHJKBrSMQ3oKAjpaBJOfP_swafbSodRHNGI-tNgTGkQR9PzF1b_jyk)

---

### **Maid Functional Flow**

1.  **Registration and Profile Setup:** Service providers register by creating an account with the "Maid" role. They can then build their profile by adding details about their skills, experience, and pricing.

2.  **Managing Availability:** Maids can set their work schedule to show customers when they are available for bookings.

3.  **Handling Booking Requests:** When a customer makes a booking request, the maid receives a notification and can either **accept** or **reject** it.

4.  **Updating Job Status:** Maids can update the status of a job, for example, by marking it as "Completed" after the work has been finished.

5.  **Viewing Past Jobs and Reviews:** The maid dashboard includes a history of all completed jobs and a section to view reviews left by customers.

[![](https://mermaid.ink/img/pako:eNo90Etv2zAMAOC_QvCwU5r5kcSPQ4HEea3YgCLpdpjdg2ozjjpbSiU5fQT575W1JjpR4kdS4AlLWRGmuGvka7lnysDDrBBgzzTfGnt_hJubW5jlG6q5NqTgO_yUNRfANPxivHr8r2eOZXmmiBkCqeD3oeqjeyV3vKEvljk2z7dkYHpkvGFPvOHmHbblnqru6ubOLezUkviRYCblPy5q2NBLR9roL7ZwbJlPy5IOpp-6oWcqzcVf3NK5VZ7J9tCQ_dVUa14LquBOPl3QyqF1_ofTK9wzbVwSvkHWaSNb6psfbe7i187_yBeiXwIOsFa8wnTHGk0DtL5l_R1PPS_Q7KmlAlMbVrRjXWMKLMTZ1h2Y-Ctli6lRna1Usqv31z6dW-Ocs1qx9vqqSFSkMtkJg2nge64Jpid8wzQMguEoGE-SKAqjJAnjAb5j6sdDb-SFnh9Gnj-OxkFwHuCHG-sN4yT2Yi-Ik3ASxhPfP38CH2Gkng?type=png)](https://mermaid.live/edit#pako:eNo90Etv2zAMAOC_QvCwU5r5kcSPQ4HEea3YgCLpdpjdg2ozjjpbSiU5fQT575W1JjpR4kdS4AlLWRGmuGvka7lnysDDrBBgzzTfGnt_hJubW5jlG6q5NqTgO_yUNRfANPxivHr8r2eOZXmmiBkCqeD3oeqjeyV3vKEvljk2z7dkYHpkvGFPvOHmHbblnqru6ubOLezUkviRYCblPy5q2NBLR9roL7ZwbJlPy5IOpp-6oWcqzcVf3NK5VZ7J9tCQ_dVUa14LquBOPl3QyqF1_ofTK9wzbVwSvkHWaSNb6psfbe7i187_yBeiXwIOsFa8wnTHGk0DtL5l_R1PPS_Q7KmlAlMbVrRjXWMKLMTZ1h2Y-Ctli6lRna1Usqv31z6dW-Ocs1qx9vqqSFSkMtkJg2nge64Jpid8wzQMguEoGE-SKAqjJAnjAb5j6sdDb-SFnh9Gnj-OxkFwHuCHG-sN4yT2Yi-Ik3ASxhPfP38CH2Gkng)