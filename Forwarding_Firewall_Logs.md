## Lab: Forwarding IPFire System Logs to Zeek and Elastic SIEM

Objective: The objective of this lab is to demonstrate how to forward system logs from an IPFire firewall to Zeek (formerly known as Bro) for analysis, and then to Elastic SIEM for visualization and monitoring.

Prerequisites:

    IPFire firewall installed and configured.
    Zeek installed and configured to analyze network traffic.
    Elastic SIEM instance set up and running.
    Basic knowledge of Linux commands and network configurations.

Materials:

    IPFire firewall.
    Server running Zeek.
    Elastic SIEM instance.

Steps:

Step 1: Configure IPFire Syslog

    Log in to the IPFire web interface.
    Navigate to Services > Log Files > Settings.
    Under "Remote Logging," enter the IP address of the server running Zeek and the port number (usually 514).
    Choose the log types you want to forward (e.g., firewall, proxy, IDS).
    Click "Save" to apply the changes.

Step 2: Configure Zeek

    Log in to the server running Zeek.

    Edit the Zeek configuration file (zeekctl.cfg) to include a syslog input.

    Add the following lines to the configuration file:
    makefile

    [zeek] type=Syslog host=<IPFire_IP_Address>

    Replace <IPFire_IP_Address> with the IP address of your IPFire firewall.

    Save the changes and restart Zeek.

Step 3: Verify Zeek Configuration

    Monitor Zeek logs to ensure that it is receiving syslog data from IPFire.

    Use the following command to tail Zeek logs:
    bash

    tail -f /var/log/zeek/conn.log

    Replace conn.log with the appropriate log file based on your Zeek configuration.

Step 4: Configure Logstash

    Log in to the server where Elastic SIEM is installed.

    Edit the Logstash configuration file (logstash.yml).

    Add a syslog input to collect logs from Zeek. Example configuration:
    graphql

    input { syslog { port => 514 type => "zeek" } }

    Save the changes and restart Logstash.

Step 5: Verify Logstash Configuration

    Monitor Logstash logs to ensure that it is receiving syslog data from Zeek.

    Use the following command to tail Logstash logs:
    bash

    tail -f /var/log/logstash/logstash-plain.log

Step 6: Index Data in Elasticsearch

    Ensure that Logstash is indexing syslog data into Elasticsearch.
    Monitor Elasticsearch indices to verify data ingestion.

Step 7: View Data in Kibana

    Log in to Kibana.
    Navigate to the SIEM app.
    Search for and visualize the data ingested from IPFire via Zeek.
    Create custom dashboards and alerts as needed.

Step 8: Test the Setup

    Generate network traffic that triggers IPFire firewall rules.
    Monitor Zeek logs to ensure that it detects and analyzes the traffic.
    Verify that the analyzed data appears in Elastic SIEM for visualization and monitoring.

Conclusion: In this lab, you have successfully configured IPFire to forward system logs to Zeek for analysis. You then set up Logstash to ingest the analyzed logs from Zeek and index them into Elasticsearch for visualization in Elastic SIEM. This setup allows for comprehensive monitoring and analysis of network traffic, enhancing the security posture of your environment.
