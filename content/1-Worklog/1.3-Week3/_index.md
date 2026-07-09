---
title: "Week 3 Worklog"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---


### Week 3 Objectives:

* Build a **Hybrid DNS** system integrating On-premises DNS and **Amazon Route 53**.
* Deploy infrastructure using **AWS CloudFormation** following the Infrastructure as Code (IaC) approach.
* Configure **Inbound/Outbound Endpoints** and **Resolver Rules** for Route 53 Resolver.
* Verify bidirectional domain name resolution between On-premises and AWS.

---

### Tasks to be carried out this week:

| No. | Day | Date | Task | Reference Material |
| --- | --- | ---- | ---- | ------------------ |
| 1 | Monday | 04/05/2026 | Research an overview of **Amazon Route 53**: DNS Resolver, Private Hosted Zones, Public Hosted Zones. Learn the concept of **Hybrid DNS**  Ewhy it's necessary to integrate On-premises DNS with Route 53 in a Hybrid Cloud environment. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 2 | Tuesday | 05/05/2026 | Deploy the Lab infrastructure using **AWS CloudFormation**: create stacks, define YAML/JSON templates, and understand the Resources/Outputs/Parameters structure. Configure VPCs, Subnets, and Security Groups via CloudFormation. | [docs.aws.amazon.com/cloudformation](https://docs.aws.amazon.com/cloudformation/) |
| 3 | Wednesday | 06/05/2026 | Create and configure a **Route 53 Inbound Endpoint**: allow DNS queries from On-premises to resolve in AWS. Create a **Route 53 Outbound Endpoint**: allow DNS queries from AWS to be forwarded to On-premises DNS servers. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 4 | Thursday | 07/05/2026 | Set up **Resolver Rules** (Forward Rules) to route DNS queries based on specific domains. Associate Resolver Rules with their respective VPCs. Test bidirectional DNS configuration using **nslookup** and **ping** commands from an EC2 instance. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 5 | Friday | 08/05/2026 | Comprehensively test the Hybrid DNS system: verify that domain name resolution works correctly in both directions. Clean up resources after the Lab to avoid incurring costs. Write the weekly summary worklog and note down lessons learned. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |

---

### Week 3 Achievements:

* Clearly understood the **Hybrid DNS** architecture and the reasons for integrating On-premises DNS with Amazon Route 53.

* Successfully deployed the Lab infrastructure using **AWS CloudFormation**, mastering basic IaC workflows:
  * Wrote CloudFormation templates defining VPCs, Subnets, and Security Groups.
  * Created and managed CloudFormation Stacks.

* Successfully configured **Route 53 Resolver**:
  * Inbound Endpoint: received DNS queries from On-premises into AWS.
  * Outbound Endpoint: forwarded DNS queries from AWS to On-premises.
  * Resolver Rules: routed DNS based on specific domains.

* Successfully verified bidirectional domain name resolution using **nslookup** and **ping**.

* Cleaned up resources after the Lab, leaving no unexpected costs.

---

### Plan for next week:

* Optimize **VPC Peering** (Route Tables, Cross-Peer DNS) and deploy **AWS Transit Gateway** for 4 VPCs.
* Practice **Infrastructure as Code** using CloudFormation + Application Composer.
* Use **Reachability Analyzer** for network troubleshooting and set up a **Bastion Host**.