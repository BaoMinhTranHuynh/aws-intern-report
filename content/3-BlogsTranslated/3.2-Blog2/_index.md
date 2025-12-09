---
title: "Blog 2"

weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy verbatim** for your report, including this warning.
{{% /notice %}}

This section will list and introduce the blog that I have translated.

### Blog 2 - Now Available – AWS Systems Manager for SAP Configuration Management: Automated Validation of SAP HANA Best Practices.
This blog announces the launch of AWS Systems Manager for SAP Configuration Management, a new feature that enables automated validation of SAP HANA database configurations against AWS-recommended best practices (based on the SAP Lens of the AWS Well-Architected Framework). This feature helps SAP administrators detect potential configuration drifts and ensure optimal performance, security, and reliability for SAP HANA workloads running on AWS.

The initial Configuration Checks focus on three main categories:

SAP EC2 Instance Type Selection: Validating if the EC2 instance type is SAP-certified.

SAP HANA EBS Storage Configuration: Checking Amazon EBS storage and file system setups.

SAP HANA Pacemaker Configuration: Reviewing Pacemaker cluster configuration for High Availability (HA) setups.

Each check returns a detailed status (OKAY, ERROR, WARNING, INFO, or UNKNOWN) and provides remediation guidance with links to relevant technical documentation. The feature supports manual checks via the AWS Console or scheduled automation via a simple API command, allowing for historical tracking of configuration changes over 30 days. The service is priced on a pay-per-use model ($0.25 USD per configuration check run per application).
[Read full blogs on Google Docs](https://docs.google.com/document/d/1OfummNzAJUQRtHSIqkvKrEJZxHHWL2dXaQxlFypCqr0/edit?usp=sharing)