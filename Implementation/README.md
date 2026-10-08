
# Technical Implementation

# Project Background
This implementation was carried out by Helix Group during the TechStylers Microsoft Cloud Security Bootcamp Final Project in June 2025. I served as Team Lead, coordinating the team's collaborative activities.

# Phase 1: Microsoft Entra ID Group Configuration
The team created three groups in Microsoft Entra ID to support department-based access control:

| Entra ID Group | AWS IAM Role | Intended Access |
|---|---|---|
| GRP-AWS-AdminAccess | AdminAccess | Full administrative access |
| GRP-AWS-DevReadOnly | DevReadOnly | Read-only access to development tools |
| GRP-AWS-FinanceViewer | FinanceViewer | View-only access to billing features |

Users were assigned to groups based on their job responsibilities.

# Phase 2: AWS IAM Role Configuration
The team configured AWS IAM roles and trust relationships to support identity federation with Microsoft Entra ID.

The intended security approach was to assign permissions through roles instead of managing separate AWS credentials for each employee.

# Phase 3: SAML-Based Single Sign-On
Microsoft Entra ID was integrated with AWS using SAML-based identity federation.

During testing, a SAML token was generated, but access to AWS failed. The team identified a need to correct permissions before successful sign-in could be achieved.

A successful end-to-end AWS login was not confirmed in the final presentation.

# Phase 4: Multi-Factor Authentication
The team implemented Microsoft Authenticator MFA as an additional authentication control for users.

The objective was to reduce the risk of unauthorized access if a user's password became compromised.

# Phase 5: Conditional Access
The project included Conditional Access policies based on:

- User location
- Device compliance
- Sign-in risk

These controls were intended to strengthen authentication decisions in line with Zero Trust principles.

# Phase 6: SCIM User Provisioning
The project presentation records that SCIM provisioning was enabled to synchronize users and groups from Microsoft Entra ID to AWS.

Users were initially created manually through the Microsoft 365 Admin Center. The presentation does not include independent evidence confirming successful end-to-end SCIM synchronization.

# Implementation Outcome
The team completed configuration activities involving Entra ID groups, AWS IAM roles, SAML federation, MFA, Conditional Access, and SCIM provisioning.

However, the recorded functional test showed that a SAML token was generated while AWS console access failed. The project therefore demonstrates configuration experience and troubleshooting, rather than a fully verified production-ready integration.

# Team Leadership
*Team: Helix Group  
*Team Lead: Titilayo Yusuf  
*Programme: TechStylers Microsoft Cloud Security Bootcamp  
*Project Date: June 2025
  
