 CloudLaunch –  Assessment (Semester 3 – Month 1)
 Overview

CloudLaunch is a lightweight project that demonstrates core AWS services for hosting a static site, storing private files, and designing a secure VPC environment.

This project covers:

Task 1: Hosting a static website on S3 with IAM access controls.

Task 2: Designing a secure VPC layout with subnets, routing, and security groups.

📝 Task 1 – Static Website Hosting & IAM User Setup
🔹 S3 Buckets

cloudlaunch-site-bucket – Hosts static website, public read-only access.

cloudlaunch-private-bucket – Private storage with restricted access (Get/Put only).

cloudlaunch-visible-only-bucket – Visible in list, contents not accessible.

🔹 IAM User – cloudlaunch-user

Permissions include:

ListBucket on all three buckets.

GetObject on site bucket.

GetObject + PutObject on private bucket.

No delete permissions.

No access to contents of visible-only bucket.

🔹 User Credentials

For instructor verification:

IAM User: cloudlaunch-user

Password: Ebirebhisi-moren

Console URL -https://us-east-1.console.aws.amazon.com/console/home?region=us-east-1#
Account ID-676206914615

⚠️ Password change is enforced on first login.

🔹 Links

S3 Website Endpoint: http://cloudlaunch-site-bucket-moren.s3-website-us-east-1.amazonaws.com

📸 Screenshots evidence:  
All proof screenshots are included in [screenshots.zip](./screenshots.zip).  
(Download and unzip to view.)

S3 buckets list

Website working in browser

Private bucket upload success + access denied on delete

Visible-only bucket → Access denied when opening object

Error when checking bucket versioning (proves limited permissions)

📝 Task 2 – VPC Design
🔹 VPC Setup

cloudlaunch-vpc – CIDR block: 10.0.0.0/16

🔹 Subnets

cloudlaunch-public-subnet → 10.0.1.0/24

cloudlaunch-app-subnet → 10.0.2.0/24

cloudlaunch-db-subnet → 10.0.3.0/28

🔹 Routing

Public Route Table (cloudlaunch-public-rt): Internet access via IGW.

App & DB Route Tables: No 0.0.0.0/0 route → private only.

🔹 Security Groups

cloudlaunch-app-sg: Allows HTTP (80) inside VPC.

cloudlaunch-db-sg: Allows MySQL (3306) only from app subnet.

🔹 Screenshots Proof

VPC list with cloudlaunch-vpc

Subnets list with 3 subnets

Route tables with associations

Security groups showing inbound rules

🔒 IAM Policy JSON

The IAM policy attached to cloudlaunch-user is included in this repo as policy.json
.

📂 Repository Contents

README.md – Project documentation

policy.json – IAM policy file

screenshots/ – Folder containing all proof screenshots

✅ Evaluation Criteria Addressed

Clear setup of static site hosting.

Strict IAM access controls enforced.

Accurate and logical VPC layout.

Screenshots included for verification.
