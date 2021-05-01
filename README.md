# stayonyourlawn
Security Solutions

Minimum Viable Product Client: Chewy Brands
Team - Stay On Your Lawn Security
Authors - Emilio Muniz, Ethan Denny, Tom Esch
Last Revised - 4/30/2021

Goal: Technical demonstration protecting PII and PCI data in AWS Cloud in accordance with GPRP compliance.
Overview: How our solution prevents exfiltration of PII and PCI data against *** using:

Simulated Attack:
Junior IT “godlrush” fallen on hard times makes a poor decision to steal PII and PCI to pay off gambling debts. As a limited privileged user, “godlrush” elevated their identity to administrator seeking access to sensitive customer data. This was done using python to try and automate exfiltration of PII and PCI data.
Kill Chain - Privilege Escalation
TacticsTechniquesProcedures - Exfiltration: TA0010 Automated Exfiltration: T1020 Traffic Duplication: .001 

SIEM/log aggregation system
CloudWatch - for collecting and monitoring operational data in the form of logs, metrics, and events, and visualize it using automated dashboards to get a unified view of our AWS resources, applications, and services.
Will be configured to ingest event logs in real time from key assets.

Cloud Monitoring
CloudTrail - will be used to generate and export event logs.
VPC Flow Logs - to capture information about the IP traffic going to and from network interfaces in our VPC. Flow log data can be published to Amazon CloudWatch Logs or Amazon S3.
AWS Lambda Function - invoke Lambda functions using the Lambda API, or Lambda to run functions in response to events from other AWS services.

DLP controls
TrendMicro will be implemented as an endpoint DLP solution and configured to detect and prevent the exfiltration of PII and PCI data classes from an instance or instances
AWS Macie appears to support recognition of sensitive data at rest.

Infrastructure:
AWS Account to host all AWS resources
User Management:
Root user must have MFA
Admin IAMs for all team members
Demo IAM accounts and roles as would be used by employees
AWS Services to be tied together:
CloudWatch
At least monitor event logs in real time from Linux Server
Cloudtrail
EC2
CIS compliant Linux Data Server
On a private subnet of a VPC
Accessible by VPN
Either OpenVPN installed on the instance or AWS VPN if it’s not too terrible
AWS Security Hub/Security Pillar coupled with AWS Macie to be utilized to encrypt PII and PCI data at rest and in transit.
AWS Lambda
A function written in Python3 to trigger a relevant response to a detected threat
VPC
With a private subnet for the EC2 Linux Server
Flow Logs for monitoring traffic in and out of the VPC
S3
For log storage
GuardDuty
Non-AWS:
VPN access between EC2 linux data server and and endpoint
An endpoint with Trend Micro
Running on a lab VC
Deliverables:
Network Security Assessment
PD01: Risk Assessment Worksheet
PD02: Security Assessment Report (SAR)
PD03: Data Security Policy
PD04: Cloud Security Policy
PD05: Security Architecture Narrative
Topology
Descriptions of how we used:
AWS AIM
AWS CloudTrail
Amazon GuardDuty
Explain how CIS benchmarks were applied to your cloud instance(s). Validate CIS compliance using AWS Security Hub.
Explain how Full Drive Encryption (FDE) was used to secure hard drives on your systems.
Explain how Public Key Infrastructure (PKI) was used in your cloud environment.
Does not include physical security
