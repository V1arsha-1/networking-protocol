This README explains the complete flow of an email, covering:

SMTP Commands
HELLO example.com
MAIL FROM:<sender@example.com>
RCPT TO:<receiver@example.com>
DATA
Subject: Test Email
Hello, this is a test.
.
QUIT


Metadata (headers, time sent, content)

How email travels across the internet

How the receiving server handles it

Mailbox storage (IMAP vs POP3)

How the email reaches the user's app

1. SMTP BASIC COMMANDS (Simple Example)

SMTP (Simple Mail Transfer Protocol) is used to send emails.

Example Commands
HELLO example.com
MAIL FROM:<sender@example.com>
RCPT TO:<receiver@example.com>
DATA
Subject: Test Email
Hello, this is a test.
.
QUIT
What they mean

HELLO – Start communication with the server.

MAIL FROM: – Sender’s email address.

RCPT TO: – Receiver’s email address.

DATA – Start writing the message body.

. – End of the message.

2. EMAIL METADATA (HEADERS + CONTENT)

Every email contains the following metadata:

1. Time Sent
   Date: Mon, 24 Nov 2025 10:30:00 +0530

Indicates when the email was sent. Example:

Date: Mon, 24 Nov 2025 10:30:00 +0530
2. Mail Headers

These describe the email’s path, sender, receiver, etc. Examples:

From: sender@example.com
To: receiver@example.com
Subject: Hello
Message-ID: <abc123@example.com>
3. Message Content

This is the actual body of the email — text, images, attachments.

3. HOW THE EMAIL MOVES BETWEEN SERVERS

Here is the entire path of an email across the internet:

Sender writes email in Gmail/Outlook/etc.

The app sends it to the SMTP server.

SMTP server checks: sender, domain, size, etc.

SMTP finds the receiver’s mail server using DNS (MX Records).

The email travels across the internet to the destination server.

The receiver’s server accepts and stores the message.

Think of it like: Post Office A → Internet → Post Office B → User’s Mailbox.

4. WHAT THE RECEIVING SERVER DOES

Once the email reaches the receiver’s server:

1. Accepts the Message

The server verifies:

valid recipient

message format

mailbox availability

2. Checks for Spam

Server runs multiple checks:

Blacklists

Virus scans

SPF, DKIM, DMARC authentication

Content analysis

3. Stores It in the User’s Mailbox

If safe, the email is placed inside the recipient’s mailbox folder (Inbox).

5. MAILBOX STORAGE TYPES — IMAP vs POP3

Emails stored on the server are accessed using either IMAP or POP3.

IMAP (Internet Message Access Protocol)

Emails stay on the server.

Syncs across multiple devices.

Read/delete actions update everywhere.

POP3 (Post Office Protocol 3)

Downloads the email to one device.

Usually deletes from the server.

Does not sync across devices.

6. HOW THE MESSAGE REACHES THE USER'S APP
IMAP Flow

User opens their email app.

App connects to the server.

It syncs inbox folders.

Messages remain on the server.

The device loads the email content when opened.

You are basically viewing letters inside the mailbox without removing them.

POP3 Flow

App connects to server.

Downloads emails to the device.

Server mailbox may be emptied.

Like taking letters out of a mailbox and bringing them inside your home.

SUMMARY

SMTP sends the email.

Metadata helps servers track and deliver the message.

Email travels across servers using DNS and internet routes.

Receiving server accepts, checks spam, and stores the message.

IMAP syncs emails; POP3 downloads them.

Email apps fetch messages using IMAP/POP3.
