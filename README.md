# UiPathInvoicesPractice
Practice Repository for the UiPath RPA Developer course

# RPA Developer Practice Repository

This repository is part of the practice for the UiPath RPA Developer course. It contains a very basic web application intended for robot development and automation.

## Project Description

### The Robot:

The robot automates the process of downloading attached `.xlsx` files from Outlook emails. The emails contain "invoice" files with a fictitious customer number. The robot will:

1. Extract the customer number from the invoice.
2. Paste the number into a basic web application called **AutoSite Basic**.
3. Search for discount eligibility on the website. 
4. If the customer is eligible for a discount, the discount amount will be displayed.
5. The robot will copy the discount, apply it to the `.xlsx` file, and calculate the new payment amount.
6. The robot will process each invoice, and at the end, will "send" the invoices to a provided email (currently, it saves them in drafts).

## Usage Instructions:

### Step 1: Obtaining Invoices
1. Navigate to the UiPath **ACME System**:  
   [https://acme-test.uipath.com/first-automation](https://acme-test.uipath.com/first-automation)
2. Click on **Notify Me** and enter your email address to receive the invoices.

### Step 2: Configuring the Robot

1. **Get Outlook Emails:**
   - In the **GetOutlookMailMessages** activity, input the email account where you received the invoices.
   - Set the `MailFolder` to `"Inbox"` or `"Bandeja de entrada"` if Outlook is in Spanish.

2. **Configure the Browser Activity:**
   - In the activity named **Use Browser Edge: ACME System 1 - Dashboard**, update the `Browser Url` field with the path to the `vendor.html` file found in the **AutoSite Basic** web folder.

3. **Sending Emails:**
   - In the activity **Send Email to create a draft email with attachments in Outlook**, update the `To` field with the recipient email address where the processed invoices should be "sent."

## Repository Structure

- **AutoSite Basic**: Basic web application where customer numbers are checked for discounts.
- **Robot**: UiPath project containing the workflow to process the invoices and interact with the web app.

## Notes

- This project is currently designed to save processed emails in the Drafts folder instead of actually sending them.

---

