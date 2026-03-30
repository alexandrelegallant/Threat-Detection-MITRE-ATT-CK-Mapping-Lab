# Threat-Detection-MITRE-ATT-CK-Mapping-Lab

## Objective

This project aimed to analyse real-world Industrial Control System (ICS) honeypot data to identify attacker behaviour and map observed activities to the MITRE ATT&CK for ICS framework.
The lab focused on building a full SIEM workflow using the ELK Stack, transforming raw telemetry into actionable security insights through log analysis and visualisation.

### Skills Learned

- Practical use of SIEM (ELK Stack) for log ingestion, analysis, and visualisation
- Log analysis of 97,000+ ICS honeypot records to detect attack patterns
- Understanding of ICS protocols (SNMP, IEC-104, Kamstrup, Guardian AST)
- Mapping real attack behaviours to MITRE ATT&CK techniques (Discovery & Collection)
- Identifying reconnaissance activity such as scanning and enumeration
- Data visualisation using Kibana dashboards for threat monitoring
- Analytical thinking in identifying anomalies and attacker trends

### Tools Used

- SIEM: ELK Stack (Elasticsearch, Logstash, Kibana)
- Analysis: Kibana dashboards, log filtering, event correlation
- Networking: ICS honeypot dataset (Conpot)
- Concepts: MITRE ATT&CK for ICS, threat detection, log analysis

## Steps
Screenshots coming soon will add 

Ref 1: Events Over Time Dashboard
Shows a large spike in SNMP traffic indicating a reconnaissance campaign

Ref 2: Top Source IPs
Displays most active attacker IPs from global locations

Ref 3: Destination Ports
Highlights targeted ICS ports such as 161 (SNMP) and 2404 (IEC-104)

### Project Steps

1. Data Ingestion
- Imported ICS honeypot dataset (~97,000 records, 93 fields) into Elasticsearch
- Parsed and structured logs for analysis using Logstash

2. Data Analysis
- Identified top targeted protocols:
- SNMP (37,146 events)
- Kamstrup_protocol (19,156)
- Guardian_ast (15,604)
- IEC-104 (13,813)
- Detected that SNMP traffic dominated, indicating large-scale reconnaissance

3. Visualisation (Kibana Dashboards)
- Built 10+ dashboards to analyse:
- Events over time (spike detection)
- Top source IPs (attacker identification)
- Destination ports (attack surface analysis)
- Geographic attack distribution
- IP reputation (known attackers vs scanners)

4. Threat Detection & Findings
- Identified a major SNMP spike, indicating automated scanning activity
- Observed repeated connections from known attacker and mass scanning IPs
- Confirmed attacker focus on device enumeration and reconnaissance
- Detected probing behaviour on ICS-specific ports (161, 2404, 50100)

5. MITRE ATT&CK Mapping
- Mapped observed behaviour to:
- Discovery (T1046 – Network Service Scanning)
- Collection (T0888, T0842)
- Data from Information Repositories (T1213)
- Determined that activity remained in early attack stages (reconnaissance)
