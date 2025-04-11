# SOC Automation Lab

## Objective
The SOC Automation Platform project aims to create an integrated security operations workflow that:

- Automates routine SOC tasks to reduce manual analysis and response time
- Demonstrates end-to-end threat detection and response using open-source tools
- Provides a reusable reference architecture for small/medium security teams
- Bridges these core security technologies:
  - Wazuh (SIEM for detection)
  - TheHive (Case management)
  - Shuffle (Workflow automation)


## Skills Learned

- Designed correlation rules in Wazuh for detecting brute force attacks, suspicious processes.
- Developed custom TheHive templates for consistent case documentation
- Development of critical thinking and problem-solving skills in cybersecurity.

## Workflow Breakdown

1. **Windows 10:** Sends security event logs to Wazuh for analysis.
2. **Wazuh Manager:** Detects security threats, triggers alerts, and performs initial responses.
3. **Shuffle:** Acts as the automation hub, receiving Wazuh alerts and:
	  - Enriching IOCs (Indicators of Compromise) using OSINT sources.
    - Creating case alerts in TheHive for further investigation.
    - Sending email notifications with responsive actions.
4. **TheHive:** Serves as the case management platform, logging incidents for investigation.
5. **Email Notifications:** Used for alerting SOC analysts and triggering automated responses.

![Lab WorkFlow](SOC_Automation.png)


## Steps

### Step 1: Local Environment Setup

**We will need these machines during this lab.**

| VM Name      | OS           | Allocation      | 
| ------------ | ------------ | --------------- | 
| win10-client | Windows 10   | 2 vCPU, 4GB RAM |
| wazuh-server | Ubuntu 22.04 | 2 vCPU, 4GB RAM |
| TheHive      | Ubuntu 22.04 | 2 vCPU, 4GB RAM | 

Installing these machines on Vmware is straightforward and does not need to be added here.

#### Step 1.2: Wazuh Installation

```
curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```

**Note to save username and password show after installation**

- username: `admin`
- password: `.Uk60McQSYZnnIrKup*+mUbr5To7eLAc

  **After that, try to login to Wazuh server, search for your server IP in any web browser**

`https://192.168.244.132` ---> for me

  ![Wazuh_dash](https://github.com/user-attachments/assets/218a7790-72a1-4f72-a8ec-0375b24efb93)

#### Step 1.3: Install TheHive

**The easiest way to install and config thehive is to follow this [docment](https://docs.strangebee.com/thehive/installation/step-by-step-installation-guide/)
After that, go to your browser search about you Ubunt `machine_ip:9000`, Will find page like that.
![TheHive_Server](https://github.com/user-attachments/assets/8fe4f965-0b0c-477b-827e-970812fe68ba)





