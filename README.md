# Project #28: AWS Serverless Message Queue Integration (SQS + Lambda)

## 🏢 Business Scenario & Customer Demand
An e-commerce store was facing website latency issues during peak traffic hours. When multiple users placed orders at the same time, synchronous backend processing (invoicing, inventory updates, emails) bottlenecked the server, causing performance drops. 

**The Solution:** Deployed a highly scalable, decoupled, and asynchronous order processing backend using a serverless message queue to ensure the frontend web application remains fast and responsive.

## 🛠️ Tech Stack & Services Used
* **Amazon SQS (Simple Queue Service):** Standard Queue used as a reliable buffer to hold incoming order payloads safely.
* **AWS Lambda (Python 3.x):** Serverless compute engine that processes messages from the queue asynchronously.
* **AWS IAM:** Custom execution policies (`AWSLambdaSQSQueueExecutionRole`) to safely allow Lambda to poll records from SQS.
* **Amazon CloudWatch:** Used for real-time monitoring and log verification.

## 📊 Architecture Flow
[Client Order] ➔ [Amazon SQS Queue] ➔ [AWS Lambda (Python)] ➔ [CloudWatch Logs Output]

## 🧪 Verification Results
Tested successfully by sending an order payload `{"order_id": 101, "item": "Gaming Laptop", "price": 1200}` through the SQS console. CloudWatch logs instantly verified that AWS Lambda successfully parsed and processed the batch request in real-time.
