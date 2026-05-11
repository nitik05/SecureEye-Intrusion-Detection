# SecureEye-Intrusion-Detection
Python-based Log Intrusion Detection Tool for Linux Systems
# SecureEye IDS

SecureEye IDS is a Python-based Log Intrusion Detection System designed to monitor Linux authentication logs and detect suspicious login attempts or brute-force attacks.

---

# Features

- Detects repeated failed login attempts
- Monitors Linux authentication logs
- Identifies suspicious IP addresses
- Generates alert messages
- Stores suspicious IPs in a report file
- Lightweight and beginner-friendly

---

# Technologies Used

- Python 3
- Linux
- Regular Expressions (Regex)
- Authentication Log Monitoring

---

# Project Structure

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
```

---

# Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/SecureEye-IDS.git
cd SecureEye-IDS
```

## Install Requirements

```bash
pip install -r requirements.txt
```

---

# Usage

Run the tool using:

```bash
sudo python3 intrusion_detector.py
```

---

# How It Works

1. Reads Linux authentication logs
2. Searches for failed password attempts
3. Extracts IP addresses using Regex
4. Counts repeated failed login attempts
5. Detects suspicious IP addresses
6. Generates alerts and saves reports

---

# Sample Output

```bash
[ALERT] 192.168.1.10 has 7 failed login attempts
```

---

# Future Enhancements

- Real-time monitoring
- Email alerts
- Dashboard integration
- Machine learning detection
- Automatic firewall blocking
- Threat intelligence integration

---

# Applications

- SOC monitoring practice
- Linux server security
- Educational cyber security projects
- Beginner IDS learning
- Security log analysis

---

# Requirements

- Python 3
- Linux (Ubuntu/Kali Recommended)
- Terminal Access

---

# Author

Nitik Meena

---

# License

This project is licensed under the MIT License.

---

# Disclaimer

This project is created for educational and ethical learning purposes only. Do not use this tool against systems without proper authorization.
