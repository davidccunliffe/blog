---
title: "Detailed Cloud and DevOps Experience report, 2008-"
date: 2024-11-12T17:04:33-05:00
draft: false
---

This is a sampling of some of the projects I’ve completed in the past 10+ years.
Most of the following projects were done for large enterprises and Fortune 500 companies.

- Designed and built a multiple foundational builds within AWS and GCP. Utilizing various Infrastructure as Code tools, in AWS prior to Landing Zone and Control Tower. I utilized Cloudformation Stacksets to deploy resources using a account factory developed with AWS Service Catalog. Later on utilizing CDK tooling such as Landing Zone Accelerator to perform the automation at scale in a centralized pipeline. In GCP I've leveraged tools such as Terraform to build out custom modules along with Python to develop organizational project builds with Zero Trust access via Workload Identity pools and pipelines.

- Designed and coded automated pipeline with the use of Gitlab, Gitlab OIDC providers to execute in multiple accounts and regions based on the changes of simple yaml config values which executed the build of 50 EC2 servers and boot strap them for either Application or MSSQL database deployments. This allowed the organization to grow horizontally or vertically and gave the developers leverage to deploy into various environments such as Sandbox, Development, Staging, QA or Production.

- Build and designed a multi-region landing zone deployment in AWS which had centralized controls for SCP, Networking, File, Active Directory Services, SFTP serverless access and Global Load Balancer Endpoints. This allowed for the customer to centralize the control of the overall infrastructure while still using custom protection and load balancing services. Networking was broken out into two accounts one for main egress and ingress (Global Load Balancing Endpoints, Firewalls and Load Balancing along with DNS through route53) and Workloads Networking account which all were shared via AWS RAM. This allowed for protected services to be restricted to specific networking staff while allowing general network changes to happen in the network workload accounts by either networking teams or application teams. All traffic was logged either via the Transit Gateway ingress/egress points or through firewall services as packets have to pass through Gateway Load Balancing for any North, Sourth or East, West Traffic patterns. The design implimented also allowed for duel redundancy between regional peers via Transit Gateway and external DNS forwarding into AWS. All Networks were controlled through IPAM allocations and allowed for easy scaling and controls on VPC CIDR designs. Each account and organizational policy were developed around business standards and compliances for the organization.

- Built automation (in Python) to extract data from Excel spreadsheets and generate Terraform AWS Security Groups variables files that plugged into Terraform templates that could take an unknown # of elements. This code was developed for networking engineers to easily deploy centralized firewall rules in GCP and Multi-VPC deployments in AWS. Once more it allowed for Auditor's to quickly review the security groups and check the state of the environment through drift policies baked into the pipelines.

- Security audit of AWS environments, and analysis of pipeline-based deployment of IaC code with recommendations for automatic security scans using a policy-as-code tool (Bridgecrew’s Checkov).

- Deployed and updated multi-account foundational architectures using the AWS Landing Zone solution (prior to the availability of the Control Tower service).

- Deployed and updated multi-account foundational architectures using the AWS Control Tower service.

- Migration of a large-scale application to AWS, architected with a Disaster Recovery (DR) failover region. Application was a complex, multi-service architecture spread across over 20 EC2 servers running both Windows & Linux, multiple S3 buckets, an RDS Oracle database, an FSx share and other ancillary services.

  - Terraform codebase for production environment of over 3000 SLoC.
  - Over 200 TB of data was transferred and synchronized from on-prem.
  - Documented detailed DR failover runbook and successfully tested failover of the production environment in AWS from the primary region to the DR region.

- Participated and assisted in the delivery of a Python3 package that reads in a set of GCP labels (from a YAML file), compares it to the resources in a GCP Project(s) and updates the labels on those resources. This is valuable for labeling un-labeled resources in projects for the purposes of billing, auditing, reporting, etc.

- Built multiple custom GitHub Actions pipeline for validating, planning and applying Terraform IaC with a Pull Request-based authorization before the Apply phase. Using both public or private modules depending on the client's requirements. The pipeline built environments based on whether or not there were actual changes to code and/or variables.

- Coded system to deploy Active Directory and SQL Server cluster running in AWS on EC2 servers. This used a combination of Terraform, SSM documents (AWS Systems Manager), and PowerShell DSC to install and configure SQL Server and Group Policy imports from S3.