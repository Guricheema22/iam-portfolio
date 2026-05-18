# Lab 06 – App Registrations and OpenID Connect (OIDC) Authentication

## Objective

The objective of this lab was to understand how modern applications integrate with Microsoft Entra ID using OpenID Connect (OIDC) and token-based authentication.

This lab focused on:
- App Registrations
- OIDC authentication flow
- Client IDs
- Redirect URIs
- JWT tokens
- Modern cloud authentication concepts
- Tenant-specific authentication endpoints

---

# Tools Used

- Microsoft Entra ID
- jwt.ms
- Web Browser (Chrome/Edge)

---

# Key Concepts Learned

- OpenID Connect (OIDC)
- App Registrations
- Client ID
- Redirect URI
- JWT Tokens
- Token Claims
- Audience
- Issuer
- Tenant-Specific Authentication
- Single-Tenant vs Multi-Tenant Applications

---

# Real-World Understanding

Modern cloud applications commonly use OpenID Connect (OIDC) instead of traditional SAML authentication.

OIDC uses token-based authentication and lightweight JSON Web Tokens (JWTs) to authenticate users and provide identity information to applications.

Applications integrate with Microsoft Entra ID through App Registrations, which define:
- Application identity
- Redirect URIs
- Authentication configuration
- Token permissions

---

# Tasks Performed

## 1. Created App Registration

Created a new App Registration in Microsoft Entra ID.

### Configuration Used

#### Application Name
```text
OIDC-Test-App
```

#### Supported Account Type
```text
Single Tenant
```

#### Redirect URI
```text
https://jwt.ms
```

The Redirect URI defines where Microsoft Entra ID sends the authentication response after successful login.

---

## 2. Investigated App Registration Overview

Reviewed:
- Application (Client) ID
- Directory (Tenant) ID
- Object ID

### Client ID
The Client ID uniquely identifies the application during authentication.

### Tenant ID
The Tenant ID identifies the Microsoft Entra organization hosting the application.

---

## 3. Configured Authentication Settings

Opened the Authentication section and verified:
- Redirect URI configuration
- ID token support enabled

Enabled:
```text
ID Tokens
```

This allows Microsoft Entra ID to issue ID tokens during OpenID Connect authentication.

---

## 4. Tested OIDC Authentication Flow

Performed OpenID Connect authentication using an authorization request URL.

Authentication flow:
1. User redirected to Microsoft login
2. User authenticated successfully
3. Microsoft Entra ID generated ID token
4. Token redirected to jwt.ms
5. jwt.ms decoded and displayed the JWT token

---

## 5. Investigated JWT Token

Reviewed decoded JWT token inside jwt.ms.

Observed claims such as:
- aud (Audience)
- iss (Issuer)
- iat (Issued At)
- nbf (Not Before)
- exp (Expiration)
- Tenant ID
- User identity information

---

## 6. Investigated Authentication Endpoint Error

Initially tested authentication using:
```text
/common/
```

endpoint.

Authentication failed because the application was configured as:
```text
Single Tenant
```

The `/common/` endpoint is designed for multi-tenant authentication scenarios.

Resolved the issue by using the tenant-specific authentication endpoint.

---

# OIDC Authentication Flow

1. User opens application  
2. Application redirects user to Microsoft Entra ID  
3. User authenticates successfully  
4. Microsoft Entra ID generates JWT ID token  
5. Token is sent to Redirect URI  
6. Application validates token and grants access  

---

# Understanding Important OIDC Components

## App Registration

Defines how applications integrate with Microsoft Entra ID for authentication.

---

## Client ID

Unique identifier assigned to the application.

---

## Redirect URI

Defines where authentication responses and tokens are sent after login.

---

## JWT Token

JSON Web Token used to carry authentication and identity information.

---

## Audience (aud)

Defines which application the token was intended for.

---

## Issuer (iss)

Identifies the Identity Provider that generated the token.

---

# SAML vs OIDC Comparison

| SAML | OIDC |
|---|---|
| XML Assertions | JWT Tokens |
| Browser-focused | API and cloud-friendly |
| Heavy XML structure | Lightweight JSON |
| Traditional enterprise apps | Modern cloud/mobile apps |

---

# What I Learned

This lab helped me understand how modern authentication works using OpenID Connect and Microsoft Entra ID.

I learned:
- How App Registrations work
- Purpose of Client IDs and Redirect URIs
- How JWT tokens are generated and validated
- How modern applications authenticate users
- Difference between SAML and OIDC authentication
- How tenant-specific authentication endpoints work
- Importance of audience and issuer validation during token authentication
