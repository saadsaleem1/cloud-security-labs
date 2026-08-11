# SC-500 Lab 3: Microsoft Entra ID Access Reviews

## Objective

Configure and perform an access review using Microsoft Entra ID Governance to validate whether a user should retain membership in a security group.

## Environment

- Microsoft Azure
- Microsoft Entra ID
- Microsoft Entra ID Governance
- Microsoft Entra Access Reviews
- Microsoft My Access

## Scenario

Organizations should periodically review user access to ensure that users retain only the permissions required for their responsibilities.

In this lab, I created a security group and configured an access review to evaluate continued membership.

## Security Group

Created the following security group:

**SC500-Security-Access-Review**

The group was used as the target resource for the access review.

## Access Review Configuration

Configured an access review with:

- Resource type: Teams + Groups
- Resource: SC500-Security-Access-Review
- Scope: All users
- Reviewer: SC500 Lab Admin
- Duration: 3 days
- Recurrence: One time
- Auto-apply results: Enabled
- If reviewer does not respond: Remove access
- No sign-in within 30 days: Enabled
- Justification required: Enabled
- Email notifications: Enabled
- Reminders: Enabled

## Review Process

The access review appeared in Microsoft My Access as a pending review.

Microsoft Entra recommended:

**Deny – Inactive user**

This demonstrated Entra ID Governance's ability to provide decision recommendations based on user activity.

After evaluating the account's continued requirement for access, I manually selected:

**Approved**

The automated recommendation was therefore overridden based on the user's legitimate requirement for continued access.

## Security Concepts Demonstrated

This lab demonstrates practical experience with:

- Identity Governance
- Access Reviews
- Group membership governance
- Least privilege
- Periodic access certification
- Automated access recommendations
- Reviewer-based access decisions
- Access removal for non-responsive reviews
- Identity lifecycle governance
- Auditability of access decisions

## Key Takeaway

Access reviews help organizations periodically validate whether users still require access to sensitive resources.

Microsoft Entra can provide automated recommendations based on signals such as inactivity, while designated reviewers retain responsibility for making the final access decision based on business and security requirements.

This provides a balance between automated identity governance and human oversight.
