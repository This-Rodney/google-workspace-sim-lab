# Google Workspace IAM & SAML SSO Lab

## 🎯 Objective
Built a functional Google Workspace environment from scratch to demonstrate hands-on Identity & Access Management (IAM) skills. The project focused on domain verification, directory structure design, user lifecycle management, and configuring Google Workspace as an Identity Provider (IdP) for SAML 2.0 Single Sign-On (SSO).

## 🧰 Technologies Used
- **Identity Provider:** Google Workspace (Business Starter Trial)
- **Domain & DNS:** IONOS
- **Protocol:** SAML 2.0
- **Service Provider (Target):** Slack (Business+ trial)

## 🏗️ Architecture Overview
1. **DNS Layer:** IONOS manages the domain records. TXT records were configured for ownership verification, and MX records were updated to route email to Google.
2. **Identity Layer (IdP):** Google Workspace Admin Console manages Organizational Units (OUs), Groups, Users, and SAML applications.
3. **Application Layer (SP):** Slack was configured as the target SaaS application for SSO integration.

## 🛠️ Implementation Steps

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

## ⚠️ Limitations & Real-World Constraints
- **Service Provider Paywall:** While the Google IdP configuration was completed successfully, full end-to-end SSO testing required the Slack Business+ tier, which requires a paid subscription. The SP-side configuration was documented based on technical documentation, but not fully executed in the lab environment.
- **Trial Lifecycle:** The environment was built using a 14-day Google Workspace trial and was decommissioned (data exported and subscription cancelled) after documentation was complete.

## 🧠 Skills Demonstrated
- **Identity & Access Management (IAM):** SAML 2.0 SSO, Identity Provider (IdP) configuration, attribute mapping.
- **Directory Services:** Organizational Unit (OU) design, Role-Based Access Control (RBAC), user/group provisioning.
- **Networking:** DNS management (TXT and MX records), domain verification.
- **Administration:** Google Workspace Admin Console, IONOS DNS panel.

## 📸 Screenshots
*(Create a `/screenshots` folder in this repo and add your images here. Replace the text below with your actual image links)*

- `![Domain Verification](screenshots/domain-verification.png)`
- `![OU Structure](screenshots/ou-structure.png)`
- `![SAML App Config](screenshots/saml-config.png)`
- `![Attribute Mapping](screenshots/attribute-mapping.png)`