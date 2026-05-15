# Lab 02 – SAML Claims Mapping with Microsoft Entra ID

## Objective

The objective of this lab was to understand how SAML claims work and how user attributes are passed from Microsoft Entra ID to a Service Provider application during authentication.

This lab focused on:
- Understanding claims and attributes
- Investigating existing claims
- Mapping user attributes
- Creating custom claims
- Testing updated SAML assertions
- Understanding how applications use claims for authorization

---

# Tools Used

- Microsoft Entra ID
- Browser-based SAML Test Application
- Web Browser (Chrome/Edge)

---

# Key Concepts Learned

- SAML Claims
- Claims Mapping
- Source Attributes
- User Attributes
- SAML Assertion
- Authentication vs Authorization
- Attribute Flow
- Identity Provider (IdP)
- Service Provider (SP)

---

# Real-World Understanding

Applications often require user information after authentication in order to personalize the user experience and apply authorization rules.

Microsoft Entra ID collects user attributes from the user profile and sends them to the Service Provider as claims inside the SAML assertion.

These claims can include:
- Email Address
- Department
- Given Name
- Surname
- Roles
- Group Information

Applications use these claims to determine what the authenticated user is allowed to access.

---

# Tasks Performed

## 1. Reviewed Existing Claims

Investigated default claims already configured in the SAML application.

Observed:
- Claim names
- Source attributes
- User attribute mappings

Example:
```text
user.department → department
```

This means Microsoft Entra ID retrieves the department value from the user profile and sends it to the application as a claim named "department".

---

## 2. Investigated Claim Source Attributes

Reviewed how Microsoft Entra ID maps internal user attributes to claims sent to the application.

Examples:
- user.givenname
- user.surname
- user.mail
- user.department

---

## 3. Added Custom Claim

Created a custom SAML claim named:
```text
department
```

Mapped the claim to:
```text
user.department
```

This allowed the application to receive department information during authentication.

---

## 4. Tested Authentication Flow

Performed another SAML authentication test after adding the custom claim.

Validated that the updated claim appeared inside the SAML assertion.

---

## 5. Reviewed Updated SAML Assertion

Verified that the SAML assertion now included the custom department claim along with other user attributes.

---

# Authentication Flow

1. User opened the application  
2. Application redirected the user to Microsoft Entra ID for authentication  
3. User authenticated successfully  
4. Microsoft Entra ID collected user attributes  
5. Entra ID generated a signed SAML assertion containing claims and authentication details  
6. Assertion was sent to the ACS URL  
7. Application validated the assertion and granted access  

---

# Claims Observed

The following claims were visible inside the SAML assertion:

- Display Name
- Email Address
- Given Name
- Surname
- Department
- Tenant ID
- Object Identifier
- Identity Provider

---

# Understanding Claims Mapping

## Source Attribute

Example:
```text
user.department
```

This is the internal user attribute stored in Microsoft Entra ID.

---

## Claim Name

Example:
```text
department
```

This is the claim name sent to the Service Provider application.

---

## Mapping Example

```text
user.department → department
```

This mapping allows Microsoft Entra ID to send the user's department information to the application during authentication.

---

# Authentication vs Authorization

## Authentication

Authentication verifies the identity of the user.

Microsoft Entra ID handled authentication by validating user credentials.

---

## Authorization

Authorization determines what the authenticated user is allowed to access inside the application.

Applications often use claims such as department or role to make authorization decisions.

---


# What I Learned

This lab helped me understand how user attributes are mapped and sent to applications during SAML authentication.

I learned:
- How claims are generated
- How claims mapping works
- Difference between source attributes and claim names
- How applications use claims for authorization
- How user identity information flows through SAML authentication
- How custom claims are added in Microsoft Entra ID
