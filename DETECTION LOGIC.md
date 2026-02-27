✅ DELIVERABLE 1
Detection Logic & Explanation
Security Monitoring & Incident Response – Detection Logic
Objective

To design structured detection rules for identifying suspicious activity through log analysis and monitoring workflows.

1️⃣ Activity & Log Analysis
Logs to Monitor

Authentication logs

Web server logs

API access logs

Application logs

System logs

Firewall logs

2️⃣ Detection Logic Rules
🔴 Rule 1: Brute Force Login Attempt

Detection Logic:

Trigger alert if:

More than 5 failed login attempts

From same IP

Within 5 minutes

Pseudo Logic:

IF failed_login_attempts > 5
AND time_window <= 5 minutes
THEN alert = "Possible Brute Force Attack"

Why This Works:
Attackers try multiple passwords rapidly.

🔴 Rule 2: Suspicious Admin Access

Trigger alert if:

Non-admin user accesses admin endpoint
OR

Admin login from new geographic location

IF user_role != admin
AND endpoint = /admin/*
THEN alert
🟠 Rule 3: Impossible Travel Detection

If user logs in:

From USA

Then 10 minutes later from Germany

Flag as suspicious.

🟠 Rule 4: Excessive API Requests

Trigger if:

100 requests per minute from one IP

Possible:

DoS attempt

Bot scraping

🟡 Rule 5: Suspicious File Upload

Trigger if:

File extension = .php / .exe / .js

Upload endpoint accessed
