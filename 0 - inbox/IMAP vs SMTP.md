---
status: newBorn
related-links:
  - "[[Basic-Concepts-MOC]]"
created: 2025-05-14T21:55
updated: 2025-05-14T23:24
---
---


### **IMAP (Internet Message Access Protocol)**

- **Purpose:** Used for **receiving** and **accessing** emails.
- **Functionality:**
    - Emails are stored on the **mail server**, not locally.
    - You can read, organize, and delete messages across multiple devices (syncs everywhere).
- **Port:** Typically uses **port 993** (SSL) or **143** (non-encrypted).
- **Common Use Case:** When you check your email using Gmail, Outlook, or Apple Mail and want the same experience across all devices.

---

### **SMTP (Simple Mail Transfer Protocol)**

- **Purpose:** Used for **sending** emails.
- **Functionality:**
    - Transfers email from your device (or mail client) to the recipient's mail server.
    - Works with authentication to prevent spam.
- **Port:** Typically uses **port 587** (TLS), **465** (SSL), or **25** (legacy, often blocked).
- **Common Use Case:** When you hit "send" in your email app, SMTP handles the delivery.

---

### In Short:

| Protocol | Role     | Direction     | Used For            |
| -------- | -------- | ------------- | ------------------- |
| IMAP     | Receiver | Incoming Mail | Syncing and viewing |
| SMTP     | Sender   | Outgoing Mail | Sending messages    |


# Reference
`related tags + notes + source + link(if any)`
 

- 