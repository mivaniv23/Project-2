# CIS 3400 – Advanced Programming
## Project 2: Python Application Development

**Student Name:** Markiian Ivaniv
**Project Title:** Budget-Expense Management Application
**Course:** CIS 3400 – Advanced Programming  
**Final Presentation:** December 8, 2026

---

## 1. Project Overview

**Application Name:** [Name]

**Project Option:** Database-Enabled

### Problem Statement
The Catawba College Solar Vehicle Team needs an organized way to manage its project budget and track expenses. Currently, managing purchases, receipts, and spending across different team departments can become difficult, especially as the team develops multiple solar vehicles. This application provides a centralized system for recording expenses, monitoring the remaining budget, and organizing financial information. It also allows the team to generate Excel reports, making financial tracking and reporting easier and more efficient.

### Intended Users
The primary users are members of the Catawba College Solar Vehicle Team, especially team leadership and members responsible for purchasing, finances, and project management.

Users will be able to:

- Monitor the team's overall budget.

- Record and organize purchases.

- Upload and access expense receipts.

- Track spending across different departments.

- Generate financial reports for specific periods.

- Review how much money remains available.

### Unique Features
Unlike a basic expense calculator or classroom budgeting demonstration, this application is designed specifically for a university solar vehicle team.

Its main distinguishing features include:

- Department-based expense tracking for Mechanical, Electrical, Media, Operations, and Travel.

- Receipt image uploads connected to individual transactions.

- A centralized SQLite database that preserves financial records.

- Automatic budget calculations and spending summaries.

- Professional Excel reports with transaction details and category summaries.

- The application is designed around the actual financial management needs of a student engineering team.

## 2. Application Features

- **Feature 1: Budget Dashboard:** Displays the total team budget, total expenses, remaining balance, and percentage of the budget used. It also provides a breakdown of spending by category and displays recent transactions.
- **Feature 2: Expense Management:** Allows users to record expenses by entering the date, amount, vendor, reference number, category, and additional notes. Users can also upload receipt images and review or delete existing transactions.
- **Feature 3: Department-Based Expense Tracking:** Organizes expenses into categories such as Travel, Mechanical, Electrical, Media, and Operations. Users can filter transactions by category, date range, and minimum or maximum expense amount.
- **Feature 4: Excel Financial Reports:** Generates downloadable Excel reports for daily, monthly, and yearly spending. Reports include transaction details, budget information, total spending, remaining balance, and a separate worksheet summarizing expenses by category.

## User Interaction

Users interact with the application through a web-based interface. They can navigate between the dashboard, expense management, budget settings, and reporting pages.

When a user records an expense, the application validates the information and stores it in the database. The dashboard automatically updates its financial calculations. Users can also select a reporting period and generate an Excel file containing the relevant financial information.

## 3. Technologies Used

List technologies **actually used** and explain their purposes. Remove unused examples.

| Technology | Purpose |
|---|---|
| Python | Main programming language for application logic and calculations. |
| Flask | Web application framework responsible for routing and connecting the interface with Python functions. |
| SQLite| Database used to permanently store budget settings and expense records. |
| HTML | Creates the application's web pages and forms. |
| CSS | Provides the application's layout, styling, and responsive design. |
| Jinja2 | Dynamically displays database information and application results in HTML templates through Flask. |
| OpenPyXL | Creates and formats downloadable Excel financial reports. |
| Werkzeug | Supports secure file naming and receipt image uploads. |
| Python Standard Library | Provides date handling, file management, SQLite connectivity, and other application functionality. |

## 4. Application Architecture

The application follows a simple client-server architecture. Flask connects the web interface with Python processing functions and the SQLite database.

Preliminary Architecture Diagram

The planned architecture consists of the following components:

1. User: Enters financial information or requests reports.

2. Web Interface: HTML templates styled with CSS.

3. Flask Application: Receives requests and processes user input.

4. Python Modules: Handle budget calculations, expense management, and report generation.

5. SQLite Database: Stores budget settings and expense transactions.

6. File Storage: Stores uploaded receipt images.

7. Excel Reporting: Generates downloadable financial reports using OpenPyXL.

8. Output: Displays updated information or provides downloadable reports.

![Application architecture](/Project2/architecture.png)


### How the Application Works



1. The user opens the application through a web browser.

2. Flask displays the appropriate page using HTML templates.

3. The user enters information, such as a new expense or an updated budget.

4. Flask receives the submitted information and passes it to the appropriate Python functions.

5. The database module validates and stores financial records in SQLite.

6. Python retrieves stored information and calculates spending totals and remaining budget.

7. The results are displayed on the dashboard or expense pages.

8. When requested, the reporting module uses OpenPyXL to generate an Excel report for download.

**Components developed by the student:** The Flask application, Python database module, expense management functionality, HTML templates, CSS styling, and Excel report generation module.



## 5. Project Structure

The initial project organization is:

```text
solar_budget_assistant/
│
├── app.py
├── database.py
├── reports.py
├── requirements.txt
├── README.md
├── .gitignore
│
├── solar_budget.db
│
├── templates/
│   ├── base.html
│   ├── dashboard.html
│   ├── expenses.html
│   ├── add_expense.html
│   ├── settings.html
│   └── reports.html
│
├── static/
│   ├── style.css
│   └── uploads/
│
└── reports/
    └── (Generated Excel reports)
```

**Important Files and Their Purposes**

- app.py: Main application file. Handles Flask routes, user requests, expense validation, budget settings, and application navigation.

- database.py: Contains the BudgetDB class, which creates database tables and handles adding, retrieving, filtering, and deleting expenses.

- reports.py: Generates formatted Excel reports using OpenPyXL.

- requirements.txt: Lists the Python packages required to run the application.

- README.md: Contains project information and installation instructions.

- solar_budget.db: SQLite database containing budget settings and expense records. Created automatically when the application initializes.

- templates/: Contains the HTML pages used by Flask.

- static/style.css: Contains the visual design and responsive styling.

- static/uploads/: Stores uploaded receipt images.

- reports/: Stores generated Excel reports.



## 6. Installation and Running the Application

The application is designed to run locally using Python and Flask.

### Step 1: Clone the repository

```bash
git clone [repository-url]
cd [repository-folder]
```

### Step 2: Create a Virtual Environment

```bash
python -m venv .venv
```

## Activate it:

### Windows:
```bash
.venv\Scripts\activate
```

### macOS/Linux:
```bash
source .venv/bin/activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Run the Application

Open a browser and navigate to:
```bash
http://127.0.0.1:5000
```

The SQLite database and required tables are created automatically when the application starts for the first time.

No external API keys or third-party database services are required for the current version.

## 7. Testing and Validation

The following tests are planned to verify that the application works correctly.

| Test | Expected Result | Actual Result |
|---|---|---|
| Add a valid expense | Expense is saved in SQLite and appears in the expense list | To be verified |
| Submit an invalid expense | Application displays an appropriate error message | To be verified |
| Update the team budget | Dashboard displays the updated budget and remaining balance | To be verified |
| Filter expenses | Only transactions matching the selected filters are displayed | [To be verified |
| Upload a receipt | Receipt image is saved and associated with the expense | To be verified |
| Generate an Excel report | Correct Excel workbook is generated and downloaded | To be verified |
| Delete an expense | Transaction is removed from the database | To be verified |

**Known Limitations**

- The current application does not include user authentication or individual accounts.

- The application is designed primarily for local use and does not yet support secure multi-user access.

- Receipt uploads are currently limited to image formats.

- A production deployment would require additional security configuration and a production web server.


## 8. AI-Assisted Development Disclosure

**AI Tools Used:** ChatGPT

### How AI Was Used

ChatGPT was used as an assistance tool during the development and planning of the application. AI assistance included brainstorming application functionality, discussing Python and Flask implementation approaches, troubleshooting programming issues, and improving project documentation.

AI assistance was also used to explore database organization, expense management functionality, and Excel report generation.

### Student Contributions

I developed the project around the financial management needs of the Catawba College Solar Vehicle Team. I made decisions regarding the application's features, expense categories, database organization, and overall interface.

My contributions include working with the Python application structure, Flask routes, SQLite database integration, HTML templates, CSS styling, receipt management, and Excel report functionality. I am responsible for reviewing, understanding, testing, and explaining the application and its implementation.

**Student statement:** I reviewed, tested, and can explain the code and technologies used in my application, including code developed with AI assistance.

## 9. Challenges and Lessons Learned

**Challenge 1: Database Organization** One of the main challenges is designing a database structure that can efficiently store and retrieve budget information and individual expense records. The solution is to use SQLite with separate tables for budget settings and expenses. A dedicated Python class handles database operations, making the application easier to organize and maintain.

**Challenge 2: Connecting the Web Interface with Python** Another challenge is connecting user input from HTML forms with Python functions and database operations. Flask provides the connection between the web pages and the backend. It allows users to submit expenses, update budget settings, and request financial reports without interacting directly with the database.

## New Skills and Technologies

Through this project, I am developing practical experience with:

- Python application development.

- Object-oriented programming and Python classes.

- Flask web application development.

- SQLite database design and SQL queries.

- HTML forms and CSS styling.

- File uploads and file management.

- Generating and formatting Excel documents with OpenPyXL.

- Organizing a multi-file Python application.
  

## 10. Application Screenshots

**Main Dashboard:** Shows the total budget, spending, remaining balance, and category breakdown.

![Main Dashboard](/Project2/mainPage.png)

**Expense Management:** Shows the expense list, filtering options, and recorded transactions.

![Expense Management](/Project2/ExpenseRecords.png)

**Financial Reports:** Shows the report generation interface and downloadable Excel reports.

![Financial Reports](/Project2/reports.png)

## 11. Future Improvements

1. User Authentication and Permissions: Introduce individual accounts and different access levels for team members, project managers, and administrators.

2. Multi-Vehicle Budget Management: Expand the application to support separate budgets and expense tracking for multiple solar vehicles, allowing the team to compare spending between projects.

---

### Documentation Timeline

- **Deliverable 1 – November 16:** Complete the project overview, planned features, proposed technologies, preliminary architecture diagram, and planned project structure. These are planning sections and may change as development progresses.
- **Deliverable 2 – November 23:** Update the README to reflect implementation progress and initial testing.
- **Final Deliverable – December 8:** Complete all sections, verify setup instructions, add screenshots, and provide final links.

