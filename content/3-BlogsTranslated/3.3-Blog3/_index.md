---
title: "Blog 3"

weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy verbatim** for your report, including this warning.
{{% /notice %}}

This section will list and introduce the blogs that I have translated.

### Blog 3 - Generative AI Architectural Patterns – Part 2 (Non-Real-Time).
Part 2 of this series introduces two complementary architectural patterns for Generative AI workflows that do not require immediate response, ideal for time-consuming tasks or scheduled, large-scale data processing: Buffered Asynchronous Processing and Non-Interactive Batch Processing.

Pattern 4: Buffered Asynchronous Request Response
This pattern uses event-driven architectures to handle long-running requests (e.g., video generation, scientific analysis) to increase scalability and reliability.

REST API with Message Queuing: The frontend sends a request via API Gateway which is buffered into Amazon SQS. Middleware (Lambda/EC2/Fargate) processes the messages in batches, calls the LLM, saves the result to DynamoDB, and the frontend polls for the response.

WebSocket API with Message Queuing: A variation using the API Gateway WebSocket API. Once processed, the middleware actively sends the result back to the client immediately (no polling required) through the WebSocket connection.

Pattern 5: Multimodal Parallel Fan-Out
This pattern is applied when interacting with multiple LLMs, data sources, or agents. It uses a fan-out mechanism via Amazon EventBridge or Amazon SNS to distribute specific messages to multiple targets in parallel, breaking down and executing complex sub-tasks simultaneously to minimize overall generation time.

Pattern 6: Non-Interactive Batch Processing
Ideal for efficiently processing large datasets on a schedule or event-driven basis (e.g., batch image optimization, periodic report generation). This pattern uses services like AWS Step Functions or AWS Glue to build serverless data processing and inferencing pipelines, optimizing resource usage and increasing throughput.
[Read full blogs on Google Docs](https://docs.google.com/document/d/1yOGQn6Z0tj7i5G_-li2U0zU6pFMy3pI_IvAF1khlEfY/edit?usp=sharing)