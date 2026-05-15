# Lab 01 – SAML SSO Integration with Microsoft Entra ID

## Objective
The objective of this lab was to understand how SAML-based Single Sign-On (SSO) works by integrating a Service Provider application with Microsoft Entra ID.

---

# Tools Used
- Microsoft Entra ID
- Browser-based SAML Test Application
- Web Browser (Chrome/Edge)

---

# Key Concepts Learned
- Identity Provider (IdP)
- Service Provider (SP)
- SAML Authentication
- SAML Assertion
- Claims / Attributes
- Entity ID
- ACS URL (Reply URL)
- Authentication vs Authorization

---

# Real-World Understanding

In this lab, Microsoft Entra ID acted as the Identity Provider responsible for authenticating the user.

The test application trusted Entra ID to verify the user identity instead of handling authentication itself.

After successful authentication, Entra ID generated a SAML assertion containing authentication details and user claims, which was sent back to the application.

---

# Tasks Performed

## 1. Created Enterprise Application
Created a custom Enterprise Application in Microsoft Entra ID to simulate integration with a third-party application.

---

## 2. Configured SAML Single Sign-On
Enabled SAML authentication under Single Sign-On settings.

---

## 3. Added Entity ID and ACS URL

4. Assigned Users

Assigned my user account to the application to allow access.

5. Tested Authentication Flow

Successfully authenticated into the SAML test application using Microsoft Entra ID.

6. Reviewed SAML Assertion Details

Validated authentication information and user claims sent from Entra ID to the Service Provider.

Authentication Flow
User opened the application
Application redirected user to Microsoft Entra ID
User authenticated successfully
Entra ID generated SAML assertion
Assertion was sent to the ACS URL
Application granted access
Claims Observed

The following claims were visible inside the SAML assertion:

Display Name
Email Address
Given Name
Surname
Tenant ID
Object Identifier
Identity Provider
- Basic SAML authentication workflow
