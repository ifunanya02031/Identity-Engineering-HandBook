# Authentication vs Authorization

## The Problem

One of the most common misconceptions in Identity & Access Management is treating authentication and authorization as the same process.

They are not.

Authentication verifies identity.

Authorization determines access.

Understanding the difference is fundamental to troubleshooting enterprise identity systems.

---

## Authentication

Authentication answers one question:

> **Who are you?**

Authentication verifies a user's identity before access to any application is considered.

Authentication is performed by the Identity Provider (IdP).

Common authentication methods include:

- Username & Password
- Multi-Factor Authentication (MFA)
- Passkeys
- Biometrics
- Certificates
- Smart Cards

If authentication fails, the identity flow stops immediately.

No assertion is generated.

No federation occurs.

No authorization is evaluated.

---

## Authorization

Authorization answers one question:

> **What are you allowed to do?**

Authorization occurs **after** successful authentication and successful federation.

Applications determine authorization using information such as:

- Roles
- Groups
- Claims
- Permissions
- Policies
- Entitlements

Authorization is performed by the application (Service Provider), not the Identity Provider.

---

## Where They Fit

Authentication is the first security decision.

Authorization is the last.

```text
User
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
Application Access
```

Every successful login follows this sequence.

---

## Authentication vs Authorization

| Authentication | Authorization |
|----------------|---------------|
| Verifies identity | Determines access |
| Performed by the Identity Provider | Performed by the Service Provider |
| Occurs first | Occurs last |
| Uses credentials | Uses roles, groups, claims, and permissions |
| Answers "Who are you?" | Answers "What can you access?" |

---

## Enterprise Example

An employee attempts to access Salesforce.

Step 1

The employee is redirected to Okta.

Okta verifies the employee's identity using a password and Multi-Factor Authentication.

Authentication succeeds.

Step 2

Okta generates a SAML assertion and sends it to Salesforce.

Salesforce validates the assertion.

Federation succeeds.

Step 3

Salesforce evaluates the employee's department, role, and group membership contained within the assertion.

The employee is assigned the Sales role.

Authorization succeeds.

Access is granted.

---

## Authentication Failure

Possible causes include:

- Incorrect password
- Failed MFA challenge
- Disabled account
- Authentication policy blocks access
- High-risk sign-in
- Untrusted device

Result:

Authentication fails.

The remaining identity flow never begins.

---

## Authorization Failure

Possible causes include:

- Missing role
- Missing group membership
- Missing entitlement
- Insufficient permissions
- Application-specific authorization policy

Result:

Authentication succeeds.

Federation succeeds.

Authorization fails.

Access is denied.

---

## Common Misconceptions

**Authentication succeeded, therefore the user should have access.**

Incorrect.

Authentication only proves identity.

Applications still determine what that identity is allowed to do.

---

**Authorization failures are authentication problems.**

Incorrect.

If the user successfully signs in but cannot access a resource, the issue is likely authorization rather than authentication.

---

## Troubleshooting Checklist

### Authentication

- Is the account active?
- Was the correct credential used?
- Did MFA succeed?
- Did an authentication policy block the request?
- Was the sign-in considered high risk?

---

### Authorization

- Is the user assigned the correct application?
- Does the user belong to the correct group?
- Does the assertion contain the expected claims?
- Does the application recognize those claims?
- Does the assigned role include the required permissions?

---

## Key Takeaways

- Authentication verifies identity.
- Authorization determines access.
- Authentication occurs before federation.
- Authorization occurs after federation.
- Authentication failure prevents the remaining identity flow.
- Successful authentication does not guarantee successful authorization.

---

## Related Topics

- Authentication
- Federation
- Single Sign-On
- Assertions
- Claims
- RBAC
- Identity Governance
```