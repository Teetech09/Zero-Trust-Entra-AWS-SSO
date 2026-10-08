
# Security Controls and Compliance Mapping

# Project Overview
This document describes the security controls incorporated into the Zero Trust SSO Integration project completed by Helix Group during the TechStylers Microsoft Cloud Security Bootcamp in June 2025.

The project focused on strengthening identity security by integrating Microsoft Entra ID with AWS through federated authentication, Multi-Factor Authentication (MFA), Conditional Access, and Role-Based Access Control (RBAC).

# 1. Security Controls Implemented

# Multi-Factor Authentication (MFA)
*Control:* Microsoft Authenticator MFA

*Purpose: Add an extra layer of authentication to reduce unauthorized access when user credentials are compromised.

*Project Activity:* The team configured MFA requirements through Microsoft Entra ID.

# Role-Based Access Control (RBAC)
*Control: Microsoft Entra ID groups mapped to AWS IAM roles

*Purpose: Restrict access based on users' responsibilities.

*Project Activity: The team configured three groups: AdminAccess, DevReadOnly, and FinanceViewer, each associated with an intended AWS access level.

# Conditional Access
**Control: Microsoft Entra Conditional Access policies

**Purpose: Evaluate access requests based on contextual signals such as location, device compliance, and sign-in risk.

**Project Activity: The team configured Conditional Access policies as part of its Zero Trust design.

# Federated Authentication
*Control: SAML-based Single Sign-On (SSO)

*Purpose: Centralize authentication and reduce the need to manage separate AWS user passwords.

*Project Activity: The team configured SAML federation between Microsoft Entra ID and AWS. A SAML token was generated during testing, and successful AWS console access was confirmed.

# Centralized Identity Management
*Control: Microsoft Entra ID identity and group management

*Purpose: Manage user identities and access assignments centrally.

*Project Activity: Users were created through Microsoft 365 Admin Center and assigned to department-based Entra groups. The presentation also records enabling SCIM provisioning.

# 2. Security Framework Mapping

| Framework | Relevant Security Area | Project Application |
|---|---|---|
| ISO/IEC 27001 | Identity management, access control and authentication | MFA, group-based RBAC, Conditional Access |
| NIST SP 800-53 | Access Control (AC), Identification and Authentication (IA) | IAM roles, SAML federation, MFA |
| DORA | ICT security and access protection | Centralized authentication and identity access controls |
| Zero Trust | Verify explicitly, use least privilege | MFA, Conditional Access, role-based permissions |

These mappings describe conceptual alignment with security requirements. They do not represent a formal compliance assessment or certification.

# 3. Security Considerations and Limitations

- The final presentation records a generated SAML token but unsuccessful AWS console access.
- Successful end-to-end identity federation was not verified.
- Conditional Access policies were successfully tested during the final project presentation in June 2025. However, successful end-to-end AWS federated login was not achieved.
- SCIM provisioning was reported as enabled, but successful synchronization was not independently demonstrated.
- Administrative access was included in the role design and requires careful restriction and monitoring in a production environment.

# 4. Recommended Security Improvements

1. Correct and retest the AWS federation permissions and trust configuration.
2. Validate successful and denied sign-in scenarios.
3. Review IAM permissions against least-privilege requirements.
4. Test Conditional Access policies under different user and device conditions.
5. Verify SCIM provisioning and deprovisioning behavior.
6. Enable appropriate sign-in and AWS activity monitoring.

These are recommended follow-up activities, not claims that the team completed them.

# 5. Conclusion

The project provided practical exposure to identity federation, Zero Trust access controls, and security framework mapping. It also demonstrated the importance of validating authentication and authorization before considering an integration operational.

**Project: TechStylers Bootcamp Final Project  
**Team: Helix Group  
**Team Lead: Titilayo Yusuf  
**Project Date: June 2025
  
