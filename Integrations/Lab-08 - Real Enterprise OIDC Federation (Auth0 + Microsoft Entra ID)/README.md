# Lab 08 — Real Enterprise OIDC Federation (Auth0 + Microsoft Entra ID)

## Objective

The objective of this lab was to build a real-world OpenID Connect (OIDC) federation between Microsoft Entra ID and Auth0 to understand how enterprise Single Sign-On (SSO) works in modern cloud IAM environments.

This lab focused on:
- OIDC federation
- OAuth 2.0 authentication flow
- JWT token generation and investigation
- Redirect URI handling
- Federation trust relationships
- Enterprise authentication troubleshooting

---

# Technologies Used

- Microsoft Entra ID
- Auth0
- OpenID Connect (OIDC)
- OAuth 2.0
- JWT Tokens
- jwt.ms

---

# Architecture Overview

```text
User
↓
Auth0 Application
↓
Redirect to Microsoft Entra ID
↓
User Authentication
↓
OIDC Token Issued
↓
Auth0 validates federation trust
↓
JWT Token generated
↓
Redirect to jwt.ms for token inspection
```

---

# Key IAM Concepts Covered

- OpenID Connect (OIDC)
- OAuth 2.0
- Identity Federation
- Single Sign-On (SSO)
- JWT Tokens
- Claims Analysis
- Audience Validation
- Issuer Validation
- Redirect URIs
- Federation Trust
- Client ID and Client Secret
- Replay Protection using Nonce
- Enterprise Authentication Troubleshooting

---

# Lab Steps Performed

## 1. Created Auth0 Web Application

Created a Regular Web Application in Auth0 named:

```text
Entra-OIDC-Lab
```

Configured:
- Allowed Callback URL
- Allowed Logout URL

Using:

```text
https://jwt.ms
```

---

## 2. Registered Application in Microsoft Entra ID

Created an App Registration in Microsoft Entra ID.

Configured:
- Single Tenant Application
- Web Platform
- Redirect URI

Generated:
- Client ID
- Client Secret

---

## 3. Configured Microsoft Federation in Auth0

Configured Enterprise Connection in Auth0 using:
- Microsoft Entra Tenant Domain
- Client ID
- Client Secret

Enabled:
- Microsoft Identity Platform (v2)
- OpenID Connect Protocol

---

## 4. Enabled Federation Login

Configured:
- Display Connection as Button
- Disabled Username-Password Authentication

This forced users to authenticate through Microsoft Entra federation instead of local Auth0 database authentication.

---

## 5. Tested OIDC Federation Flow

Used Auth0 authorization endpoint to initiate OIDC authentication flow.

Successful flow:

```text
Auth0
↓
Microsoft Entra Login
↓
Successful Authentication
↓
OIDC Token Issued
↓
Redirect to jwt.ms
↓
JWT Claims Displayed
```

---

# JWT Token Investigation

After successful authentication, the JWT token was investigated using jwt.ms.

The following important claims were analyzed:

| Claim | Purpose |
|---|---|
| aud | Audience (target application) |
| iss | Token issuer |
| exp | Token expiration |
| iat | Issued at time |
| sub | Unique user identity |
| nonce | Replay protection |
| sid | Session identifier |
| email | User identity claim |

---

# Important Security Concepts Learned

## Audience Validation

Applications validate the `aud` claim to verify whether the token was specifically issued for that application.

---

## Issuer Validation

The `iss` claim identifies the trusted identity provider that issued the token.

---

## Nonce Protection

OIDC uses nonce values to prevent replay attacks and unauthorized reuse of authentication responses.

---

## Redirect URI Security

Identity providers only redirect authentication responses to pre-approved redirect URIs to prevent token theft and malicious redirection attacks.

---

# Real-World IAM Understanding

This lab simulated a real enterprise federation environment where:
- Auth0 acted as the federation broker
- Microsoft Entra ID acted as the Identity Provider (IdP)
- OIDC handled authentication
- JWT tokens securely carried user identity claims between systems

This lab also demonstrated how IAM engineers troubleshoot:
- Federation issues
- Redirect URI problems
- Authentication flow failures
- Session reuse behavior
- Token validation issues
- Identity provider routing problems

---

# Screenshots

| Screenshot |
|---|
| 01-auth0-web-application-created |
| 02-auth0-callback-and-logout-config |
| 03-entra-app-registration-created |
| 04-entra-app-overview |
| 05-entra-client-secret-created |
| 06-auth0-microsoft-federation-config |
| 07-auth0-login-button-enabled |
| 08-auth0-database-login-disabled |
| 09-auth0-microsoft-login-page |
| 10-successful-jwt-token-issued |

---

# Skills Gained

- Microsoft Entra ID Federation
- OpenID Connect (OIDC)
- OAuth 2.0
- JWT Token Investigation
- Enterprise SSO Configuration
- Authentication Troubleshooting
- Identity Federation
- Modern Authentication Architecture
- IAM Security Concepts
- Federation Debugging

---

# Outcome

Successfully implemented and tested a real enterprise OIDC federation between Auth0 and Microsoft Entra ID, authenticated users through federated SSO, and investigated real JWT authentication tokens and claims.
