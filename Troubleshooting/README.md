
# Troubleshooting and Security Findings

# Project Background

This document describes the technical challenges and security observations from the TechStylers Microsoft Cloud Security Bootcamp Final Project completed by Helix Group in June 2025.

*Project: Zero Trust SSO Integration – Microsoft Entra ID and AWS  
*Team: Helix Group  
*Team Lead: Titilayo Yusuf

# Finding 1: Federated AWS Sign-In Failure

*Category: Identity Federation / Authentication and Authorization  
*Affected Services: Microsoft Entra ID, SAML SSO, AWS IAM  
*Status: Unresolved in the final presentation

# Description
The team configured SAML-based identity federation between Microsoft Entra ID and AWS. During the functional demonstration, a SAML token was generated, but access to the AWS Console failed.

# Observation
- Microsoft Entra ID and AWS federation components were configured.
- A SAML token was generated during testing.
- AWS Console access was unsuccessful.
- The team identified a need to review permissions before login could succeed.

# Potential Causes for Further Investigation
The following are troubleshooting possibilities, not confirmed root causes:

- Incorrect AWS IAM role permissions or trust configuration.
- Incorrect SAML assertion attributes or role mapping.
- Federation metadata or configuration mismatch.
- Missing or incorrect user-to-role assignment.

# Business and Security Impact
The confirmed impact was an availability issue: intended users could not successfully access AWS through the configured federated sign-in process.

Overly permissive role mappings or trust policies could also create confidentiality and integrity risks. However, no unauthorized access was demonstrated in the presentation.

# Recommended Remediation
1. Review the AWS SAML identity provider configuration.
2. Verify IAM role trust policies.
3. Validate the SAML assertion and role attributes.
4. Review Entra group-to-AWS role mappings.
5. Confirm that users have the required role assignments.
6. Retest the complete authentication and authorization flow.

# Finding 2: Federation Configuration and Metadata Troubleshooting

*Category: Identity Federation Configuration  
*Affected Services: Microsoft Entra ID and AWS IAM  
*Status: Troubleshooting discussed; exact resolution not documented

# Description
The team's final presentation identifies trust relationship errors and metadata issues among the technical challenges encountered.

# Security Considerations
Incorrect trust configuration may prevent legitimate access. Overly broad trust relationships could also create unintended access paths.

# Recommended Remediation
- Review SAML federation metadata.
- Validate identity provider and service provider configuration.
- Check IAM role trust relationships.
- Document configuration changes and test results.

# Finding 3: End-to-End Security Validation Gap

**Category:** Security Testing and Validation  
**Affected Controls:** MFA, Conditional Access, RBAC, SAML SSO, SCIM Provisioning

# Description
The presentation records the configuration of several identity security controls, but it does not provide evidence that all end-to-end authentication, authorization, Conditional Access, and provisioning scenarios were successfully tested.

This is a documentation and verification limitation, not proof that the controls were ineffective.

# Potential Security Impact
Without complete validation, an organization may be unable to confirm that intended users receive appropriate access or that unauthorized access is consistently denied.

# Recommended Remediation
- Test successful and unsuccessful sign-in scenarios.
- Verify MFA enforcement.
- Validate Conditional Access behavior.
- Test least-privilege permissions for each AWS role.
- Confirm SCIM user provisioning and deprovisioning.
- Record test evidence and outcomes.

# Key Lessons Learned

1. Successful SAML token generation does not automatically mean AWS authorization will succeed.
2. IAM role trust relationships and permission assignments are essential to federated access.
3. Security controls must be tested, not merely configured.
4. Troubleshooting requires reviewing both identity provider and AWS configurations.
5. Technical documentation should distinguish confirmed results from assumptions.
6. Team collaboration and communication are important when investigating complex cloud identity issues.

# Final Reflection

As Team Lead, this project strengthened my understanding of identity federation, Zero Trust architecture, cloud access management, and collaborative troubleshooting.

The experience reinforced the importance of validating security configurations and documenting unresolved technical challenges transparently.

*Project Completion: June 2025  
*GitHub Documentation: October 2026
  
