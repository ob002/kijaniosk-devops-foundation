# Region and Availability Zone Architecture

## Region Selection: us-east-1 (N. Virginia)
Selected for low latency to our primary user base and compliance with data residency requirements.

## Multi-Availability Zone (Multi-AZ) Reliability
We will deploy our application across at least two Availability Zones (e.g., us-east-1a and us-east-1b). If a power outage or network failure takes down one AZ, traffic will automatically route to the other, ensuring high availability.
