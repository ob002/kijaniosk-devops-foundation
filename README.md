# KijaniKiosk DevOps Foundation

Welcome to the **KijaniKiosk DevOps Starter Kit**. This repository serves as the technical blueprint and engineering foundation for the early architecture of the KijaniKiosk online platform. 

It documents the essential infrastructure thinking, security principles, and collaboration workflows required before the system scales to real customers.

## 📁 Project Structure

The core documentation is located in the `starter-kit/` directory:

- `delivery-notes.md` - DevOps mindset: Flow, Feedback, and Learning
- `cloud-model.md` - Cloud reasoning: Justification for IaaS
- `region-az.md` - Reliability: Region selection and Multi-AZ design
- `least-privilege.md` - Security: IAM role and policy design
- `network-topology.png` - Network: Public/Private subnet diagram

## 🏗️ Architecture Highlights

* **Cloud Service Model:** We selected **IaaS** to maintain granular control over network segmentation, custom IAM policies, and horizontal scaling.
* **Reliability:** The system is designed across multiple Availability Zones (Multi-AZ) within a primary region (e.g., `us-east-1`) to ensure high availability.
* **Security (Least Privilege):** Application components are assigned strict IAM roles. For example, the image-serving component only has `s3:GetObject` permissions for a specific bucket.
* **Network Segmentation:** The architecture utilizes a Virtual Private Cloud (VPC) with distinct Public and Private subnets to isolate public-facing load balancers from internal servers.

##  Git Collaboration Workflow

This project follows a standard **GitHub Flow** branching strategy:

1. **`main`**: The production-ready branch.
2. **`develop`**: The integration branch where features are merged.
3. **`feature/*`**: Short-lived branches for specific tasks (e.g., `feature/starter-kit-files`).

All changes are submitted via **Pull Requests (PRs)** from a feature branch into `develop`, ensuring code review and continuous feedback.

##  DevOps Principles in Action

* **Flow:** Small, frequent commits and automated PR checks reduce bottlenecks.
* **Feedback:** Peer reviews via Pull Requests provide immediate feedback on architectural decisions.
* **Learning:** This repository acts as a living document, ensuring future engineers understand the "why" behind our infrastructure choices.
