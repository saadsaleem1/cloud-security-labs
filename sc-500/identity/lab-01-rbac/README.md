# Lab 01 – Azure RBAC & Least Privilege

## Overview

This lab demonstrates the implementation and validation of Azure Role-Based Access Control (RBAC) using the principle of least privilege.

A dedicated Microsoft Entra ID test user was created and assigned the built-in **Reader** role at the resource group scope. The account was then used to validate that read operations were permitted while deployment and write-related operations were denied.

## Objectives

- Create a dedicated Microsoft Entra ID test identity
- Implement Azure RBAC at the resource group scope
- Apply the principle of least privilege
- Assign the built-in Reader role
- Validate authorized read access
- Test an unauthorized deployment operation
- Verify Azure RBAC enforcement through an authorization failure

## Lab Environment

| Component | Configuration |
|---|---|
| Cloud Platform | Microsoft Azure |
| Identity Platform | Microsoft Entra ID |
| Subscription | SC-500 Security Labs |
| Resource Group | `rg-sc500-rbac-lab-01` |
| Test Identity | SC500 Lab Reader |
| RBAC Role | Reader |
| Assignment Scope | Resource Group |
| Region | East US |

## Architecture

The RBAC configuration implemented in this lab follows the model:

`Security Principal + Role Definition + Scope = Role Assignment`

For this implementation:

`SC500 Lab Reader + Reader + rg-sc500-rbac-lab-01 = Least-Privilege Role Assignment`

The Reader role was intentionally scoped only to the lab resource group rather than the entire Azure subscription.

## Implementation

### 1. Created the Lab Resource Group

A dedicated resource group was created to isolate resources and RBAC testing:

`rg-sc500-rbac-lab-01`

### 2. Created a Microsoft Entra ID Test User

A dedicated test identity named **SC500 Lab Reader** was created in Microsoft Entra ID.

Using a separate identity allowed RBAC permissions to be tested independently from the subscription Owner account.

### 3. Assigned the Reader Role

The built-in Azure **Reader** role was assigned to the SC500 Lab Reader identity at the resource group scope.

The Reader role permits the identity to view resources and configuration information without granting permissions to modify or deploy resources.

### 4. Validated Read Access

The SC500 Lab Reader account successfully authenticated to Azure and accessed the `rg-sc500-rbac-lab-01` resource group.

This confirmed that the Reader role provided the expected read access.

### 5. Tested a Restricted Operation

While authenticated as SC500 Lab Reader, an Azure Storage Account deployment was attempted within the resource group.

Azure rejected the deployment validation because the Reader identity did not have authorization to perform:

`Microsoft.Resources/deployments/validate/action`

Azure returned:

`AuthorizationFailed`

This demonstrated that the RBAC configuration successfully prevented the Reader identity from performing an operation outside its assigned permissions.

## Security Outcome

The lab successfully demonstrated least-privilege access:

| Action | Result |
|---|---|
| Authenticate to Azure | Allowed |
| View assigned resource group | Allowed |
| View resource information | Allowed |
| Validate resource deployment | Denied |
| Deploy/modify resources | Denied |

The identity received sufficient access to perform its intended read-only function without receiving unnecessary administrative privileges.

## Security Concepts Demonstrated

- Azure Role-Based Access Control (RBAC)
- Microsoft Entra ID identities
- Least privilege
- Role assignments
- Resource-level scoping
- Authorization enforcement
- Separation of administrative and standard identities
- Azure Resource Manager authorization

## Evidence

Screenshots documenting the configuration and validation are stored in the `screenshots` directory.

- `01-rbac-role-assignment.png`
- `02-reader-access-success.png`
- `03-reader-write-denied.png`

## Key Takeaways

Azure RBAC permissions are determined by the combination of a security principal, role definition, and assignment scope.

Scoping the Reader role to a specific resource group limited the test identity's access while still allowing it to perform its required read operations.

Testing the account directly confirmed that Azure enforced the configured authorization boundary by permitting read access while denying deployment operations.

---

**Certification Track:** Microsoft SC-500 – Cloud and AI Security Engineer Associate

**Focus Area:** Identity, Access Control, and Cloud Security
