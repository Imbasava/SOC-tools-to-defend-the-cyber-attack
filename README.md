


This project implements a Security Operations Center (SOC) with tools to detect and prevent brute force and DDoS attacks. Our SOC combines Snort for intrusion detection, ELK (Elasticsearch, Logstash, Kibana) for log management and visualization, and Fail2Ban for intrusion prevention. This setup ensures effective monitoring and response to cyber threats.

Features
Intrusion Detection: Snort monitors network traffic for suspicious patterns.
Log Management & Visualization: ELK stack collects, processes, and visualizes logs.
Intrusion Prevention: Fail2Ban bans IPs with repeated failed login attempts.
Prerequisites
Before beginning, ensure the following requirements are met:

A Linux-based server (e.g., Ubuntu)
Docker and Docker Compose installed
Basic knowledge of network security and Linux command line

Installation
Step 1: Clone the Repository
Clone the project repository:
git clone https://github.com/Imbasava/soc-tools-to-defend-the-cyber-attack.git

Step 2: Install Dependencies
Install Snort 2.9.20
Snort will monitor and detect suspicious traffic based on defined rules.
![image](https://github.com/user-attachments/assets/b3cb852f-b17b-435f-95b2-f9805ef7d5b7)

Set Up the ELK Stack
Using Docker Compose, set up Elasticsearch, Logstash, and Kibana to manage and visualize logs.
![image](https://github.com/user-attachments/assets/ea1c9f3f-4aeb-4aff-a364-f18f32404613)

Install Fail2Ban
Fail2Ban will monitor failed login attempts and ban IPs based on specified criteria.

Configuration
Snort
Update the snort.conf file with your network settings.
ELK Stack (Elasticsearch, Logstash, Kibana)
Configure Logstash to parse Snort and Fail2Ban logs.
Customize Kibana dashboards to visualize attacks and blocked IPs.

Usage

Start Snort

sudo snort -c /etc/snort/snort.conf -i eth0  # Replace 'eth0' with your network interface

Start Fail2Ban

sudo service fail2ban start
Start ELK Stack

sudo service logstash start
sudo service elasticsearch start
sudo service kibana start

Monitoring and Detection
Kibana enables real-time log monitoring and visual data representation.
Snort detects intrusions based on predefined rules, sending alerts to ELK.
Fail2Ban automatically bans IPs with repeated failed login attempts.

Use Cases
1. Detecting and Preventing Brute Force Attacks on SSH
Snort detects multiple failed login attempts.
Fail2Ban bans the IP after a specified number of failed logins.
ELK Stack visualizes logs for monitoring.

![image](https://github.com/user-attachments/assets/15d9fe27-a054-4eae-bb18-f383bf74dbed)

2. Detecting DDoS Attacks
Snort detects patterns indicative of a DDoS attack.
ELK visualizes attack patterns for real-time analysis.
Further measures can be implemented for advanced DDoS mitigation.

Contributing
We welcome contributions! Please fork the repository, make changes, and create a pull request. Make sure your code follows project standards and includes appropriate documentation.


License
Distributed under the MIT License. See LICENSE for more information.

Acknowledgments
Snort
ELK Stack
Fail2Ban

