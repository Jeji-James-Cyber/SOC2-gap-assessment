# Current-State Security Practices: Brighter (Fictional)

> Fictional readiness assessment. All facts below are invented for this exercise. They represent what an analyst might learn from interviews, document review and system walkthroughs as of 1 November 2026.

## 1. Governance, policies and culture
- CS-01: An information security policy and an acceptable use policy exist. Both were written about two years ago and have not been reviewed since.
- CS-02: A code of conduct exists. New hires acknowledge it during onboarding, but there is no yearly re-acknowledgement.
- CS-03: Security reports to the CTO. There is no independent security committee, and the board receives security updates only when there is a major customer or investor question.
- CS-04: Policies are stored on the company wiki, but there is no single owner for keeping them current, and no formal policy approval step.
- CS-05: Customers can read a public security page and a status page. Customer contracts include security and uptime commitments.
- CS-06: There is a security contact email address, but no published vulnerability disclosure policy.

## 2. People and training
- CS-07: Background checks are done for all new hires, applied consistently since last year.
- CS-08: Security awareness training is given once during onboarding. There is no annual refresher, and about 70% of current staff have ever completed it.
- CS-09: Job descriptions for engineering and security roles include security responsibilities. Other roles do not.
- CS-10: Offboarding starts with an email from HR to IT. Access removal takes about 3 days on average, and there is no checklist.

## 3. Risk management
- CS-11: Risks are discussed informally in engineering leadership meetings. There is no risk register and no scheduled risk assessment.
- CS-12: Fraud risk (for example, misuse of customer financial data by insiders) has not been formally considered.
- CS-13: One external penetration test was done 14 months ago. Of 11 findings, 7 were fixed and 4 remain open without a documented decision.
- CS-14: Business-impact analysis and continuity planning are limited to a short business continuity document that is out of date.

## 4. Monitoring of controls
- CS-15: There is no internal audit function, and no regular self-assessment of whether controls are working.
- CS-16: Security issues found in practice are raised in Slack. There is no formal log of control deficiencies, and nothing reaches senior management in a regular report.

## 5. Identity and access
- CS-17: Okta provides single sign-on for most business applications. 77 of 85 workforce accounts (about 91%) have MFA enrolled. The 8 without MFA are legacy service accounts and some contractor accounts.
- CS-18: AWS console access goes through Okta, but 4 engineers still have long-lived IAM user keys that were created before SSO was introduced.
- CS-19: Access requests are made through Slack messages or Jira tickets, inconsistently. Approval is by the requester's manager, and is not always recorded.
- CS-20: Access reviews are ad hoc. The last review of AWS access was about 9 months ago, and GitHub access has never been formally reviewed.
- CS-21: Production database access is limited to the DevOps team and 3 senior engineers. There is no segregation between people who can deploy code and people who can change production data.
- CS-22: The Dublin office uses badge access and a paper visitor log. Most staff work in a hybrid pattern.

## 6. Endpoints and malware
- CS-23: Company laptops are used by all staff. A mobile device management tool covers 51 of 85 laptops (60%). Disk encryption status is unknown on the others.
- CS-24: Endpoint antivirus is installed centrally on managed laptops only.
- CS-25: Removable storage is not restricted. There is no data loss prevention tooling.

## 7. Network and perimeter
- CS-26: The AWS production environment sits in a private network with a load balancer as the public entry point. Security groups are managed by the DevOps team.
- CS-27: Security group rules have never been formally reviewed. Two rules allowing wide administrative access from the internet were found during an informal check last quarter, and are still open.

## 8. Vulnerability management and monitoring
- CS-28: Vulnerability scans run manually, roughly every 3 months. Critical vulnerabilities take about 21 days on average to patch, and there is no target timeframe.
- CS-29: CloudWatch collects logs and metrics with 30-day retention. There is no central security log monitoring or alerting. Alerts exist only for outages and capacity.
- CS-30: Dependency scanning is enabled on GitHub for the main application repositories, but alerts are reviewed only occasionally.

## 9. Incident response
- CS-31: A draft incident response plan exists but has never been tested. Incidents are coordinated in a Slack channel.
- CS-32: There were 3 incidents in the last 12 months. Only 1 has a written post-incident review.
- CS-33: There is no defined process for notifying customers about a security incident, apart from general contract wording.

## 10. Change management
- CS-34: Application code changes require a pull request with one approval on the main repositories. Repository administrators can bypass this, and hotfixes regularly do.
- CS-35: Automated tests run in GitHub Actions on each pull request. Deployments to production are automatic after merge.
- CS-36: Infrastructure changes in AWS are made through the console and scripts. There are no tickets or approvals for them.

## 11. Vendors
- CS-37: There are about 14 vendors with access to company or customer data. 3 of them (about 21%) have had a documented security review.
- CS-38: Vendor contracts are signed by Finance after business approval. Security is not consistently consulted.
- CS-39: Vendor assurance reports and certifications are not collected or tracked.

## 12. Availability and recovery
- CS-40: Customer contracts promise 99.9% availability. Measured availability over the last 12 months was 99.87%.
- CS-41: CloudWatch alarms track CPU and database storage. Capacity is reviewed informally during quarterly planning.
- CS-42: RDS takes automatic daily backups. A full restore has never been tested.
- CS-43: A disaster recovery plan exists as a one-page document, which has never been tested.

## 13. Confidentiality and data handling
- CS-44: The database and document storage are encrypted at rest. There is no formal key management or rotation process.
- CS-45: Bank-connection tokens are stored in the production database. Access to them is limited to the application, but token access is not logged separately.
- CS-46: There is no data classification scheme or data retention policy. Customer data is deleted manually on request, with no standard process or timeline.
- CS-47: Retired laptops are wiped by IT, but disposal is not recorded.

## 14. Processing integrity
- CS-48: Invoice and tax calculation logic has automated unit tests that run in the pipeline.
- CS-49: Bank-feed imports have retry logic, but there is no automatic check that imported totals match the source.
- CS-50: Failed imports go to an error queue that support staff check when they have time. There is no defined timeframe for resolving errors.
- CS-51: There is no written specification of the data fields the system processes. Product requirements live in Jira tickets.
- CS-52: Customer-facing reports are not independently checked before release.
