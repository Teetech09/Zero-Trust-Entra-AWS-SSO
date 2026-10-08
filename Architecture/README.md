
## Zero Trust Identity Federation Architecture

### Project Background
This architecture was developed by Helix Group as part of the TechStylers Microsoft Cloud Security Bootcamp Final Project in June 2025.

The solution was designed for Oringo Ltd. to centralize employee authentication through Microsoft Entra ID and provide role-based access to AWS using SAML Single Sign-On (SSO).

# Architecture Components

1. **Microsoft Entra ID:** Central identity provider responsible for user authentication and group membership.
2. **Multi-Factor Authentication (MFA):** Microsoft Authenticator provides an additional authentication factor.
3. **Conditional Access:** Policies consider location, device compliance, and sign-in risk.
4. **SAML Federation:** Establishes federated authentication between Microsoft Entra ID and AWS.
5. **AWS IAM Roles:** Determine the permissions granted to users based on their assigned roles.
6. **Group-Based RBAC:** Microsoft Entra groups represent different job responsibilities and access levels.
7. **SCIM Provisioning:** The project presentation records enabling SCIM to synchronize users and groups from Entra ID to AWS.

# Authentication and Access Flow

1. A user initiates access to AWS through the federated sign-in process.
2. Microsoft Entra ID authenticates the user.
3. MFA and applicable Conditional Access policies are evaluated.
4. The user's group membership determines the intended AWS access role.
5. SAML federation provides authentication information to AWS.
6. AWS IAM roles define the permissions available to the federated user.

### Security Benefits

- Centralized identity and access management.
- Reduced reliance on separate AWS user credentials.
- Additional authentication protection through MFA.
- Access control based on job responsibilities.
- Conditional Access policies to strengthen authentication decisions.
- Support for least-privilege security principles.

# Implementation and Testing Status

The team configured Entra groups, AWS IAM roles, trust relationships, and SAML federation. During testing, a SAML token was generated, but AWS access failed because the required permissions were not correctly configured. The presentation does not confirm a successful end-to-end federated login.

# Architecture Diagram

The original architecture diagram will be added to this folder as `zero-trust-architecture.png`.

![Zero Trust Architecture](zero-trust-architecture.png)

# Project Leadership

*Team: Helix Group  
*Team Lead: Titilayo Yusuf  
*Programme: TechStylers Microsoft Cloud Security Bootcamp  
*Project Completion: June 2025
  
