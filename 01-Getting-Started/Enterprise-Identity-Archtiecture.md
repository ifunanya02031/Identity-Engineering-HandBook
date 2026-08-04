# Enterprise Identity Architecture

## The Problem

Enterprise organizations rarely rely on a single system to manage identities.

Employee information originates in one system, authentication occurs in another, identities may be stored in a directory service, and access is granted across dozens or even hundreds of applications.

Without a defined architecture, identity becomes fragmented, manual processes increase, and access quickly becomes difficult to manage.

Enterprise Identity Architecture defines how these systems work together.

---

## The Solution

Enterprise Identity Architecture is the framework that connects identity systems throughout an organization.

Each system has a specific responsibility.

Rather than replacing one another, these systems work together to manage identities securely from onboarding through offboarding.

---

## Core Components

### Human Resources (HR)

The HR system is typically the authoritative source for employee information.

Examples include:

- Workday
- SAP SuccessFactors
- Oracle HCM

Common responsibilities:

- Employee creation
- Department changes
- Manager changes
- Employment status
- Job title
- Employee termination

---

### Directory Services

Directory Services store enterprise identities and organizational information.

Examples include:

- Active Directory
- Microsoft Entra ID
- LDAP

Common responsibilities:

- User objects
- Groups
- Organizational Units (OUs)
- Identity attributes

---

### Identity Provider (IdP)

The Identity Provider authenticates users and provides identity services to enterprise applications.

Examples include:

- Okta
- Microsoft Entra ID
- Ping Identity

Common responsibilities:

- Authentication
- MFA
- SSO
- Federation
- Authentication Policies

---

### Enterprise Applications

Applications consume identities.

Examples include:

- Salesforce
- AWS
- Microsoft 365
- Slack
- Jira
- ServiceNow
- GitHub

Applications are responsible for authorizing access based on the information they receive from the Identity Provider.

---

### Identity Governance

Identity Governance oversees how access is requested, approved, reviewed, and maintained throughout the identity lifecycle.

Common responsibilities:

- Access Requests
- Manager Approvals
- Access Reviews
- Certifications
- Separation of Duties
- Compliance

---

## Enterprise Identity Flow

```text
                Human Resources
                  (Workday)
                      │
                      ▼
            Directory Services
          (AD / LDAP / Entra ID)
                      │
                      ▼
           Identity Provider (IdP)
                    (Okta)
                      │
      ┌───────────────┼────────────────┐
      ▼               ▼                ▼
 Salesforce          AWS          Microsoft 365
      ▼               ▼                ▼
   GitHub          ServiceNow        Slack
```

Each system performs a specific role within the enterprise identity ecosystem.

---

## Identity Flow

```text
Employee Hired
        │
        ▼
HR System Updated
        │
        ▼
Directory Updated
        │
        ▼
Identity Provider
        │
        ▼
Authentication
        │
        ▼
Federation
        │
        ▼
Authorization
        │
        ▼
Application Access (Final)
```

---

## Design Principles

A well-designed enterprise identity architecture should:

- Centralize authentication
- Automate identity lifecycle management
- Enforce least privilege
- Minimize manual administration
- Support Single Sign-On (SSO)
- Scale across enterprise applications
- Improve security and governance

---

## Key Takeaways

- Enterprise IAM is an ecosystem, not a single product.
- Each identity system has a specific responsibility.
- HR creates identity changes.
- Directory Services store enterprise identities.
- Identity Providers authenticate users.
- Applications authorize access.
- Governance oversees access throughout the identity lifecycle.

---

## Related Topics

- Identity Lifecycle
- Authentication
- Federation
- Provisioning
- Directory Services
- Identity Governance