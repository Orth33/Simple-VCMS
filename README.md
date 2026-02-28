# Simple Veterinary Clinic Management System (VCMS)

## 📋 Project Overview

The **Simple Veterinary Clinic Management System (VCMS)** is a comprehensive desktop application designed to streamline operations in veterinary clinics. This system provides an integrated solution for managing animal records, scheduling appointments, tracking services, managing employee information, handling billing and expenses, and maintaining inventory.

Built with PyQt5 for a modern desktop GUI and MySQL for robust data persistence, VCMS enables veterinary clinics to efficiently manage all aspects of their business operations, from patient registration to financial reporting.

## 🎯 Key Features

- **🔐 Authentication System**: Secure login system with employee roles and access levels
- **🐾 Animal Management**: Register and maintain comprehensive records of animals including medical histories, behavioral warnings, and medical conditions
- **📅 Appointment Scheduling**: Schedule, manage, and track veterinary appointments with status tracking
- **👥 Employee Management**: Manage staff information including roles, designations, salaries, and access levels
- **🏥 Medical Records**: Maintain detailed medical records and treatment history for each animal
- **💊 Service Management**: Define and manage veterinary services with pricing and availability
- **💰 Billing System**: Generate bills for rendered services with adjustments and payment status tracking
- **📊 Financial Management**: Track clinic expenses with approval workflow and financial reporting
- **🛏️ Day Care Services**: Manage pet daycare bookings with start/end times and special notes
- **📦 Inventory Management**: Track medical supplies and equipment with stock levels
- **📈 Analytics & Reports**: Generate reports on appointments, animals, employees, and financial metrics
- **🎨 Customizable Themes**: Apply different color themes to the application interface
- **💾 Data Persistence**: Remember login credentials with optional auto-login feature

## 💻 Technologies & Dependencies

### Core Technologies
- **Frontend**: PyQt5 (v5.15.10) - Desktop GUI framework
- **Backend**: Python 3.x
- **Database**: MySQL - Relational database management
- **Database Driver**: mysql-connector-python (v8.2.0)
- **UI Theming**: qt-material (v2.14) - Material design for PyQt5
- **Build Tools**: qt5-tools (v5.15.2.1.3)

## 📁 Project Structure

```
Simple-VCMS/
├── App.py                      # Main application entry point
├── Auth.py                     # Authentication and login system
├── MySQLHandler.py             # Database connection handler
├── Operations.py               # Business logic operations
│
├── Models/                     # Data models
│   ├── Animal.py              # Animal model and operations
│   ├── Employee.py            # Employee model and operations
│   ├── Appointment.py         # Appointment model and operations
│   ├── Service.py             # Service model and operations
│   ├── Billing.py             # Billing model and operations
│   ├── Expense.py             # Expense model and operations
│   ├── DayCareService.py      # Day care service model
│   ├── Item.py                # Inventory item model
│   ├── Veterinarian.py        # Veterinarian (extends Employee)
│   └── AnalyticsReport.py     # Report generation
│
├── UI Files/                   # PyQt5 Designer UI files (.ui)
│   ├── LoginUI.ui
│   ├── MainUI.ui
│   ├── AnimalRegistrationUI.ui
│   ├── AnimalDetailsUI.ui
│   ├── AppointmentUI.ui
│   ├── EmployeeUI.ui
│   ├── ServiceUI.ui
│   ├── BillingUI.ui
│   ├── DayCareUI.ui
│   ├── InventoryUI.ui
│   ├── ExpensesUI.ui
│   ├── AnalyticsReportUI.ui
│   └── SettingUI.ui
│
├── Database/
│   ├── VCMS_MySQL.sql         # Database schema and initial data
│   └── SQL Files/             # Additional SQL scripts
│       ├── animal.sql
│       ├── appointments.sql
│       ├── employees.sql
│       ├── services.sql
│       ├── invoices.sql
│       └── triggers.sql
│
├── Config/
│   ├── config.txt             # Theme configuration
│   ├── mysql_config.config    # Database credentials
│   └── remember.config        # Saved login credentials
│
├── UI Theme/
│   ├── custom.css             # Custom CSS styling
│   ├── resources.qrc          # Qt resource file
│   └── resources_rc.py        # Compiled resources
│
├── resources/                 # Application resources
│   └── windowIcon.png
│
├── requirements.text          # Python dependencies
└── README.md                  # This file
```

## 🚀 Installation Guide

### Prerequisites
- **Python 3.8+** installed on your system
- **MySQL Server 5.7+** running and accessible
- **pip** package manager (usually included with Python)

### Step 1: Clone/Download the Project
```bash
# Navigate to your desired directory
cd path/to/projects

# Clone the repository or download the ZIP file
git clone <repository-url>
cd Simple-VCMS
```

### Step 2: Create Python Virtual Environment (Recommended)
```bash
# On Windows
python -m venv venv
venv\Scripts\activate

# On macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
# Upgrade pip to latest version
pip install --upgrade pip

# Install all required packages
pip install -r requirements.text
```

### Step 4: Database Setup

#### Option A: Using Automated Script
1. Open MySQL and create the database:
   ```bash
   mysql -u root -p
   ```

2. Run the SQL schema file:
   ```bash
   mysql -u root -p < VCMS_MySQL.sql
   ```

#### Option B: Manual Setup
1. Open MySQL command line or MySQL Workbench
2. Execute the SQL script from `VCMS_MySQL.sql`:
   - This creates the `VCMS` database
   - Creates all necessary tables
   - Inserts sample data for testing

### Step 5: Configure Database Connection

1. **Update `mysql_config.config`** file with your MySQL credentials:
   ```
   user = your_mysql_username
   password = your_mysql_password
   port = 3306
   ```

2. **Verify MySQL is running**:
   ```bash
   # On Windows
   mysql -u root -p -e "SELECT VERSION();"
   ```

### Step 6: (Optional) Configure Application Theme

Edit `config.txt` to set your preferred theme:
```
dark_amber.xml
```

## 🏃 How to Run

### Starting the Application

#### Method 1: Direct Python Execution
```bash
# Ensure virtual environment is activated
python App.py
```

#### Method 2: From Command Line
```bash
# Windows
python App.py

# macOS/Linux
python3 App.py
```

## 💡 Usage Guide

### Main Features

#### 1. Authentication
- Launch the application to see the **Login Window**
- Enter email and password
- Check **"Remember Me"** to auto-populate credentials on next launch
- Access level determines available features

#### 2. Dashboard/Home
- Central hub displaying key metrics
- Quick access to main features
- Recent activities and appointments

#### 3. Animal Management
- **Register New Animals**: Add pets with owner information and medical details
- **View Animal Records**: Search and filter animals
- **Medical History**: Track all treatments and medical conditions
- **Behavioral Notes**: Record behavioral warnings and special needs

#### 4. Appointment Management
- **Schedule Appointments**: Create appointments with specific dates/times
- **Assign Veterinarian**: Link appointments to available veterinarians
- **Track Status**: Monitor appointment status (Scheduled, Completed, Cancelled)
- **View History**: Access past appointments

#### 5. Service Management
- **Define Services**: Create veterinary services with descriptions
- **Set Pricing**: Configure service costs
- **Availability**: Manage service availability

#### 6. Billing System
- **Create Bills**: Generate invoices for rendered services
- **Apply Adjustments**: Add discounts or charges
- **Payment Tracking**: Monitor payment status
- **Bill History**: View past invoices and transactions

#### 7. Employee Management
- **Add Staff**: Register new employees with roles
- **Manage Roles**: Assign designations and access levels
- **Track Salaries**: Maintain salary information
- **Employment Status**: Track active/on-leave status

#### 8. Expense Management
- **Log Expenses**: Record clinic expenses
- **Approval Workflow**: Track expense approval status
- **Financial Reports**: Analyze expense patterns

#### 9. Day Care Services
- **Book Services**: Schedule pet daycare with specific dates and times
- **Special Notes**: Add allergy/behavioral information
- **Pricing**: Integrated with billing system

#### 10. Inventory Management
- **Track Supplies**: Monitor medical supplies and equipment
- **Stock Levels**: Track inventory quantities
- **Pricing**: Record supplier prices

#### 11. Analytics & Reports
- **Generate Reports**: Create reports on:
  - Appointment statistics
  - Animal population demographics
  - Revenue analysis
  - Expense summaries
  - Employee performance

#### 12. Settings
- **Theme Customization**: Apply different color themes
- **Application Configuration**: Adjust system settings
