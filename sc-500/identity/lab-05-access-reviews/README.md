# SC-500 Lab 5: Microsoft Entra ID Access Reviews

## Objective

Configure and perform a Microsoft Entra ID Access Review to evaluate whether a user should retain membership in a security group.

This lab demonstrates identity governance, access certification, automated access recommendations, reviewer-based decisions, and access lifecycle management using Microsoft Entra ID Governance.

---

## Technologies Used

- Microsoft Azure
- Microsoft Entra ID
- Microsoft Entra ID Governance
- Microsoft Entra Access Reviews
- Microsoft My Access
- Microsoft Entra Security Groups

---

## Scenario

Organizations should periodically review user access to ensure that users retain only the permissions necessary to perform their responsibilities.

For this lab, I created a dedicated security group and configured an access review to determine whether a user should continue to have access.

The review also demonstrated how Microsoft Entra can generate automated recommendations based on identity activity while allowing a human reviewer to make the final access decision.

---

## Step 1 – Create Security Group

Created a Microsoft Entra security group:

**Group Name:** `SC500-Security-Access-Review`

**Group Type:** Security

**Membership Type:** Assigned

The SC500 Lab Admin account was added as a member of the group.

This group served as the resource being evaluated during the access review.

---

## Step 2 – Configure Access Review

Navigated to:

Microsoft Entra ID → Identity Governance → Access Reviews

Created an access review for:

**Resource:** `SC500-Security-Access-Review`

Configuration included:

- Review type: Teams + Groups
- Review scope: All users
- Reviewer: SC500 Lab Admin
- Duration: 3 days
- Recurrence: One time
- Auto-apply results to resource: Enabled
- If reviewers do not respond: Remove access
- Inactivity decision helper: Enabled
- Justification required: Enabled
- Email notifications: Enabled
- Reminders: Enabled

---

## Step 3 – Validate Access Review

After creating the review, I verified that the access review became active.

The SC500 Lab Admin account appeared as the identity requiring review.

The review was then accessed through Microsoft My Access.

---

## Step 4 – Review Automated Recommendation

Microsoft Entra evaluated the account and generated the following recommendation:

**Recommendation: Deny**

**Reason: Inactive user**

This demonstrated the use of identity activity signals to assist reviewers in determining whether access should continue.

---

## Step 5 – Perform Access Certification Decision

After evaluating the account's continued requirement for access, I manually selected:

**Decision: Approved**

The automated Deny recommendation was therefore overridden by the reviewer because continued access was required for security administration and Identity Governance lab activities.

This demonstrates that automated recommendations can assist access governance decisions while human reviewers retain responsibility for the final access certification decision.

---

## Security Concepts Demonstrated

This lab provided hands-on experience with:

- Microsoft Entra Identity Governance
- Access Reviews
- Access certification
- Security group governance
- Identity lifecycle management
- Least privilege
- Automated access recommendations
- Inactivity-based access evaluation
- Reviewer-based access decisions
- Automated access remediation
- Access review notifications and reminders
- Auditability of access decisions

---

## Security Engineering Takeaway

Access Reviews help organizations continuously validate whether users still require access to resources.

Rather than allowing permissions to remain indefinitely, organizations can periodically evaluate access based on identity activity, business requirements, and security policies.

Microsoft Entra can provide automated recommendations based on signals such as inactivity while designated reviewers make the final decision.

This supports least privilege and reduces the risk of unnecessary or stale access remaining within an environment.

---

## Evidence

Screenshots included in this repository demonstrate:

1. Creation of the security group
2. Access review configuration
3. Active access review
4. Reviewer assignment
5. Access review appearing in Microsoft My Access
6. Microsoft Entra inactivity-based Deny recommendation
7. Final Approved access certification decision
