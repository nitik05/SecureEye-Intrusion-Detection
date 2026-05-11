# SecureEye-Intrusion-Detection
Python-based Log Intrusion Detection Tool for Linux Systems
# README.md

````markdown
# SecureEye IDS

SecureEye IDS is a Python-based Log Intrusion Detection System designed to monitor Linux authentication logs and detect suspicious login attempts or brute-force attacks.

---

## Features

- Detects repeated failed login attempts
- Monitors Linux authentication logs
- Identifies suspicious IP addresses
- Generates alert messages
- Stores suspicious IPs in a report file
- Lightweight and beginner-friendly

---

## Technologies Used

- Python 3
- Linux
- Regular Expressions (Regex)
- Authentication Log Monitoring

---

## Project Structure

```bash
SecureEye_v2/
│
├── intrusion_detector.py
├── suspicious_ips.txt
├── requirements.txt
├── README.md
├── LICENSE
├── .gitignore
├── screenshots/
├── reports/
└── logs/
````

---

## Installation

### Clone Repository

```bash
git clone https://github.com/yourusername/SecureEye-IDS.git
cd SecureEye-IDS
```

### Install Requirements

```bash
pip install -r requirements.txt
```

---

## Usage

Run the tool using:

```bash
sudo python3 intrusion_detector.py
```

---

## Sample Output

```bash
ALERT: Suspicious IP Detected
IP Address: 192.168.1.10
Failed Attempts: 7
```

---

## Future Enhancements

* Real-time monitoring
* Email alerts
* Dashboard integration
* Machine learning detection
* Automatic firewall blocking

---

## Author

Nitik Meena

---

## License

This project is licensed under the MIT License.

````

---

# requirements.txt

```txt
colorama
````

---

# .gitignore

```gitignore
# Python cache
__pycache__/
*.pyc
*.pyo
*.pyd

# Virtual environment
venv/
env/

# Logs
*.log

# Reports
suspicious_ips.txt

# VS Code
.vscode/

# System files
.DS_Store
Thumbs.db
```

---

# LICENSE

```text
MIT License

Copyright (c) 2026 Nitik Meena

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND.
```

---

# intrusion_detector.py

```python
import re
from collections import defaultdict
from colorama import Fore, init

init(autoreset=True)

log_file = '/var/log/auth.log'
attempts = defaultdict(int)
threshold = 5

print(Fore.CYAN + '[+] SecureEye IDS Started...')

try:
    with open(log_file, 'r') as file:
        for line in file:
            if 'Failed password' in line:
                match = re.search(r'from (\d+\.\d+\.\d+\.\d+)', line)

                if match:
                    ip = match.group(1)
                    attempts[ip] += 1

    report = open('suspicious_ips.txt', 'w')

    for ip, count in attempts.items():
        if count > threshold:
            alert = f'[ALERT] {ip} has {count} failed login attempts'
            print(Fore.RED + alert)
            report.write(alert + '\n')

    report.close()

    print(Fore.GREEN + '[+] Scan Completed Successfully.')

except FileNotFoundError:
    print(Fore.RED + '[-] Authentication log file not found.')
```

---

# Folder Names To Create

Create these folders manually inside SecureEye_v2:

```text
screenshots
reports
logs
```

---

# Recommended GitHub Repository Description

```text
Python-based Log Intrusion Detection System for Linux authentication log monitoring and brute-force attack detection.
```

---

# Recommended Topics/Tags For GitHub

```text
python
cybersecurity
intrusion-detection
linux
soc
ids
log-monitoring
ethical-hacking
security
python-project
```
