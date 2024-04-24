Lab: Intrusion Detection System (IDS)

https://www.youtube.com/watch?v=2XLzMb9oZBI&t=425s

Links to an external site.

Objective: The objective of this lab is to guide participants through setting up a home lab for Elastic Stack Security Information and Event Management (SIEM). Participants will learn how to set up an Elastic Cloud instance, install and configure a Kali Linux VM, forward logs from the Kali VM to the SIEM, generate security events, query and analyze logs, create visualizations and dashboards, and set up alerts.

Prerequisites:

    VirtualBox or VMware installed on your computer.
    Basic knowledge of Linux and virtualization software.

Overview of Tasks:

    Set up a free Elastic account and create an Elastic Cloud deployment.
    Install and configure a Kali Linux VM.
    Configure Elastic Agent on the Kali VM to forward logs to the SIEM.
    Generate security events on the Kali VM.
    Query for security events in the Elastic SIEM.
    Create a dashboard to visualize security events.
    Create alerts for security events.

Task 1: Set up an Elastic Account

    Sign up for a free trial at https://cloud.elastic.co/registration 

Links to an external site..
Log in to the Elastic Cloud console at https://cloud.elastic.co

    Links to an external site..
    Click on “Start your free trial.”
    Create a new deployment selecting “Elasticsearch” as the deployment type.
    Choose a region and deployment size, then click on “Create Deployment.”
    Wait for the deployment to be ready, then click “continue.”

Task 2: Setting up the Kali Linux VM

    Download the Kali Linux VM from https://www.kali.org/get-kali/#kali-virtual-machines 

    Links to an external site..
    Create a new VM using the Kali VM file in your preferred virtualization platform (e.g., VirtualBox, VMware).
    Follow the on-screen prompts to install Kali.
    Once installed, log in to the Kali VM using the credentials “kali” for both username and password.

Task 3: Setting up the Agent to Collect Logs

    Log in to the Elastic SIEM instance and navigate to the Integrations page.
    Search for “Elastic Defend” and click on it to open the integration page.
    Click on “Install Elastic Defend” and follow the instructions to install the agent on the Kali VM.
    Once installed, verify the agent status by running sudo systemctl status elastic-agent.service on the Kali terminal.

Task 4: Generating Security Events on the Kali VM

    Install Nmap on the Kali VM by running sudo apt-get install nmap.
    Run an Nmap scan on the Kali machine using sudo nmap <vm-ip>.
    Run additional Nmap scans with different options to generate various security events.

Task 5: Querying for Security Events in the Elastic SIEM

    Inside your Elastic Deployment, navigate to the “Logs” tab under “Observability.”
    Enter a search query to filter the logs, e.g., event.action: “nmap_scan” or process.args: “sudo”.
    Click on “Search” to execute the query and view the results.

Task 6: Creating a Dashboard to Visualize Events

    Navigate to the Elastic web portal and click on “Dashboards” under “Analytics.”
    Click on “Create dashboard” and then “Create Visualization.”
    Select “Area” or “Line” as the visualization type and configure it to show event counts over time.
    Save the visualization and complete the dashboard settings.

Task 7: Creating an Alert

    Click on “Alerts” under “Security” in the Elastic web portal.
    Click on “Manage rules” and then “Create new rule.”
    Define the rule conditions using a custom query, e.g., to detect Nmap scan events.
    Provide a name, description, and severity level for the alert.
    Configure the action to be taken when the rule is triggered.
    Click on “Create and enable rule” to create the alert.

Conclusion:

In this lab, you have set up a home lab for Elastic SIEM using Elastic Cloud and a Kali Linux VM. You configured the Elastic Agent to forward logs from the Kali VM to the SIEM, generated security events on the Kali VM, queried and analyzed the logs in the SIEM, created a dashboard to visualize security events, and set up an alert to detect security events. This lab provides valuable hands-on experience in security monitoring and incident response using Elastic SIEM.
