# 02 – Identity Fundamentals

Identity is the foundation of every IAM system.

Before discussing authentication protocols, provisioning standards, or governance frameworks, it is important to understand the core concepts that drive enterprise identity.

This section introduces the principles that appear throughout the remainder of this handbook. Rather than focusing on individual technologies, these topics explain how identity systems function together to manage users securely across the enterprise.

---

## Learning Objectives

After completing this section, you should be able to:

- Distinguish authentication from authorization.
- Differentiate identity provisioning from account provisioning.
- Explain the Joiner, Mover, Leaver (JML) lifecycle.
- Describe the purpose of identity governance.
- Explain how identity federation enables Single Sign-On.
- Understand how Zero Trust influences identity security.

---

## Topics Covered

### Authentication vs Authorization

Understand the difference between verifying identity and determining access.

---

### Identity vs Account Provisioning

Learn why identity changes occur before account changes and how identity lifecycle events drive downstream provisioning.

---

### Joiner, Mover, Leaver (JML)

Explore how enterprise organizations manage employee onboarding, role changes, and offboarding.

---

### Identity Governance

Learn how organizations oversee access requests, approvals, reviews, certifications, and compliance throughout the identity lifecycle.

---

### Identity Federation

Understand how trusted systems share authentication to provide seamless access across enterprise applications.

---

### Zero Trust

Learn why modern identity security assumes no user or device should be trusted by default, regardless of network location.

---

## Identity Fundamentals at a Glance

```text
                  Identity
                      │
      ┌───────────────┴───────────────┐
      ▼                               ▼
Authentication                  Provisioning
      │                               │
      ▼                               ▼
 Federation                  Identity Changes
      │                               │
      ▼                               ▼
Authorization              Account Changes
      │                               │
      └───────────────┬───────────────┘
                      ▼
               Application Access
                      │
                      ▼
             Governance & Compliance
```

Each concept builds upon the previous one.

Identity is established.

Identity is verified.

Identity is shared.

Access is granted.

Access is maintained.

Access is governed.

---

## Design Principles

Throughout this handbook, identity fundamentals are approached from an engineering perspective.

Every topic answers the following questions:

- What problem does this solve?
- Why does the enterprise need it?
- Where does it fit within the identity flow?
- What happens if it fails?
- How should it be investigated?

Understanding these relationships is more valuable than memorizing individual technologies.

---

## Next Steps

Continue through the documents in order:

1. Authentication vs Authorization
2. Identity vs Account Provisioning
3. Joiner, Mover, Leaver (JML)
4. Identity Governance
5. Identity Federation
6. Zero Trust

Each topic builds upon the previous one and will be referenced throughout the remainder of the handbook.