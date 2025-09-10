# Migadu-Small-Group-Mail-Distribution
Low-cost guide for setting up a Migadu-based mail distribution system for small groups, clubs, and associations. Covers mailbox structure, delegations, forwarding workarounds, and best practices for shared email use.

## Introduction

Many small organizations, groups, clubs, or other collaborations use email and messaging apps like WhatsApp, Signal, or Telegram to communicate internally.  
This works well — as long as all members use the same tools and keep the shared information manageable.

The situation changes when:
- Some members do not have (or do not want) to use the chosen messaging app.
- You want to use the communication history as an archive for agreements, documents, photos, videos, etc.
- You need a reliable way to find contact information and keep it up to date.

Without a central system, conversations often become cluttered with:
- Repeated questions (“Where can I find that document?” / “I didn’t get that email.” / “Can you send it again?”)
- Confusion about contact details (“What’s John’s email?” / “Oh, that’s outdated — use this one instead.”)
- Links to files scattered across different cloud storage locations.

While cloud storage (Google Drive, OneDrive, etc.) can help, it often turns messages into a long list of links rather than a smooth communication flow.

That’s why it is useful to choose a communication system that **everyone** in the group uses — and nowadays, that is usually email.  
The next step is to manage it centrally so that:
- Everyone receives all relevant messages.
- Members can easily send messages to the whole group, subgroups, or specific roles.
- The setup is simple to maintain.

My own small organization — a symphony orchestra — faced exactly this challenge.  
We chose email as our main communication channel and used [Migadu](https://migadu.com/) to build a flexible email distribution system with multiple groups and role-based addresses.  

It took some experimentation to get it right, but the current setup is stable and works well for our needs. This guide documents how we did it — so that others can learn from our experience and avoid the initial trial-and-error phase.

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

## How This Guide is Structured

This guide is divided into several subdocuments, each covering a specific part of setting up and maintaining a Migadu-based mail distribution system.

Each subdocument can be updated independently, allowing the guide to grow over time while keeping the main README concise.

- **[Key Decisions](docs/key-decisions.md)** – Fundamental choices that determine the overall design of the system.  
- **[Mailbox Setup](docs/mailbox-setup.md)** – How to create personal mailboxes, configure forwarding, and apply Sieve scripts.  
- **[Mail Distribution Setup](docs/mail-distribution-setup.md)** – How to structure delegations, groups, and the overall hierarchy for email distribution.  


## License

This repository uses a dual license structure:

- **Code** (if any) is licensed under the [MIT License](./LICENSE).  
  You are free to use, modify, and distribute it with attribution.

- **Documentation and non-code content** (including text, images, and diagrams)  
  is licensed under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).  
  You may share and adapt it for any purpose, even commercially, as long as you give appropriate credit.
