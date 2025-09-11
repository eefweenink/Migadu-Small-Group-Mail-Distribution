# Mailbox Setup

## 1. Create a Migadu Account

Start by creating a Migadu account:  
[Sign up for a Migadu account](https://admin.migadu.com/public/signup)

Follow the instructions — it’s straightforward:  
- Register your domain name  
- Configure the DNS settings (Migadu provides helpful tools)  
- Once the account is active, proceed with payment  

For our needs, the **Micro account ($19/year)** has been more than sufficient.  

After setup, log in here to start configuring your email system:  
[Login to Migadu](https://admin.migadu.com/public/login)


## 2. Setup a Personal Mailbox with Forwarding

Follow these steps to create a mailbox and forward all incoming emails to an external address:

### Create the Mailbox

1. Go to **Default Mailbox Services** and enable all options, including **ManageSieve** (this is a one-time setup for the first mailbox).  WARNING: By default, ManageSieve is disabled!
2. Click **New Mailbox**.  
3. Enter the mailbox details:
   - **Email address** and **Mailbox name**  
   - Use a **recognizable name** for the person (e.g., first and last name), not a role or group. Roles and groups are handled separately in the mail distribution setup.  
4. Set an **initial password**. Use the same password for all mailboxes — convenient for the administrator. Users can change it later if they need to access the mailbox directly via IMAP, etc.  
5. Save the mailbox.

### Configure Forwarding

1. Click on the newly created mailbox.  
2. In the right-hand menu, go to **Forwarding** → **New Forwarding**.  
3. Enter the **destination email address**.  
4. A confirmation email is sent to the destination address.  
   - The recipient must **confirm the forwarding** either by clicking the link in the email or sending back the provided code.  
5. Go back to **Forwarding** and check that the destination address is listed and active.  
   - Forwarding will **not work** until the recipient confirms.

### Set Group Tags

1. In the right-hand menu, click **Listing Settings**.  
2. Under **Comma-Separated Tags**, enter the **group name** this mailbox belongs to (see the section on configuring the mail distribution system).  
3. Click **Save Changes**.

### Configure Sieve Script (Webmail Side)

1. Go to [Migadu Webmail](https://webmail.migadu.com/) and log in using the mailbox email and password.  
   - Using the same password for all mailboxes is convenient for initial setup.  
2. Go to **Settings → Filters**.  
3. Add a new script, use next example as most simple version:  

```sieve
require ["fileinto", "variables", "envelope"];
redirect "externalmailaddress@domain.com";
keep;
```
PS: If the receiver uses more then 1 mailadress:
add extra lines: 
```sieve
require ["fileinto", "variables", "envelope"];
redirect "externalmailaddress@domain.com";
redirect "secondexternalmailaddress@domain.com";
keep;
```

- Give the script a name, save it, and select it (the circle should be filled/black).  
✅ Once the recipient has confirmed the forwarding, the mailbox is active, and all incoming emails will be automatically forwarded to the external address.

### Repeat this for all external forwarding mailboxes

## 3. Setup Mailboxes for the Mail Distribution System

Follow the steps above to create a mailbox.  

**Important:** Do **NOT** set up external forwarding or the Sieve script for these mailboxes.  
Skip the sections **Configure Forwarding** and **Configure Sieve Script (Webmail Side)**.  

> Note: Refer to the Mail Distribution System setup for mailbox names and group allocation.

