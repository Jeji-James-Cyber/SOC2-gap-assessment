# Scope Definition: Brighter (Fictional) SOC 2 Readiness Assessment

> This is a fictional readiness assessment for portfolio purposes. It is not a SOC 2 audit or report.

## 1. Assessment type and period
- Report type targeted: SOC 2 Type II (readiness assessment only)
- Assessment as-of date: 1 November 2026
- Remediation window: 1 November 2026 to 30 April 2027
- Planned observation period: 1 May 2027 to 31 October 2027

## 2. Trust Services Categories
| Category | In scope | Notes |
|---|---|---|
| Security (CC1 to CC9) | Yes | Mandatory |
| Availability (A1) | Yes | Customers depend on platform uptime |
| Confidentiality (C1) | Yes | Confidential financial data and bank-connection tokens |
| Processing Integrity (PI1) | Yes | Invoice, expense and bank-feed data must be processed completely and accurately |
| Privacy (P1 to P8) | No | Excluded for manageability. Data protection obligations (e.g. GDPR) still apply separately |

## 3. System boundary
### In scope
- Brighter production web application and public API
- Production AWS environment (EC2, RDS PostgreSQL, S3, CloudWatch)
- Okta, GitHub and GitHub Actions, Jira, Slack, Google Workspace
- Employees and contractors with access to production or customer data
- Customer business data, user account data, bank-connection tokens
- Processes: onboarding/offboarding, access management, change management, incident response, vendor management, backup and recovery
- Invoice and expense processing, bank-feed imports

### Out of scope
- Public marketing website
- Internal corporate tools with no access to customer data or production
- Beta or experimental features not available to customers
- Internal HR system

## 4. Third parties (carve-out method)
| Vendor | Role | Treatment |
|---|---|---|
| AWS | Hosting | Carve-out |
| Okta | Identity / SSO | Carve-out |
| GitHub | Source code and CI/CD | Carve-out |
| Payment processor | Card payments | Carve-out (no card data stored by Brighter) |

## 5. Assumptions and limitations
- Brighter is fictional; all practices and evidence are invented for this exercise
- Criteria wording will be verified against the official AICPA Trust Services Criteria
- This is not an attestation and does not replace an audit by a licensed CPA firm
