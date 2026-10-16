# Student Enrollment ETL Automation Using n8n and AI

## 📌 Project Overview

This project automates the process of cleaning, validating, filtering, and exporting student enrollment data using **n8n and AI**.

The workflow reads student data from a CSV file, uses an AI model to process the records, applies JavaScript data-cleaning and validation rules, filters students based on city and email validity, and generates an Excel file.

## 🎯 Project Objectives

- Extract student enrollment data from a CSV file.
- Clean whitespace and standardize data.
- Validate student email addresses.
- Normalize fee payment values.
- Filter students from Chennai with valid email addresses.
- Export the filtered records to an Excel (`.xlsx`) file.

## 🔄 Workflow

1. **CSV Upload** – Upload the raw student enrollment CSV file.
2. **Extract from File** – Extract records from the uploaded CSV.
3. **Basic LLM Chain** – Use AI to process and structure the student data.
4. **OpenAI Chat Model** – Provide AI capabilities for data processing.
5. **Code in JavaScript** – Clean fields, validate emails, and normalize fee payment values.
6. **IF Node** – Filter students whose city is Chennai and whose email is valid.
7. **Convert to File** – Export the filtered records to an Excel file.

## 🛠️ Technologies Used

- **n8n** – Workflow automation and ETL processing
- **OpenAI** – AI-assisted data processing
- **JavaScript** – Data cleaning and validation
- **CSV** – Raw input data format
- **Excel (.xlsx)** – Filtered output data format
- **Git and GitHub** – Version control and project hosting

## 📂 Repository Structure

```text
.
├── .gitattributes
├── .gitignore
├── ETL AI AUTOMATION.json
├── File.xlsx
├── Screenshot 2026-10-17 035624.png
├── Screenshot 2026-10-17 042522.png
├── student_enrollment_raw.csv
└── README.md
```

## 🧹 Data Cleaning and Validation

The JavaScript node performs the following operations:

- Removes leading and trailing whitespace.
- Replaces repeated spaces with a single space.
- Converts email addresses to lowercase.
- Checks email addresses against a basic email validation pattern.
- Replaces invalid email addresses with `Invalid Email`.
- Converts fee payment values such as `Yes`/`No` and `Paid`/`Unpaid` into Boolean values.
- Standardizes city capitalization.

## 🔍 Filtering Rules

The IF node filters the records using these conditions:

| Field | Condition | Expected value |
|---|---|---|
| City | Is equal to | `Chennai` |
| Email_Valid | Is equal to | `true` |

Both conditions must be true. Only matching records continue to the Excel export step.

## 📊 Output

The workflow generates an Excel file containing student records from Chennai with valid email addresses.

The output includes fields such as:

- Student ID
- Name
- Email
- Phone
- Course
- Fee Paid
- City
- Enrollment Date

The exact output columns depend on the fields configured in the workflow.

## 🚀 How to Run the Project

1. Install or open n8n.
2. Import `ETL AI AUTOMATION.json` into your n8n instance.
3. Configure your OpenAI credentials in n8n.
4. Execute the workflow and upload `student_enrollment_raw.csv` through the form.
5. Verify the cleaned records in the JavaScript node output.
6. Check the IF node's **true** output for matching records.
7. Execute the Convert to File node and download the generated Excel file.

**Note:** Node names or settings may need adjustment depending on your n8n version.

## 📸 Screenshots

The repository includes screenshots demonstrating the workflow and its execution.

- `Screenshot 2026-10-17 035624.png`
- `Screenshot 2026-10-17 042522.png`

## 🔐 Security

- Do not commit API keys, passwords, or other secrets.
- Configure credentials securely within n8n.
- Check CSV and Excel files for personal student information before making the repository public.

## 👨‍💻 Conclusion

This project demonstrates how n8n, AI, and JavaScript can be combined to automate student enrollment data processing. It reduces manual cleaning effort and produces a filtered Excel file for further analysis.

---

**Project:** Student Enrollment ETL Automation  
**Platform:** n8n  
**Output:** Filtered Excel file (`.xlsx`)
