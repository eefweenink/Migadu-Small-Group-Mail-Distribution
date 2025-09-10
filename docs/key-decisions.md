## Key Decisions for the Email Distribution System

Based on our experience setting up a Migadu-based mail system for a small group, we identified a few critical principles that shape the entire setup:

### 1. External Forwarding from Personal Mailboxes

All emails received by the system must eventually be forwarded to each recipient's external email address.  
- One option would be to give everyone access to their own mailbox within the system, but most people do not want to manage another mailbox.  
- Forwarding to external email works very well in Migadu, but **each recipient must activate it themselves** by responding to the first setup email. This step is unavoidable and can cause issues if not done correctly.  
- Lesson learned: make sure this step is required **only once per recipient**.  
- Practical solution:  
  - Each user gets one personal mailbox in the system.  
  - A **Sieve script** (see later sections) automatically forwards all incoming emails to their external address.  
  - The recipient must approve this forwarding **once**, after which it continues automatically.

### 2. Use Delegations Only for Group Distribution

Within the system, only **delegations** are used to distribute emails to groups and role-based addresses.  
- Other options, such as aliases or identities, can cause problems with external forwarding.  
  - Some external providers treat forwarded messages as spam or block them entirely.  
- Note: The first forwarded email often lands in spam, so recipients must mark it as desired. This is normal and expected.  

### ✅ Summary

- **Forwarding from personal mailboxes is mandatory** to ensure delivery to external addresses.  
- **Delegations are used exclusively** for distributing emails to groups or roles.  
- Avoid aliases or secondary identities for forwarding purposes.  

This structure ensures that the system works reliably while keeping setup simple for users.

