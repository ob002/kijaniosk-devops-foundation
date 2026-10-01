# Cloud Service Model Justification

## Decision: Infrastructure as a Service (IaaS)

For the early architecture of KijaniKiosk, we recommend IaaS (e.g., AWS EC2, VPC).

### Why IaaS?
1. **Control over Network Segmentation:** IaaS gives us full control over Virtual Private Clouds (VPCs), routing tables, and security groups.
2. **Custom IAM Policies:** IaaS allows granular control over IAM roles and policies to implement "Least Privilege".
3. **Scalability:** IaaS allows us to scale the infrastructure horizontally as the user base grows.
