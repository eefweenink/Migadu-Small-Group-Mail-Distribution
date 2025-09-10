# Mail Distribution System Setup

For actual email distribution, we use **delegations only**.  

### Planning is Key

It is crucial to have a clear plan in advance for how emails should be distributed.  
As an example, we have included the structure of our orchestra (see figure).  
![image of structure of orchestra maildistribution](/fig/Scherm%C2%ADafbeelding%202025-08-28%20om%2011.08.32.png)


In this setup, there are two main categories:  
- **Orchestra-related emails** (for the musicians)  
- **Organization-related emails** (for the association management and administration)  
- Additional mailboxes for another language (e.g., Dutch)  

### Hierarchical Distribution

The system is hierarchical. For example, an email sent to the orchestra follows these steps:  

1. Email arrives in the **Orchestra mailbox**.  
2. From the Orchestra mailbox, it is distributed to **Sections** (e.g., Strings and Winds mailboxes).  
3. From Section mailboxes, emails are sent to **instrument-specific mailboxes** (Violin, Bass, etc.).  
4. Finally, from the instrument mailboxes, emails are delivered to **individual personal mailboxes**, where external forwarding is configured.  

The same hierarchy is applied to all organizational roles.  
Some members hold multiple roles, and the system ensures that all relevant emails reach their personal mailbox correctly before being forwarded externally.

## 2. Organizing Mailboxes with Groups and Delegations

As the number of mailboxes grows, the system can quickly become hard to manage.  
For example, in our orchestra with 35 members, we have over 50 mailboxes (1 per member plus around 15 distribution mailboxes).

### Group Organization

To keep the Migadu panel organized, mailboxes are placed into groups:  
- **organization** – mailboxes related to the association/management  
- **orchestra** – mailboxes related to the musicians  
- **forwarders** – personal mailboxes with external forwarding  
- **untagged** – a small number of mailboxes without a group  

### Setting Delegations

1. Open the mailbox submenu (this can also be done when creating a new mailbox).  
2. Go to **Delegations**.  
3. In the input field, enter the names of the mailboxes where emails should be forwarded.  
   - Example: `subgroup1` (Migadu automatically appends `@domain.com`)  
   - **Important:** avoid typos, as incorrect names will cause emails to be lost.  
4. Click **Save Changes**.  
5. Go to **Listing Settings**.  
   - Here you can set tags for the Migadu panel.  
   - You can create your own tag names and assign multiple tags separated by commas (`,`).  

### Recommendations

- Repeat this process for all mailboxes.  
- For accuracy, it is strongly advised to **use copy-paste** for mailbox names, especially for member mailboxes — typos are easy to make and can break mail distribution.  
