# Identity & Access Management Labs (AZ-500)

## Lab 1: Entra ID Users, Groups, and RBAC

### Objective
Configure Azure identity and access controls using Microsoft Entra ID and Role-Based Access Control (RBAC).

### Services Used
- Microsoft Entra ID
- Azure RBAC
- Azure Resource Groups

### Steps Performed
1. Created test users in Entra ID
2. Created security groups and assigned users
3. Created a resource group for testing
4. Assigned RBAC roles at the resource group level
5. Validated access permissions

### Security Rationale
RBAC enforces least-privilege access by ensuring users only have permissions required for their role.

### Lessons Learned
- Role scope selection is critical to avoid over-permissioning
- Group-based RBAC scales better than individual assignments
