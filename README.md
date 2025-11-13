# Pharma Maintenance PowerApp Demo

This repository contains a **Power Platform maintenance management system**.

> ⚠️ **Disclaimer**\
> This is an **independent personal demo**.\
> It is **not an official product**, and it does **not** contain any
> confidential or proprietary information from any company.\
> All data inside this solution is **sample data** created solely for
> demonstration and educational purposes.

------------------------------------------------------------------------

## 📌 Project Overview

Equipment maintenance system built on Microsoft Power Platform:

### **✔ Power Apps (Canvas App)**

App for technicians to enter new maintenance logs. Adding, removing, or modifying entries in the app updates the `maintenanceLog` dataverse.

### **✔ Dataverse Tables**

- **`maintenanceLog`** --- dataverse that the app is built on top of
- **`AlertLogs`** --- automatically created by Power Automate for critical status entries

### **✔ Power Automate Flow**

When a technician enters a log and machine status is critical, Power Automate automatically creates an entry in the `AlertLogs` dataverse.

### **✔ Power BI Dashboard**

Power BI dashboard built on top of the dataverse data.

The Power BI report is fully editable and located in `/powerbi/`.

------------------------------------------------------------------------

## 🧱 Solution Architecture

       +---------------------------+
       |      Canvas App          |
       |  (Technician Interface)  |
       +------------+-------------+
                    |
                    v
       +---------------------------+
       |    maintenanceLog         |
       |    Dataverse              |
       +-------------+-------------+
                     |
                     v
       +---------------------------+
       |     Power Automate Flow   |
       |  (Critical status →       |
       |   AlertLogs dataverse)    |
       +-------------+-------------+
                     |
                     v
       +---------------------------+
       |       Power BI Report     |
       +---------------------------+

------------------------------------------------------------------------

## 📂 Repository Structure

    pharma-maintenance-powerapp-demo/
    │
    ├── solution/
    │   └── PharmaMaintenanceDemo.zip        # Exported unmanaged solution
    │
    ├── unpacked/                            # Text-based source version of the solution
    │   ├── CanvasApps/
    │   ├── Workflows/
    │   ├── Customizations.xml
    │   └── ... (Dataverse + Flow metadata)
    │
    ├── powerbi/
    │   └── MaintenanceDashboard.pbix         # Power BI dashboard
    │
    ├── documentation/
    │   ├── explanation.md (optional)
    │   └── screenshots/ (optional)
    │
    ├── LICENSE
    ├── .gitignore
    └── README.md

This layout follows Microsoft ALM best practices.

------------------------------------------------------------------------

## 🚀 How to Import the Power Apps Solution

1.  Go to **Power Apps → Solutions**
2.  Click **Import**
3.  Select the file:\
    `solution/PharmaMaintenanceDemo.zip`
4.  Complete the wizard
5.  After import, manually update:
    -   Connections\
    -   Environment variables (if any)\
    -   Flow activation\
6.  Open the Canvas App from the solution and test it

------------------------------------------------------------------------

## 📊 Power BI Dashboard

The Power BI report is located at:

    /powerbi/MaintenanceDashboard.pbix

To open it:

1.  Download the `.pbix` file\
2.  Open in **Power BI Desktop**\
3.  Reconnect to your Dataverse environment (Home → Transform Data →
    Data Source Settings)

The report includes: - Maintenance KPI cards\
- Task distribution charts\
- Equipment issue breakdown\
- Technician activity insights

------------------------------------------------------------------------

## 🛠️ Tools Used

-   **Power Apps (Canvas)**\
-   **Microsoft Dataverse**\
-   **Power Automate**\
-   **Power BI Desktop**\
-   **Power Platform CLI (PAC)**\
-   **Git & GitHub**

------------------------------------------------------------------------

## 🎯 Purpose

Equipment maintenance management system for technicians to log maintenance events with automated critical status handling and Power BI analytics.

------------------------------------------------------------------------

## 📬 Contact

If you'd like more details about how this was built or want to discuss
workflow improvements, feel free to reach out.
