# Lab 01 – SAML SSO Integration with Microsoft Entra ID

## Objective

The objective of this lab was to understand how SAML-based Single Sign-On (SSO) works by integrating a Service Provider application with Microsoft Entra ID.

This lab focused on:
- Understanding SAML authentication flow
- Creating Enterprise Applications
- Configuring SAML SSO
- Assigning users
- Testing authentication
- Reviewing SAML assertions and claims

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

In this lab, Microsoft Entra ID acted as the Identity Provider responsible for authenticating users.

The SAML test application acted as the Service Provider and trusted Microsoft Entra ID to verify user identity.

After successful authentication, Entra ID generated a signed SAML assertion containing authentication details and user claims. The assertion was then sent back to the application through the ACS URL.

---

# Tasks Performed

## 1. Created Enterprise Application

Created a custom Enterprise Application in Microsoft Entra ID to simulate integration with a third-party application.

---

## 2. Configured SAML Single Sign-On

Enabled SAML authentication under the Single Sign-On settings of the Enterprise Application.

---

## 3. Added Entity ID and ACS URL

### Entity ID

https://sptest.iamshowcase.com/metadata

### ACS URL (Reply URL)

https://sptest.iamshowcase.com/acs

The Entity ID uniquely identified the Service Provider application.

The ACS URL defined where Microsoft Entra ID should send the SAML response after successful authentication.

---

## 4. Assigned Users

Assigned my user account to the application to allow access.

This step demonstrated authorization by defining which users were allowed to use the application.

---

## 5. Tested Authentication Flow

Successfully authenticated into the SAML test application using Microsoft Entra ID.

The application redirected the authentication request to Microsoft Entra ID, which verified the user identity and returned a SAML response.

---

## 6. Reviewed SAML Assertion Details

Validated authentication information and user claims sent from Microsoft Entra ID to the Service Provider.

The SAML assertion included:
- Authentication status
- User identity information
- Claims and attributes
- Identity Provider details
- Session information

---

# Authentication Flow

1. User opened the application  
2. Application redirected the user to Microsoft Entra ID for authentication  
3. User authenticated successfully  
4. Microsoft Entra ID generated a signed SAML assertion containing authentication details and user claims  
5. Assertion was sent to the ACS URL  
6. Application validated the SAML response and granted access  

---

# Claims Observed

The following claims were visible inside the SAML assertion:

- Display Name
- Email Address
- Given Name
- Surname
- Tenant ID
- Object Identifier
- Identity Provider

These claims provided user information to the application after successful authentication.

---

# Authentication vs Authorization

## Authentication

Authentication verifies the identity of the user.

In this lab, Microsoft Entra ID handled authentication by validating user credentials.

---

## Authorization

Authorization determines whether an authenticated user is allowed to access the application.

In this lab, user assignment controlled authorization.

---

---

# What I Learned

This lab helped me understand how enterprise applications use Microsoft Entra ID for authentication through SAML SSO.

I learned:

- How trust is established between an application and Identity Provider
- How SAML assertions are generated
- How claims are passed to applications
- Difference between authentication and authorization
- Importance of Entity ID and ACS URL during integration
- Basic SAML authentication workflow

---

# Interview Takeaway

After completing this lab, I can confidently explain:

- Basic SAML authentication flow
- Role of Identity Provider and Service Provider
- Purpose of ACS URL and Entity ID
- What a SAML assertion contains
- How user claims are sent during authentication
- Difference between authentication and authorization
