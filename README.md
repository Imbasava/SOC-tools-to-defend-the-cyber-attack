
# SOC Tools to Detect and Prevent Cyber Attacks

In this tutorial, we are going to detect Brute Force Attacks and prevent them, as well as detect DDoS attacks.

## Screenshots

### Brute Force Attack from Kali Linux
![Brute Force Attack](https://github.com/user-attachments/assets/15d9fe27-a054-4eae-bb18-f383bf74dbed =600x400)

### All Traffic Visualization
![Traffic Visualization](https://github.com/user-attachments/assets/b3cb852f-b17b-435f-95b2-f9805ef7d5b7 =600x400)

### Banning IP After Continuous Failed Login Attempts
![Banning IP](https://github.com/user-attachments/assets/ea1c9f3f-4aeb-4aff-a364-f18f32404613 =600x400)

### SOC Monitoring
![SOC Monitoring](https://github.com/user-attachments/assets/ae9e2b7f-a259-42b9-9de1-998fd7ff0c42 =600x400)

---

## Introduction

This project combines multiple security tools to create a comprehensive Security Operations Center (SOC) solution. The tools implemented include **Snort** for intrusion detection, **ELK (Elasticsearch, Logstash, Kibana)** for log management and visualization, and **Fail2Ban** for intrusion prevention. This setup includes use cases for detecting brute force attacks on an SSH server and detecting DDoS attacks.

---

## Prerequisites

Before you begin, ensure you have met the following requirements:
- A Linux-based server (e.g., Ubuntu)
- Docker and Docker Compose installed
- Basic knowledge of network security and the Linux command line.

---

## Installation

### Step 1: Clone the Repository

To clone the repository, run:
```bash
git clone https://github.com/Imbasava/soc-tools-to-defend-the-cyber-attack.git


## Step 2: Install Dependencies

1. **Install Snort 2.9.20**
2. **Set up the ELK stack** using Docker Compose
3. **Install Fail2Ban**

Detailed instructions for each tool are provided in their respective directories within the repository.

---

## Configuration

### Snort
- Update the `snort.conf` file with your network settings.

### ELK Stack (Elasticsearch, Logstash, Kibana)
- Configure Logstash to parse Snort and Fail2Ban logs.
- Customize Kibana dashboards for visualization.

---

## Starting the Services

### Start Snort
```bash
sudo snort -c /etc/snort/snort.conf -i eth0  # Replace 'eth0' with your network interface

### Start Fail2Ban
```bash
sudo service fail2ban start

sudo service logstash start
sudo service elasticsearch start
sudo service kibana start

## Monitoring and Detection
Use Kibana to monitor logs and visualize data.
Snort will detect intrusions based on the defined rules.
Fail2Ban will ban IP addresses based on failed login attempts and other criteria.
##Use Cases
Detecting and Preventing Brute Force Attacks on SSH

Snort detects multiple failed login attempts.
Logs are sent to ELK for visualization.
Fail2Ban blocks the offending IP after a set number of failed attempts.
Detecting DDoS Attacks

Snort detects patterns indicative of a DDoS attack.
Logs are analyzed in ELK for real-time visualization.
Additional measures can be implemented to mitigate the attack.
##Contributing
Contributions are welcome! Please fork the repository and create a pull request with your changes. Ensure that your code follows the project's coding standards and includes appropriate documentation.
