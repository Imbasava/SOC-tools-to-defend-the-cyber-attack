In this tutorial we are going to detect the Brute Force Attack and prevent it. Aslo detects the DDoS attack.

Brute force attack from the kali linux.

## Tutorial: Detecting and Preventing Brute Force & DDoS Attacks

In this tutorial, we detect brute force attacks and prevent them, as well as detect DDoS attacks.

<p align="center">
    <img src="https://github.com/user-attachments/assets/15d9fe27-a054-4eae-bb18-f383bf74dbed" alt="Brute force attack from Kali Linux">
	
    <br><em>Brute force attack from Kali Linux</em>
</p>

<p align="center">
    <img src="https://github.com/user-attachments/assets/b3cb852f-b17b-435f-95b2-f9805ef7d5b7" alt="All traffic displayed" width="500">
	
    <br><em>All network traffic</em>
</p>


<p align="center">
    <img src="https://github.com/user-attachments/assets/ea1c9f3f-4aeb-4aff-a364-f18f32404613" alt="Banning IP after failed login attempts">
	
    <br><em>Banning the IP after continuous failed login attempts</em>
</p>


<p align="center">
    <img src="https://github.com/user-attachments/assets/ae9e2b7f-a259-42b9-9de1-998fd7ff0c42" alt="SOC Monitoring">
	
    <br><em>SOC Monitoring</em>
</p>



SOC Toolset Implementation

Introduction

This project combines multiple security tools to create a comprehensive Security Operations Center (SOC) solution. The tools implemented include Snort for intrusion detection, ELK (Elasticsearch, Logstash, Kibana) for log management and visualization, and Fail2Ban for intrusion prevention. This setup includes use cases for detecting brute force attacks on an SSH server and detecting DDoS attacks.

Prerequisites
Before you begin, ensure you have met the following requirements:

A Linux-based server (e.g., Ubuntu)
Docker and Docker Compose installed
Basic knowledge of network security and Linux command line.

Installation

Step 1: Clone the Repository

Copy code->
git clone https://github.com/Imbasava/soc-tools-to-defend-the-cyber-attack.git


Step 2: Install Dependencies

  *Install Snort 2.9.20
  *Set up the ELK stack using Docker Compose
  *Install Fail2Ban
Detailed instructions for each tool are provided in their respective directories within the repository.

Configuration
Snort
 -Update the snort.conf file with your network settings.

ELK Stack(elasticssearch,logstash,kibana)
 -Configure Logstash to parse Snort and Fail2Ban logs.
 -Customize Kibana dashboards for visualization.

# Start Snort 
sudo snort -c /etc/snort/snort.conf -i eth0     #eth0 is your network interface
# Start Fail2Ban
sudo service fail2ban start
# Start ELK
sudo service logstash start
sudo service elasticsearch start
sudo service kibana start

Monitoring and Detection

Use Kibana to monitor logs and visualize data.
Snort will detect intrusions based on the defined rules.
Fail2Ban will ban IP addresses based on failed login attempts and other criteria.

Use Cases
1. Detecting and Preventing Brute Force Attacks on SSH
Snort detects multiple failed login attempts.
Logs are sent to ELK for visualization.
Fail2Ban blocks the offending IP after a set number of failed attempts.
2. Detecting DDoS Attacks
Snort detects patterns indicative of a DDoS attack.
Logs are analyzed in ELK for real-time visualization.
Additional measures can be implemented to mitigate the attack.

Contributing
Contributions are welcome! Please fork the repository and create a pull request with your changes. Ensure that your code follows the project's coding standards and includes appropriate documentation.

License


Acknowledgments
Snort
ELK Stack
Fail2Ban
