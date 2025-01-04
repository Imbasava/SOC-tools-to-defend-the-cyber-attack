# SOC Tools to Defend Cyber Attacks

This project implements a Security Operations Center (SOC) solution, leveraging multiple security tools to detect and prevent cyberattacks, such as brute force and DDoS attacks. It integrates Snort for intrusion detection, ELK Stack (Elasticsearch, Logstash, Kibana) for log management and visualization, and Fail2Ban for intrusion prevention.

## Key Features
- **Brute Force Attack Detection and Prevention**: Monitors failed SSH login attempts, visualizes the data, and blocks malicious IPs using Fail2Ban.
- **DDoS Attack Detection**: Analyzes traffic patterns to identify potential DDoS activity and provides real-time visualization through ELK dashboards.
- **Comprehensive Monitoring**: SOC setup includes log collection, intrusion detection, and automated response mechanisms.


---

## Visual Demonstration

### 1. Brute Force Attack from Kali Linux  
<img src="https://github.com/user-attachments/assets/15d9fe27-a054-4eae-bb18-f383bf74dbed" alt="Brute Force Attack" width="600" />

### 2. Traffic Visualization  
<img src="https://github.com/user-attachments/assets/b3cb852f-b17b-435f-95b2-f9805ef7d5b7" alt="Traffic Analysis" width="600" />

### 3. Banning the IP After Continuous Failed Login Attempts  
<img src="https://github.com/user-attachments/assets/ea1c9f3f-4aeb-4aff-a364-f18f32404613" alt="Fail2Ban Action" width="600" />

### 4. SOC Monitoring  
<img src="https://github.com/user-attachments/assets/ae9e2b7f-a259-42b9-9de1-998fd7ff0c42" alt="SOC Monitoring" width="600" />

---


## Table of Contents
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Use Cases](#use-cases)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Prerequisites
Before setting up the SOC environment, ensure you have:
- A Linux-based server (e.g., Ubuntu)
- Docker and Docker Compose installed
- Basic knowledge of network security and Linux command line

## Installation

### Clone the Repository
```bash
git clone https://github.com/Imbasava/soc-tools-to-defend-the-cyber-attack.git
```


### Install Dependencies
- Install Snort 2.9.20
- Set up the ELK stack using Docker Compose
- Install Fail2Ban

Refer to the detailed instructions for each tool in their respective directories.

## Configuration

### Snort
Update the `snort.conf` file with your network settings.

### ELK Stack
- Configure Logstash to parse Snort and Fail2Ban logs.
- Customize Kibana dashboards for visualization.

### Fail2Ban
Modify Fail2Ban configuration to suit your SSH server settings.

## Usage

### Starting the Services

#### Snort
```bash
sudo snort -c /etc/snort/snort.conf -i eth0  # Replace eth0 with your network interface
```
## Usage

### Starting the Services

#### Fail2Ban
```bash
sudo service fail2ban start
```
#### ELK Stack

```bash
sudo service logstash start
sudo service elasticsearch start
sudo service kibana start
````
## Monitoring and Detection
Use Kibana to monitor logs and visualize intrusion data.
Snort detects intrusions based on predefined rules.
Fail2Ban bans IP addresses after consecutive failed login attempts.
## Use Cases
 ### 1. Detecting and Preventing Brute Force Attacks on SSH
Detection: Snort logs multiple failed login attempts.
Visualization: Logs are analyzed in ELK.
Prevention: Fail2Ban blocks the offending IP.
 ### 2.  Detecting DDoS Attacks
Detection: Snort identifies traffic patterns indicative of a DDoS attack.
Visualization: ELK dashboards provide real-time insights.

## Contributing
Contributions are welcome! Please fork the repository, make your changes, and submit a pull request. Ensure your code adheres to the project's coding standards and includes appropriate documentation.
## License
MIT License


##  Acknowledgments
``` plaintext
Snort
ELK Stack
Fail2Ban
```
