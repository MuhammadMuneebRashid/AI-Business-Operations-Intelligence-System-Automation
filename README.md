# 🤖 AI Business Operations Intelligence System

An **AI-powered Business Operations Intelligence System** built with **n8n and Google Gemini** to analyze business operations, generate actionable reports, and intelligently process customer complaints.

The system combines **business data analysis, AI-powered decision support, complaint intelligence, and workflow automation** to help businesses understand their operational performance and respond to customer issues more effectively.

> 🚧 **Project Status: In Progress**
>
> This project is currently under active development. The current version focuses on business performance analysis and customer complaint intelligence, with additional capabilities planned for future development.

---

## 📌 Overview

The **AI Business Operations Intelligence System** is designed to transform raw business operational data into meaningful and structured insights.

The current system processes two major areas:

### 📊 Business Operations Analysis

The system analyzes business reports and calculates:

* Total Revenue
* Total Expenses
* Profit
* Total Orders
* Pending Orders
* Major/Large Expenses
* Business Performance Reports

The profit is calculated using:

```text
Profit = Total Revenue - Total Expense
```

### 📢 Customer Complaint Intelligence

The system analyzes customer complaints and determines:

* Complaint Priority
* Complaint Type
* Customer Information
* Order Information
* Complaint Details
* Professional Message for the Business Owner
* Professional Message for the Customer

---

## ✨ Key Features

### 📈 Business Performance Intelligence

The system retrieves business report data from Google Sheets and processes pending reports.

It collects important operational information such as:

* Business Name
* Report Date
* Total Revenue
* Total Orders
* Total Expenses
* Pending Orders

The data is then passed to an AI Agent for analysis and professional reporting.

---

### 💰 Profit Analysis

The AI analyzes revenue and expenses to calculate business profit.

```text
Profit = Total Revenue - Total Expense
```

The system also examines revenue and expense information to identify significant expense entries and include relevant findings in the business report.

---

### 📊 AI-Generated Business Reports

Google Gemini analyzes the business data and produces a structured professional report.

The AI output currently contains:

```json
{
  "profit": "",
  "professional_report": ""
}
```

This structured format allows the generated intelligence to be used by future workflow modules and reporting systems.

---

### 📢 Customer Complaint Analysis

Customer complaints are retrieved from Google Sheets and filtered based on their status.

Pending or unprocessed complaints are sent to the AI Agent for analysis.

The system extracts information including:

* Customer Name
* Customer Email
* Order ID
* Complaint Category
* Complaint Description
* Complaint Date
* Row Number

---

### 🧠 AI Complaint Intelligence

Google Gemini analyzes each complaint to determine:

* **Priority**
* **Complaint Type**
* Appropriate response
* Professional communication for the owner
* Professional communication for the customer

The structured AI output is:

```json
{
  "priority": "",
  "subject": "",
  "complaint_type": "",
  "professional_message_for_owner": "",
  "professional_message_for_customer": ""
}
```

---

## 🔄 Workflow Architecture

```text
                    ┌─────────────────────┐
                    │   Schedule Trigger  │
                    └──────────┬──────────┘
                               │
                ┌──────────────┴──────────────┐
                │                             │
                ↓                             ↓
       ┌─────────────────┐           ┌─────────────────┐
       │ Business Report │           │    Complaints   │
       │  Google Sheets  │           │  Google Sheets  │
       └────────┬────────┘           └────────┬────────┘
                ↓                             ↓
       ┌─────────────────┐           ┌─────────────────┐
       │ Data Filtering  │           │ Data Filtering  │
       └────────┬────────┘           └────────┬────────┘
                ↓                             ↓
       ┌─────────────────┐           ┌─────────────────┐
       │ Business Data   │           │ Complaint Data  │
       │   Processing    │           │   Processing    │
       └────────┬────────┘           └────────┬────────┘
                ↓                             ↓
       ┌─────────────────┐           ┌─────────────────┐
       │ Google Gemini   │           │ Google Gemini   │
       │   AI Analysis   │           │   AI Analysis   │
       └────────┬────────┘           └────────┬────────┘
                ↓                             ↓
       ┌─────────────────┐           ┌─────────────────┐
       │ Profit &        │           │ Priority &      │
       │ Business Report │           │ Complaint Type  │
       └─────────────────┘           └─────────────────┘
```

---

## 🧩 Main Workflow Modules

### Module 1 — Business Intelligence

```text
Google Sheets
     ↓
Pending Report Filter
     ↓
Business Data Extraction
     ↓
Google Gemini
     ↓
Profit Calculation
     ↓
Professional Business Report
```

The workflow retrieves pending business reports and sends the relevant data to the AI Agent for analysis.

---

### Module 2 — Complaint Intelligence

```text
Google Sheets
     ↓
Pending Complaint Filter
     ↓
Complaint Data Extraction
     ↓
Google Gemini
     ↓
Priority Detection
     ↓
Complaint Type Classification
     ↓
Owner & Customer Messages
```

This module helps businesses understand customer complaints and generate appropriate professional communication.

---

## 🛠️ Technology Stack

| Technology        | Purpose                                    |
| ----------------- | ------------------------------------------ |
| **n8n**           | Workflow automation and orchestration      |
| **Google Gemini** | AI-powered business and complaint analysis |
| **Google Sheets** | Business and complaint data storage        |
| **JavaScript**    | Data filtering and transformation          |

---

## 📋 Business Report Data

The current business analysis workflow works with fields such as:

```text
row_number
business_name
report_date
total_revenue
total_order
total_expense
pending_orders
status
```

Pending or empty-status reports are selected for processing before being passed to the AI Agent.

---

## 📋 Complaint Data

The complaint analysis workflow currently processes:

```text
row_number
name
email
order_id
category
description
complaint_date
status
```

Pending or unprocessed complaints are selected for AI analysis.

---

## 🧠 AI Intelligence Layer

Google Gemini acts as the intelligence layer of the system.

Instead of simply moving data between applications, the AI analyzes business information and produces structured intelligence.

### Business Intelligence

```text
Revenue + Expenses
        ↓
   Profit Analysis
        ↓
Business Performance Report
```

### Complaint Intelligence

```text
Customer Complaint
        ↓
Priority Analysis
        ↓
Complaint Classification
        ↓
Professional Communication
```

---

## ⚙️ How It Works

The workflow is triggered automatically using an n8n Schedule Trigger.

The current schedule is configured to run at the specified scheduled hour.

The workflow then retrieves both:

1. Business reports
2. Customer complaints

Each dataset follows its own processing path.

The business data is analyzed for financial and operational insights, while complaints are analyzed for priority, type, and appropriate communication.

---

## 🚧 Development Status

**Current Status: 🟡 In Progress**

This project is still under active development.

### ✅ Currently Implemented

* [x] Scheduled workflow execution
* [x] Business report retrieval
* [x] Complaint retrieval
* [x] Pending data filtering
* [x] Business data processing
* [x] Complaint data processing
* [x] Profit calculation logic
* [x] Large expense analysis
* [x] AI-generated business reports
* [x] Complaint priority analysis
* [x] Complaint type classification
* [x] Professional owner communication
* [x] Professional customer communication
* [x] Structured AI output
* [x] Google Gemini integration
* [x] Google Sheets integration

### 🔨 Planned Features

* [ ] Automated business dashboards
* [ ] KPI monitoring
* [ ] Advanced business performance analytics
* [ ] Historical trend analysis
* [ ] Automated alerts for important business events
* [ ] Advanced complaint tracking
* [ ] Complaint resolution monitoring
* [ ] Business recommendations using AI
* [ ] Automated daily/weekly management reports
* [ ] Additional business data integrations
* [ ] More AI-powered operational workflows

---

## 🎯 Project Goals

The long-term goal is to develop a complete AI-powered business operations intelligence platform that can:

* Monitor business performance
* Analyze operational data
* Identify important business trends
* Detect potential issues
* Analyze customer complaints
* Prioritize operational problems
* Generate management reports
* Assist with business decisions
* Automate repetitive operational processes
* Provide actionable business insights

---

## 🔮 Future Vision

The project is intended to evolve beyond basic workflow automation into an **intelligent business operations system**.

Future versions may provide a centralized intelligence layer where business owners can receive:

```text
Business Data
     ↓
AI Analysis
     ↓
Business Intelligence
     ↓
Problems & Opportunities
     ↓
Recommended Actions
     ↓
Automated Operations
```

The ultimate objective is to help businesses move from **raw operational data to actionable intelligence** with minimal manual effort.

---

## 🔐 Security

Sensitive credentials should never be committed to the repository.

This includes:

* Google credentials
* API keys
* OAuth tokens
* Private spreadsheet information
* Other authentication credentials

Use n8n's credential management system to securely store integrations.

---

## 📂 Project Structure

```text
AI-Business-Operations-Intelligence-System/
│
├── workflows/
│   └── n8n workflow files
│
├── documentation/
│   └── project documentation
│
└── README.md
```

---

## 🚀 Getting Started

1. Set up an n8n instance.
2. Import the workflow JSON.
3. Connect Google Sheets.
4. Configure Google Gemini credentials.
5. Prepare business report data.
6. Prepare customer complaint data.
7. Test the workflow.
8. Verify the AI-generated output.
9. Activate the workflow.

---

## 💡 Project Highlights

This project demonstrates the combination of:

**AI + Business Intelligence + Workflow Automation + Data Analysis + Customer Operations**

The current implementation focuses on two important business areas:

> **Business Performance Intelligence**

and

> **Customer Complaint Intelligence**

These modules form the foundation for a larger AI-powered business operations platform.

---

## 📌 Current Project Status

> 🚧 **This project is currently in progress and actively being developed.**

The current version provides the foundation for business performance analysis and customer complaint intelligence.

More automation modules, analytics capabilities, AI insights, and business operations features will be added as development continues.

---

<img width="1920" height="1080" alt="complaint project" src="https://github.com/user-attachments/assets/05bae8c7-6f15-4ef5-90a5-8d559086232b" />
<img width="1920" height="1080" alt="reporting project" src="https://github.com/user-attachments/assets/38fd3b10-9704-4650-80ee-d48deb7b562b" />

<img width="1920" height="1080" alt="business intelligence system" src="https://github.com/user-attachments/assets/ed6e0d39-1377-4b70-8461-a452ef775b3f" />

## ⭐ Conclusion

The **AI Business Operations Intelligence System** is an ongoing project focused on using artificial intelligence and workflow automation to make business operations more intelligent and efficient.

By combining **n8n, Google Gemini, Google Sheets, and JavaScript**, the system can currently analyze business performance, calculate profit, identify significant expenses, classify customer complaints, determine complaint priority, and generate professional communication.

The project will continue to evolve toward a broader **AI-driven business intelligence and operations platform**.

---

**🚧 Project Status: In Progress**

**Built with n8n • Google Gemini • Google Sheets • JavaScript**
