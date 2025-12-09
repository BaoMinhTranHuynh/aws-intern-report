---
title: "Translated Blogs"

weight: 3
chapter: false
pre: " <b> 3. </b> "
---

{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}

This section will list and introduce the blogs you have translated.

### Blog 1 - Measuring Developer Productivity with Amazon Q Developer and Jellyfish

This blog guides you on how to integrate Amazon Q Developer with Jellyfish to effectively measure the impact of generative AI on developer productivity. Modern development teams are pressured to deliver high-quality code faster, often hindered by "toil"—manual, repetitive, and low-value work. Amazon Q Developer helps reduce this toil, but measuring its real impact requires looking at the entire Software Development Lifecycle (SDLC). The integration combines Amazon Q Developer's AI usage data with other technical metrics using Jellyfish, an Engineering Management solution. This provides engineering leaders with a holistic view to measure impact (e.g., track reduction in time from first commit to Pull Request) and monitor adoption across the team, enabling data-driven decisions on AI investment.

### Blog 2 - Now Available – AWS Systems Manager for SAP Configuration Management: Automated Validation of SAP HANA Best Practices
 
This blog announces the launch of AWS Systems Manager for SAP Configuration Management, a new feature that enables automated validation of SAP HANA database configurations against AWS-recommended best practices (based on the SAP Lens of the AWS Well-Architected Framework). This feature helps SAP administrators detect potential configuration drifts and ensure optimal performance, security, and reliability for SAP HANA workloads running on AWS. The Configuration Checks focus on key areas like EC2 Instance Type Selection, EBS Storage Configuration, and Pacemaker HA Setup. The feature supports both manual and scheduled automation checks via API, with results providing detailed status (OKAY, ERROR, WARNING, INFO) and remediation guidance.

### Blog 3 - Generative AI Architectural Patterns – Part 2 (Non-Real-Time)


This part of the series introduces architectural patterns for Generative AI workflows that do not require immediate response, ideal for time-consuming tasks or scheduled, large-scale data processing. The two main approaches covered are Buffered Asynchronous Processing and Non-Interactive Batch Processing. Key patterns include: Buffered Asynchronous Request Response (using API Gateway/WebSocket API with Amazon SQS and DynamoDB for long-running tasks), Multimodal Parallel Fan-Out (using Amazon SNS/EventBridge to distribute tasks to multiple LLMs/agents), and Non-Interactive Batch Processing (using AWS Step Functions or AWS Glue for scheduled data processing and inferencing). These patterns enable building scalable, reliable, and cost-effective cloud-native applications.