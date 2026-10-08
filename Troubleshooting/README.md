
# Troubleshooting, Security Findings and Testing Results

# Project Information

*Project: Zero Trust SSO Integration – Microsoft Entra ID and AWS  
*Programme: TechStylers Microsoft Cloud Security Bootcamp (Identity, Data & AI)  
*Team: Helix Group  
*Team Lead: Titilayo Yusuf  
*Project Completion:June 2025  
*Documentation: October 2026

# 1. Overview

This document presents the technical challenges, security findings, successful tests, and lessons learned during our TechStylers Bootcamp Final Project.

As Team Lead of Helix Group, I coordinated our collaborative project to integrate Microsoft Entra ID with AWS using SAML-based Single Sign-On (SSO), Multi-Factor Authentication (MFA), Conditional Access, and Role-Based Access Control (RBAC).

The project provided hands-on experience in identity federation, Zero Trust security, cloud access management, and troubleshooting.

During the final project presentation, we successfully demonstrated location-based Conditional Access and access to Azure resources through AWS. However, the original presentation also recorded an unsuccessful AWS Console SAML login.

These outcomes are documented separately to provide an accurate account of our project.

# 2. Finding 1: AWS Federated Sign-In Failure

*Category: Identity Federation / Authentication and Authorization  
*Affected Services: Microsoft Entra ID, SAML SSO, AWS IAM  
*Status: Unresolved in the original project presentation

# Description

Our team configured SAML-based identity federation between Microsoft Entra ID and AWS.

During testing, a SAML token was generated, but the attempted AWS Console login was unsuccessful.

# Observations

- Microsoft Entra ID and AWS federation components were configured.
- AWS IAM roles and trust relationships were established.
- A SAML token was generated during the login attempt.
- AWS Console access failed.
- The team identified the need to review the required permissions.

# Potential Causes

The following are possible troubleshooting areas rather than confirmed root causes:

1. Incorrect AWS IAM role trust configuration.
2. Incorrect SAML assertion attributes or role mappings.
3. Missing or insufficient role permissions.
4. Federation metadata mismatch.
5. Incorrect user-to-role assignments.

# Business and Security Impact

*Availability: Legitimate users could not complete the intended AWS Console login.

*Confidentiality: Incorrectly configured role mappings could potentially expose resources to unauthorized users, although no such exposure was demonstrated.

*Integrity: Overly permissive roles could potentially allow unauthorized changes to cloud resources. This was a potential risk, not a confirmed incident.

# Recommended Remediation

1. Review AWS IAM role trust policies.
2. Validate the SAML identity provider configuration.
3. Verify role mappings and SAML assertion attributes.
4. Review user and group assignments.
5. Confirm the necessary permissions are configured.
6. Repeat the complete AWS federated login test.

# 3. Finding 2: Trust Relationship and Federation Metadata Challenges

*Category: Identity Federation Configuration  
*Affected Services: Microsoft Entra ID and AWS IAM  
*Status:Troubleshooting discussed; resolution not documented

# Description

During the project, our team encountered challenges involving trust relationships and federation metadata.

These issues strengthened our understanding of how an identity provider and cloud service provider must be correctly configured to establish trusted authentication.

# Security Considerations

Incorrect federation configuration can prevent authorized users from accessing resources.

Overly permissive trust relationships could also introduce unintended access paths.

# Recommended Remediation

- Review identity provider metadata.
- Validate the AWS SAML provider configuration.
- Check IAM role trust relationships.
- Confirm that SAML attributes match the expected role mappings.
- Document configuration changes and retest the federation process.

# 4. Finding 3: Remaining End-to-End Security Validation Gaps

**Category: Security Testing and Validation  
**Affected Controls: SAML SSO, AWS IAM RBAC, MFA, SCIM Provisioning

# Description

Our team configured several identity and access management security controls and successfully demonstrated selected security functions during the final presentation.

However, not every end-to-end authentication, authorization, and provisioning test was documented as successful.

# Testing Results

| Security Control | Result |
|---|---|
| Location-Based Conditional Access | Successfully tested during the final presentation |
| AWS-to-Azure Resource Access | Successfully demonstrated |
| AWS Console SAML Login | SAML token generated, but access failed |
| Multi-Factor Authentication | Configured; separate testing evidence not documented |
| Role-Based Access Control | Groups and IAM roles configured; full AWS authorization not confirmed |
| SCIM Provisioning | Reported as enabled; successful synchronization testing not documented |

# Security Implications

Incomplete testing may leave uncertainty about whether all security controls operate as intended.

Although our Conditional Access test was successful, this did not establish that the entire AWS federated authentication and authorization process was functioning correctly.

# Recommended Improvements

1. Retest the unsuccessful AWS Console SAML login.
2. Verify permissions for each AWS IAM role.
3. Document MFA authentication test results.
4. Validate SCIM provisioning and deprovisioning.
5. Test authorized and unauthorized access scenarios.
6. Retain screenshots and logs as evidence.

## 5. Finding 4: Successful Conditional Access and Cross-Cloud Access Testing

**Category:** Zero Trust Security Validation  
**Status:** Successful demonstrations during the final presentation

### Test 1: Location-Based Conditional Access

During the TechStylers Bootcamp Final Project presentation in June 2025, our team successfully tested a Microsoft Entra ID Conditional Access policy.

The policy blocked a user sign-in based on location.

# Test Outcome

*Result: Successful*

The demonstration confirmed that the tested location-based access restriction operated as intended.

# Security Significance

- Demonstrated how Conditional Access can restrict sign-ins based on location.
- Validated identity-based access control.
- Reinforced the Zero Trust principle of verifying access requests.
- Provided practical experience testing Microsoft Entra security policies.

# Test 2: AWS-to-Azure Resource Access

During the final presentation, our team successfully accessed Azure resources through AWS.


# Security Significance

- Demonstrated a working AWS-to-Azure access scenario.
- Provided practical exposure to access across cloud environments.
- Reinforced the importance of managing authentication and authorization across cloud platforms.
- Highlighted the need to document the direction and outcome of cross-cloud access tests accurately.

# 6. Lessons Learned

# Identity Federation

I gained a deeper understanding of how SAML-based federation works between Microsoft Entra ID and AWS, including the importance of correct IAM role mappings and trust relationships.

# Authentication vs Authorization

The unsuccessful AWS Console login demonstrated that generating a SAML token does not automatically guarantee access to the requested cloud resources.

# Conditional Access Validation

Our successful location-based Conditional Access test reinforced the importance of validating access restrictions through practical demonstrations.

# Cross-Cloud Access

The successful AWS-to-Azure access demonstration strengthened our understanding of working across different cloud environments.

# Troubleshooting and Documentation

The project taught us to investigate configuration problems systematically, distinguish confirmed outcomes from possible causes, and document both successful and unsuccessful tests.

# Teamwork and Leadership

Serving as Team Lead strengthened my ability to coordinate team activities, support technical collaboration, communicate challenges, and contribute to project delivery.

# 7. Recommendations for Future Projects

Based on our experience, I recommend:

1. Establishing a clear test plan before implementing identity federation.
2. Validating SAML role mappings and trust relationships before demonstrations.
3. Testing MFA and Conditional Access under different scenarios.
4. Documenting both successful and failed authentication attempts.
5. Capturing configuration screenshots and relevant logs.
6. Verifying the complete authentication and authorization process.
7. Recording each team member's responsibilities and technical contributions.

# 8. Final Reflection

The TechStylers Bootcamp Final Project was a valuable hands-on learning experience that combined cloud security, identity and access management, Zero Trust principles, and teamwork.

As Helix Group Team Lead, I gained practical experience coordinating a collaborative cybersecurity project and supporting technical problem-solving.

Although our AWS Console SAML login was unsuccessful during the recorded test, we successfully demonstrated location-based Conditional Access and AWS-to-Azure resource access during the final presentation.

The experience reinforced an important lesson: security configurations must be tested, verified, and documented to demonstrate their effectiveness.


*Project: TechStylers Microsoft Cloud Security Bootcamp Final Project  
*Team: Helix Group  
*Role: Team Lead  
*Completed: June 2025  
*Documented on GitHub: October 2026


  

  
