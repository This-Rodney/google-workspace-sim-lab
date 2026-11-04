# Google Workspace IAM & SAML SSO Lab

## Objective
Built a functional Google Workspace environment from scratch to demonstrate hands-on Identity & Access Management (IAM) skills. The project focused on domain verification, directory structure design, user lifecycle management, and configuring Google Workspace as an Identity Provider (IdP) for SAML 2.0 Single Sign-On (SSO).

## Technologies Used
- **Identity Provider:** Google Workspace (Business Starter Trial)
- **Domain & DNS:** IONOS
- **Protocol:** SAML 2.0
- **Service Provider (Target):** Slack (Business trial)

## Architecture Overview
1. **DNS Layer:** IONOS manages the domain records. TXT records were configured for ownership verification, and MX records were updated to route email to Google.
2. **Identity Layer (IdP):** Google Workspace Admin Console manages Organizational Units (OUs), Groups, Users, and SAML applications.
3. **Application Layer (SP):** Slack was configured as the target SaaS application for SSO integration.

## Implementation Steps

### 1. Domain Setup & Verification
- Registered a custom domain and accessed the IONOS DNS management console.
- Added a DNS TXT record provided by Google to verify domain ownership.
- Removed default registrar MX records and configured Google's single MX record (`smtp.google.com`) to activate Gmail for the domain.

### 2. Directory Structure & User Lifecycle (RBAC)
- Designed an Organizational Unit (OU) hierarchy to represent company departments (e.g., `Engineering`, `Marketing`, `Finance`, `HR`).
- Created Groups for email distribution and access control.
- Provisioned test users and assigned them to specific OUs to enforce policy inheritance.
- Tested user login workflows via Gmail to verify successful authentication and directory assignment.

### 3. SAML 2.0 SSO Configuration (IdP Side)
- Navigated to the Google Admin Console and added a custom SAML application for Slack.
- Downloaded the Google IdP metadata (SSO URL, Entity ID, and Certificate).
- Configured attribute mapping to pass user data (Primary Email, First Name, Last Name) to the Service Provider.
- Configured OU-based app access, ensuring only specific departments were authorized to use the application.

## Limitations & Real-World Constraints
- **Service Provider Paywall:** While the Google IdP configuration was completed successfully, full end-to-end SSO testing required the Slack Business+ tier, which requires a paid subscription. The SP-side configuration was documented based on technical documentation, but not fully executed in the lab environment.
- **Trial Lifecycle:** The environment was built using a 14-day Google Workspace trial and was decommissioned (data exported and subscription cancelled) after documentation was complete.

## 📸 Screenshots
<img width="1170" height="448" alt="Screenshot 2026-09-28 at 10 10 51 PM" src="https://github.com/user-attachments/assets/e48375df-fbf6-4ae7-b1a1-651f1c9cbaac" />
<img width="981" height="747" alt="Screenshot 2026-09-28 at 10 19 24 PM" src="https://github.com/user-attachments/assets/03eddf7c-0423-4dce-813e-1db7f8911ffc" />
<img width="996" height="678" alt="Screenshot 2026-11-03 at 6 03 35 PM" src="https://github.com/user-attachments/assets/27914daa-2ba4-446b-9cfd-d2791b03e7f9" />
<img width="756" height="584" alt="Screenshot 2026-09-29 at 12 55 42 PM" src="https://github.com/user-attachments/assets/43e555aa-51a5-4d28-b3c6-c2fa334032cf" />
<img width="682" height="556" alt="Screenshot 2026-09-29 at 1 21 56 PM" src="https://github.com/user-attachments/assets/03d9de7f-988e-4a44-83a9-759c9e77444a" />
<img width="851" height="665" alt="Screenshot 2026-09-29 at 3 04 11 PM" src="https://github.com/user-attachments/assets/665f36db-c813-47eb-9e6f-3befacc6c354" />
<img width="1201" height="737" alt="Screenshot 2026-09-29 at 3 12 20 PM" src="https://github.com/user-attachments/assets/c64c7eb3-6529-48bb-885e-690b136d6d7e" />
<img width="1118" height="564" alt="Screenshot 2026-09-29 at 8 17 00 PM" src="https://github.com/user-attachments/assets/ed7c8ea3-1abd-4fcc-913b-1736b1a256a6" />

