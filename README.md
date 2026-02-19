 🛡️ EDR Home Lab — SOC Attack & Detection Simulation
This project is a hands‑on cybersecurity home lab built to understand how real attackers behave and how security teams detect them.
* 🧑‍💻 "Kali Linux" = the attacker trying to break in
* 🖥️ "Windows Machine" = the victim being attacked
* 🎥 "Sysmon" = the security camera recording everything
* 📊 "Splunk" = the SOC control room analyzing the evidence

The goal is simple:generate attacks → collect logs → detect suspicious activity
just like a real SOC analyst would do.

🎯 Objectives

* Safely simulate real‑world cyber attacks
* Capture deep endpoint telemetry using Sysmon
* Forward and analyze logs in Splunk SIEM
* Detect common threats (brute force, PowerShell abuse, persistence)
* Build practical SOC analyst experience

 Lab Architecture

```
+-------------------+        Attack Traffic        +----------------------+
|   Kali Linux      |  --------------------------> |    Windows Victim    |
|   (Attacker)      |                               |  (Sysmon Installed) |
+-------------------+                               +----------+-----------+
                                                               |
                                                               | Sysmon Logs
                                                               v
                                                      +------------------+
                                                      |     Splunk SIEM  |
                                                      | (Log Analysis)   |
                                                      +------------------+
```



Attacker → Victim → Logs Generated → Splunk → Detection

 ⚙️ Lab Setup

1️⃣ Virtual Environment

* Installed "VirtualBox"
* Created two VMs:

  * Kali Linux (Attacker)
  * Windows (Victim)
* Configured both on the "same internal network"

* This creates an isolated and safe range.

2️⃣ Windows Endpoint Configuration

* Installed "Sysmon" on the Windows machine
* Applied "Olaf Hartong modular configuration"
* Verified logs in:

Now the endpoint has high‑visibility telemetry.
 3️⃣ Splunk SIEM Setup

* Installed Splunk Enterprise
* Installed Splunk Universal Forwarder on Windows
* Forwarded Sysmon logs into Splunk

Example log source:

spl
index=endpoint sourcetype=XmlWinEventLog:Microsoft-Windows-Sysmon/Operational

 At this stage, Splunk becomes your mini SOC.
4️⃣ Attack Simulation (Kali Linux)

The following controlled attacks were performed:


* payload execution
*  Network scanning

These actions intentionally generate logs for detection practice.

 Key Learning Outcomes

* Understood attacker vs defender mindset
* Learned endpoint telemetry analysis
* Built basic Splunk detections
* Practiced SOC investigation workflow

✅ Conclusion
This EDR home lab demonstrates how real-world attacks can be simulated and detected using endpoint telemetry and SIEM analysis.
It provides practical SOC experience by connecting attacker behavior to meaningful security alerts.
Overall, the project builds a strong foundation in threat detection, log analysis, and defensive cybersecurity operations.


  







