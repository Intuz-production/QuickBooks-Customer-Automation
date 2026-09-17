*Intuz — Your automation partner, one workflow at a time.*

<p align="center">
  <picture>
    <img alt="Banner Image" src="https://github.com/user-attachments/assets/210f97fc-0fce-404a-b647-7dfe1302cd37" />
  </picture>
</p>

[Intuz](https://www.intuz.com) helps organizations orchestrate AI, automation, and enterprise systems through scalable workflows. Our repository showcases proven implementations across healthcare, operations, customer support, document processing, sales, and back-office functions, enabling teams to accelerate automation initiatives without starting from scratch.

[N8N Creator](https://n8n.io/creators/intuz/) · [AI Automation Company](https://www.intuz.com/company/) · [AI Development Company](https://www.intuz.com/company/) · [For Custom Workflow Automation](https://www.intuz.com/get-started/)

# Automate QuickBooks customer & estimate creation from Google Sheets

This n8n template from Intuz provides a complete and automated solution to accelerate your sales and quoting process into QuickBooks.

This workflow creates a seamless data pipeline from a Google Sheet directly into QuickBooks, automating the creation of new customers and their initial sales estimates. It’s designed to save time, reduce human error, and ensure your financial records are always up-to-date.

## How it works

1. **Trigger on New Sheet Row:** The workflow starts automatically when you add a new row containing customer and estimate details to your designated Google Sheet.

2. **Check for Duplicates:** Before doing anything else, it takes the customer’s name from the sheet and searches your QuickBooks account to see if a customer with that exact name already exists.

3. **Route Based on Existence (If/Else Logic):**
   - **If the Customer is NEW:** The workflow proceeds down the “true” path, first creating a new customer record in QuickBooks with the details from the sheet (Name, Email, Phone, Company). Immediately after, it creates a new sales estimate linked to that newly created customer.
   - **If the Customer ALREADY EXISTS:** The workflow follows the “false” path and stops. This is a built-in safety measure to prevent creating duplicate customer records.

4. **End of Process:** The workflow concludes, having either created a new customer and estimate or having intelligently stopped to avoid duplication.

## Step by Step Instructions

Follow these steps carefully to get the workflow running.

### 1. Connect Your Credentials

- **Google:** Connect your Google account using OAuth2. Ensure you have enabled permissions for both Google Sheets and Google Drive.
- **QuickBooks:** Connect your QuickBooks Online account using OAuth2 credentials.

### 2. Prepare Your Google Sheet

This is the most critical step. Create a Google Sheet and ensure the first row contains these exact column headers:

- CustomerName
- Email
- Phone
- Company Name
- Amount

### 3. Configure the n8n Nodes

**Google Sheets Trigger:**

- Select your Google Sheet from the Document ID dropdown.
- Select the specific sheet from the Sheet Name dropdown.

**Create an estimate (QuickBooks Node):**

- This node has a default product/service (`itemId`) and tax code (`TaxCodeRef`) set. You must update these to match the items and tax codes in your QuickBooks account. See the Customization section for more details.

### 4. Activate the Workflow

Save the workflow and toggle the Active switch to “on”. Now, every time you add a new row to your sheet, the automation will run.

## FAQ

**Is this template free to use?**
Yes. It's an open-source n8n workflow published by Intuz — copy the workflow JSON from this repo and import it into your own n8n instance at no cost.

**Do I need a paid n8n plan to run this?**
No. It runs on n8n's free self-hosted Community Edition or on n8n Cloud. You'll need your own credentials for the services this workflow connects to, not a specific n8n pricing tier.

**What happens if the customer already exists in QuickBooks?**
The workflow stops. It searches QuickBooks by customer name first and only creates a new customer and estimate when no match is found — so existing customers are never duplicated.

## Related n8n templates from Intuz

- [Automate QuickBooks customers & sales receipts generation from a Google Sheet](https://github.com/Intuz-production/Automate-QuickBooks-Customer-Sales-Receipt-Creation)
- [Automate real-time QuickBooks invoice sync to Google Sheets](https://github.com/Intuz-production/QuickBooks-Invoice-Sync)
- [Sync new subscribers from Google Sheets to MailerLite without duplicates](https://github.com/Intuz-production/Sync-subscribers-to-MailerLite)

See all of Intuz's free n8n templates: https://www.intuz.com/n8n-workflow-automation-templates/

## Connect with us

Intuz is a USA-based AI & workflow automation company with 16+ years of experience building custom AI-enabled workflow automations for SMBs and Enterprises, specializing in agentic AI, LLM integrations, and CRM/ERP sync across Healthcare, FinTech, eCommerce, Manufacturing, and Real Estate. Explore 30+ free templates at intuz.com/n8n-workflow-automation-templates or get a custom workflow built at intuz.com/get-started.

* **Website:** https://www.intuz.com/
* **Email:** [getstarted@intuz.com](mailto:getstarted@intuz.com)
* **LinkedIn:** https://www.linkedin.com/company/intuz/
* **Get Started:** https://n8n.partnerlinks.io/intuz

## For Custom Workflow Automation

[Click here - Get Started](https://www.intuz.com/get-started/)
