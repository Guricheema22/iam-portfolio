# Lab 09 – Microsoft Graph API and OAuth Access Tokens

## Objective

The objective of this lab was to understand how OAuth 2.0 Access Tokens are used to securely access APIs using delegated permissions in Microsoft Entra ID.

This lab focused on:
- OAuth 2.0
- Access Tokens
- Microsoft Graph API
- OAuth scopes and permissions
- Delegated authorization
- Consent flow
- JWT access token investigation

---

# Tools Used

- Microsoft Entra ID
- Microsoft Graph API
- jwt.ms
- Web Browser (Chrome/Edge)

---

# Key Concepts Learned

- OAuth 2.0
- Access Tokens
- Delegated Permissions
- OAuth Scopes
- Consent
- Microsoft Graph API
- JWT Claims
- API Authorization
- Audience (`aud`)
- Scope Claim (`scp`)

---

# Real-World Understanding

Modern cloud applications use OAuth 2.0 and Access Tokens to securely access APIs and resources on behalf of users.

Unlike ID Tokens, which are mainly used for authentication, Access Tokens are used for:
- API authorization
- Accessing protected resources
- Delegated access

Applications request permissions through OAuth scopes and receive Access Tokens containing those permissions after successful user consent and authentication.

---

# Tasks Performed

## 1. Investigated API Permissions

Opened the App Registration:
```text
OIDC-Test-App
```

Reviewed delegated API permissions configured for Microsoft Graph.

### Permissions Observed

| Permission | Purpose |
|---|---|
| openid | OIDC authentication |
| profile | Basic user profile |
| email | User email access |
| User.Read | Read signed-in user profile |

---

# Understanding Delegated Permissions

Delegated permissions allow applications to act on behalf of the signed-in user.

Example:
```text
User.Read
```

means:
- Application can read the currently signed-in user’s profile
- Permission is limited to that user context

---

## 2. Configured Authentication Settings

Opened:
```text
Authentication
```

Enabled:
- Access Tokens
- ID Tokens

under:
```text
Implicit grant and hybrid flows
```

This allowed the application to request OAuth Access Tokens through browser authentication flow.

---

## 3. Generated Real OAuth Access Token

Used OAuth authorization request URL to generate an Access Token from Microsoft Entra ID.

### OAuth Request Components

| Parameter | Purpose |
|---|---|
| client_id | Identifies application |
| response_type=token | Requests Access Token |
| redirect_uri | Token return location |
| scope | Requested permissions |
| nonce | Security protection |

---

# OAuth Consent Flow

During login, Microsoft Entra displayed a consent prompt requesting permission to:
```text
Read your profile
```

This demonstrated delegated authorization where the user grants API access permissions to the application.

---

## 4. Investigated Access Token Using jwt.ms

After successful authentication, jwt.ms displayed the decoded Access Token.

Investigated important JWT claims such as:
- aud
- scp
- iss
- exp
- tid

---

# Important JWT Claims Investigated

## aud (Audience)

Defines which API/resource the token is intended for.

In this lab:
```text
Microsoft Graph API
```

This demonstrated that Access Tokens target APIs/resources rather than applications.

---

## scp (Scope)

Defines permissions granted to the Access Token.

Observed:
```text
User.Read
```

Meaning:
- Token can read signed-in user profile from Microsoft Graph API

---

## iss (Issuer)

Identifies Microsoft Entra ID as the Identity Provider issuing the token.

---

## exp (Expiration)

Defines token expiration time for security purposes.

---

# Access Token vs ID Token

| ID Token | Access Token |
|---|---|
| Authentication | API authorization |
| Identifies user | Grants API access |
| Audience = Application | Audience = API |
| Used for login/session | Used for protected resources |

---

# OAuth Authorization Flow

```text
User logs in
↓
Entra ID authenticates user
↓
Access Token generated
↓
Application calls Microsoft Graph API
↓
API validates token and scopes
↓
API returns data
```

---

# What I Learned

This lab helped me understand how OAuth 2.0 works in real cloud environments using Access Tokens and APIs.

I learned:
- Difference between ID Tokens and Access Tokens
- How delegated permissions work
- Purpose of OAuth scopes
- How APIs validate Access Tokens
- Importance of token audience (`aud`)
- How permissions appear inside the `scp` claim
- How modern cloud applications securely access APIs using OAuth

This lab also helped connect authentication concepts with real API authorization workflows used in modern IAM environments.
