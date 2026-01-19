# Automated-Phishing-Detection-and-Response-System

Phishing Email Detector with Automated Quarantine and Alert System
This project is an automated tool for detecting, quarantining, and alerting about suspicious phishing emails. It integrates with the VirusTotal API to scan URLs found in emails, flags potential phishing threats, quarantines them, and notifies the security team.

Table of Contents
Features

Requirements

Setup Instructions

Configuration

Usage

Project Files

Disclaimer

License

Features
Automated Email Scanning: Fetches unread emails and scans their content for suspicious URLs.

Phishing Detection: Uses VirusTotal API to check for malicious URLs in email bodies.

Email Quarantine: Flags and moves potentially harmful emails to quarantine.

Alert System: Sends an alert email to notify the security team of any phishing attempt.

Logging: Logs flagged emails for record-keeping and review.

Requirements
Python 3.6+

Required packages:

requests -- for API calls

imaplib and email -- for email handling

re and base64 -- for URL extraction and encoding

A VirusTotal API key for URL analysis

Setup Instructions
1. Clone the Repository:

    git clone https://github.com/jagdishtripathy/Email-phishing-detector.git
    cd Email-phishing-detector
2. Create a Virtual Environment (optional but recommended):

    python3 -m venv myenv
    source myenv/bin/activate  # On Windows: myenv\Scripts\activate
3. Install Required Packages:

    pip install requests
4. Configure Email and VirusTotal API:

   Update email_handler.py:

    EMAIL_ADDRESS = 'your_email@example.com'
    EMAIL_PASSWORD = 'your_password'
    IMAP_SERVER = 'imap.example.com'
   Update phishing_detection.py:

    api_key = 'your_virustotal_api_key'
Configuration
In email_handler.py, set:

EMAIL_ADDRESS: Your email address

EMAIL_PASSWORD: Your email account password or app-specific password

IMAP_SERVER: IMAP server address (e.g., imap.gmail.com for Gmail)

In phishing_detection.py, set:

api_key: Your VirusTotal API key
Usage
To run the project, execute:

python main.py
The program will:

Connect to the email inbox and fetch unread emails.

Check each email's content for URLs and scan them using VirusTotal.

Quarantine flagged phishing emails.

Send an alert email to the security team.

Log details of flagged emails.

Project Files
main.py -- Orchestrates the overall detection process

email_handler.py -- Handles email connection and fetching

phishing_detection.py -- Uses VirusTotal to scan URLs

quarantine.py -- Moves flagged emails to quarantine

alert.py -- Sends alert emails

logger.py -- Logs flagged email details
