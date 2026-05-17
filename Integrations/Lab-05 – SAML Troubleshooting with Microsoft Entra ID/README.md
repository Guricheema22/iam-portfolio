# Lab 05 – SAML Troubleshooting with Microsoft Entra ID

## Objective

The objective of this lab was to understand common SAML authentication and authorization failures by intentionally creating configuration issues and troubleshooting them in Microsoft Entra ID.

This lab focused on:
- ACS URL troubleshooting
- Authorization failures
- Claims mapping issues
- SAML authentication testing
- Troubleshooting methodology
- Restoring broken SSO configurations

---

# Tools Used

- Microsoft Entra ID
- Browser-based SAML Test Application
- Web Browser (Chrome/Edge)

---

# Key Concepts Learned

- ACS URL
- Authorization Failures
- Claims Mapping
- SAML Assertion Delivery
- Authentication vs Authorization
- SAML Troubleshooting
- Assertion Validation
- User Assignment

---

# Real-World Understanding

SAML integrations can fail for many different reasons such as incorrect URLs, invalid claims, expired certificates, or authorization issues.

IAM engineers are responsible for identifying where the authentication flow is breaking and resolving the issue.

This lab focused on intentionally breaking SAML configurations in order to understand how authentication and authorization failures occur in real-world environments.

---

# Tasks Performed

## 1. Tested Incorrect ACS URL

Modified the Reply URL (ACS URL) with an incorrect value.

### Original ACS URL
```text
https://sptest.iamshowcase.com/acs
```

### Incorrect ACS URL
```text
https://wrongurl.com/acs
```

After testing authentication, the application failed because the SAML assertion was sent to the wrong destination.

This demonstrated how important ACS URL configuration is during SAML authentication.

---

## 2. Investigated User Assignment Failure

Removed the user assignment from the Enterprise Application and tested access again.

Observed:
- Authorization failure
- Access denied behavior

This demonstrated the difference between:
- Authentication
- Authorization

The Identity Provider could still authenticate the user, but the user was not authorized to access the application.

---

## 3. Tested Incorrect Claims Mapping

Modified the department claim mapping.

### Original Mapping
```text
user.department → department
```

### Incorrect Mapping
```text
user.city → department
```

This caused incorrect attribute data to be sent inside the SAML assertion.

The test demonstrated how incorrect claims can impact application authorization and user access.

---

## 4. Restored Working Configuration

Restored:
- Correct ACS URL
- Correct user assignment
- Correct claim mappings

Verified that SAML authentication worked successfully again after configuration correction.

---

# Common SAML Troubleshooting Areas

## ACS URL Mismatch

Incorrect ACS URLs can cause assertions to be delivered to invalid destinations, resulting in login failures.

---

## Authorization Failures

Users may authenticate successfully but still be denied access if they are not assigned to the application.

---

## Claims Mapping Issues

Incorrect claims can cause:
- Incorrect permissions
- Missing user attributes
- Authorization problems
- Application access failures

---

## Assertion Validation Issues

Applications validate:
- Audience restriction
- Issuer
- Signature
- Assertion conditions

Incorrect validation settings can cause SAML authentication failures.

---

# Troubleshooting Workflow

1. Verify authentication success  
2. Verify user assignment and authorization  
3. Validate ACS URL configuration  
4. Review claim mappings  
5. Validate assertion details and trust settings  
6. Restore correct configuration and retest authentication  

---

# What I Learned

This lab helped me understand how IAM engineers troubleshoot SAML integrations in real-world environments.

I learned:
- How ACS URL mismatches affect SAML authentication
- Difference between authentication and authorization failures
- How incorrect claims impact application access
- How to investigate SAML configuration issues
- Importance of validating SAML configuration step-by-step
- How to restore and retest broken SSO configurations
