
# Python Automation Scripts:
This repository contains a collection of Python automation scripts I designed to simplify common DevOps and cloud operations tasks. 
These scripts help reduce manual effort, improve reliability, and provide quick operational insights.

Features:
- Clean Up Snapshots – Automatically identify and remove unused snapshots to save storage costs.
- EC2 Status Check – Retrieve the running/stopped status of your EC2 instances.
- EKS Status Check – Verify the health and availability of your Amazon EKS clusters.
- Monitor Websites – Continuously monitor website availability and response status.
- Restore Volume – Restore an EBS volume from a snapshot when needed.
- Backup Volume – Create backups of EBS volumes for disaster recovery.
- List Files in Folder – Script to quickly list and manage files in a given directory.
- Cloud Cost Optimization - We will create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

Python Boto3 module using Lambda function delete stale EBS snapshot that are not attached to any active instances and have been in stale state for a certain period (e.g., 7 days)

lambda Function are event driven in nature and we Intergated Cloudwatch with lambda funtion using EventBridge to schedule and trigger function to run at a particular time (e.g,every 7days at 6am) to check and delete stale EBS snapshots in AWS.

Requirements:
```
- Python 3.8+
- AWS CLI configured with valid credentials (for AWS-related scripts)
- Required Python packages.
```

Usage:
Clone this repository and run the scripts individually based on your task:
```
git clone https://github.com/tanya-domi/Python-Automation.git
cd Python-Automation/
```
feel free to use and adapt to your personal need.

