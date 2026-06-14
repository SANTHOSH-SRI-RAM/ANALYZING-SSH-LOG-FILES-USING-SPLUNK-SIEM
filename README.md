# SSH Log Analysis Using Splunk SIEM

## Project Overview

This project demonstrates the analysis of SSH authentication logs using Splunk SIEM to identify suspicious login activities, monitor user behavior, and detect potential security threats. The project focuses on collecting SSH log data, extracting relevant fields, and performing security analytics using Splunk Search Processing Language (SPL).

## Objectives

- Monitor SSH login activity.
- Identify successful and failed login attempts.
- Detect brute-force attack patterns.
- Analyze user access behavior.
- Investigate suspicious source IP addresses.
- Generate security insights using Splunk dashboards and reports.

## Tools & Technologies

- Splunk Enterprise
- Linux SSH Logs
- SPL (Search Processing Language)
- Syslog Data Sources

## Project Architecture

1. SSH logs generated from Linux servers.
2. Logs ingested into Splunk.
3. Data indexed and normalized.
4. SPL queries used for analysis.
5. Security events visualized through dashboards.

## Dataset

The dataset contains SSH authentication logs with the following fields:

- Timestamp
- Username
- Source IP Address
- Login Status
- Session Information
- Commands Executed

## Key Analysis Performed

### 1. SSH Login Monitoring

Tracked all SSH authentication attempts and user activities.

```spl
index=ssh_logs
```

### 2. Failed Login Detection

Identified unauthorized access attempts.

```spl
index=ssh_logs action="failed"
| stats count by user
```

### 3. Top Source IP Analysis

Detected IP addresses generating the highest number of login attempts.

```spl
index=ssh_logs
| top src_ip
```

### 4. User Activity Analysis

Monitored user access frequency.

```spl
index=ssh_logs
| stats count by user
```

### 5. Anomaly Detection

Detected unusual spikes in SSH activity.

```spl
index=ssh_logs
| timechart span=1h count
```

## Findings

- Multiple failed login attempts were observed from specific source IPs.
- Certain users generated higher login frequencies than normal.
- Time-based analysis helped identify unusual authentication spikes.
- Suspicious activity patterns could indicate brute-force attempts.

## Security Recommendations

- Enable Multi-Factor Authentication (MFA).
- Restrict SSH access using firewall rules.
- Implement account lockout policies.
- Continuously monitor authentication logs.
- Block malicious IP addresses automatically.

## Skills Demonstrated

- Security Monitoring
- Log Analysis
- SIEM Operations
- Threat Detection
- Incident Investigation
- SPL Query Writing
- Security Analytics

## Learning Outcomes

Through this project, I gained hands-on experience in:

- Collecting and analyzing SSH logs.
- Writing SPL queries for threat detection.
- Investigating authentication anomalies.
- Using Splunk SIEM for security monitoring.
- Generating actionable security insights.

## Author

Santhosh Sri Ram V

Cybersecurity Analyst | SOC Analyst | Security Operations
