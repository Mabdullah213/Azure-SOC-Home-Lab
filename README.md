# Azure Security Operations (SOC) Home Lab

This repository contains my Azure-based **Security Operations Center (SOC) lab**, designed to simulate real-world detection and response scenarios using **Microsoft Sentinel**.  
The lab demonstrates how to monitor, detect, and respond to security threats using **KQL detections**, **Logic Apps**, and **automated playbooks**.

---

##  Project Overview

The goal of this project is to build a functional **SOC environment** in Azure that centralizes alert monitoring and enables automated incident response.

### Key Features
- **Centralized Monitoring:** Built using Microsoft Sentinel connected to Azure resources.
- **Custom Detections:** Developed KQL analytics rules for scenarios like:
  - Brute-force login attempts  
  - Token theft or session hijacking  
  - Privilege escalation events
- **Automated Response:** Implemented Logic Apps and Playbooks to:
  - Isolate compromised users or devices  
  - Gather forensic evidence automatically  
  - Notify the SOC team for investigation
  While I did use the visual tool found in Sentinel, I have made some Playboks that can be copied to the 'Code View', and used.

---

## Repository Structure

Azure-SOC-HomeLab/
│
├── detections/
│ ├── brute_force_detection.kql
│ ├── token_theft_detection.kql
│ └── privilege_escalation_detection.kql
│
├── playbooks/
│ ├── isolate_user_playbook.json
│ ├── evidence_collection_playbook.json
│ └── notification_playbook.json
│
└── README.md



- **detections/** → Contains KQL analytics rules used in Microsoft Sentinel  
- **playbooks/** → Contains Logic App definitions for automated responses  

---

##  How it all works

1. **Data Ingestion:**  
   Connect Azure services (e.g., Azure AD, Defender for Cloud, etc.) to Microsoft Sentinel.

2. **Detection:**  
   Sentinel runs the KQL rules stored in the `detections/` folder to identify suspicious activity.

3. **Response:**  
   When a rule triggers, the corresponding playbook from `playbooks/` is executed automatically.

---

##  Tools & Services Used

- **Microsoft Sentinel** – SIEM for detection and analysis  
- **Azure Logic Apps** – For automated workflows  
- **Azure Monitor Logs / Log Analytics** – For data collection  
- **Kusto Query Language (KQL)** – For custom analytics rules  

---

##  Getting Started with all this

To replicate or test this lab in your environment:

1. **Deploy Microsoft Sentinel** on your Azure subscription.  
2. **Import Detections**  
   - Go to *Sentinel → Analytics → Create → Scheduled query rule*  
   - Paste the contents of any `.kql` file from the `detections/` folder  
3. **Import Playbooks**  
   - Go to *Logic Apps → Add → Import from JSON template*  
   - Upload the desired `.json` playbook file  
4. **Test Your Setup**  
   - Simulate brute-force or privilege escalation activity  
   - Monitor alerts and verify the automated responses

---

##  License

This project is provided for **educational and research purposes only**.  
Use responsibly in lab or test environments.

---

##  Author

**Muhammad Abdullah Javed**  
Azure Security | Cloud | SOC Automation  
[LinkedIn](https://linkedin.com/in/mjaved213) • [GitHub](https://github.com/Mabdullah213)
