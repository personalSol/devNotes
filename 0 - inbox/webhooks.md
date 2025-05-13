---
status: newBorn
related-links: []
created: 2025-04-28T15:42
updated: 2025-05-13T11:34
---
	---

A **webhook** is a way for one system to send real-time information to another system automatically when something happens.

**In simple terms:**  
A webhook is like setting up a "push notification" between two apps. Instead of you constantly asking, "Has something changed?" (like you would with an API polling), the app tells you immediately when it happens.

---

**How it works:**

- You give one app (the sender) a URL to another app (the receiver).
- When a specific event happens (like a new user signs up, a payment is made, etc.), the sender app makes an **HTTP request** (usually a `POST`) to the receiver’s URL.
- The receiver processes the data sent in that request.

---

**Example:**  
Imagine you run an online store and you use a payment service like Stripe.

- You set up a webhook to your server: `https://mystore.com/payment-updates`.
- When someone pays, Stripe sends a `POST` request with payment details to your webhook URL.
- Your server gets that info immediately and can react — like updating the order status or sending a confirmation email.

---

**Key points about webhooks:**

- They are **event-driven** (they react to something happening).
- They usually use **HTTP POST** to send data.
- They're faster and more efficient than polling (constantly asking for updates).
- You need a server (or a service like Zapier) to receive the webhook data.
- notify apps on real time

---



# Reference
`related tags + notes + source + link(if any)`
 

- 