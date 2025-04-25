# ReAgent-AI-Assignment

Author: Camille Zhang  
Email: zhiqi.zhang@vanderbilt.edu

## Overview

This project is an n8n workflow that automates sending personalized emails to contacts stored in a CRM (Google Sheets), updates the email status based on delivery results, and handles errors gracefully.

## Setup Instructions

1. Import the provided `.json` file into your n8n environment.
2. Connect your Google Sheets account as a credential.
3. Connect your SMTP email account for sending emails.
4. Open the workflow and trigger it manually.
5. Make sure your Google Sheet includes the following columns:  
   `first_name`, `company`, `last_product_purchased`, `renewal_date`, `email`, `email_status`, `last_contacted`
6. The workflow will send personalized emails and update the sheet accordingly.

### 📋 CRM Used

- **Google Sheets**  
Used as a lightweight CRM to store and manage contact information: 
https://docs.google.com/spreadsheets/d/1FIMJVorxR6PKjyoS9Yc-y-jVDPiM-qFZ9ps8tUNOhGI/edit?usp=sharing

### Extra Features & Assumptions

- Emails are only sent if `email_status = "pending"`.
- The `email_status` is updated to `"sent"` upon successful SMTP response.
- `last_contacted` is updated with the current timestamp upon send attempt.
