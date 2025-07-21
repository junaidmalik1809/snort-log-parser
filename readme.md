📖 Project Title:
Automated Snort Log Parser with Python

🚀 Overview
This project demonstrates how to integrate Snort IDS with a custom Python automation script to parse and display alerts in real time.
It is part of my Phase 5 (Python for Cybersecurity Automation) learning roadmap.

✨ What It Does
✅ Monitors the Snort alert log file (/var/log/snort/alert.fast)
✅ Prints out all detected alerts in the console
✅ Helps security analysts quickly review IDS activity

🛠️ Technologies Used
🖥️ Snort IDS (installed on Ubuntu)

🐍 Python 3

Linux environment (Ubuntu 22.04+)

⚙️ Setup Steps
1. Install Snort
   ```  
   sudo apt update
   sudo apt install snort -y
   ```

2. Generate Traffic to Test
From another machine or VM:

```
nmap -sS 192.168.1.103
ping -c 4 192.168.1.103
```
3. Run Snort

```
sudo snort -A fast -i enp0s3 -c /etc/snort/snort.conf

```

Python Script to Parse Alerts
Saved this as parse_alerts.py:

```
alert_file = "/var/log/snort/alert.fast"

print("=== Snort Alerts Found ===")
with open(alert_file, "r") as f:
    for line in f:
        print(line.strip())
```
Ran it with:

```
sudo python3 parse_alerts.py

```

📌 Use Case
This script shows how a junior SOC analyst or security engineer can automate alert triage by parsing IDS logs programmatically.

✨ Future Enhancements
Filter alerts by priority

Color-code or highlight specific threats

Export alerts to CSV or JSON
