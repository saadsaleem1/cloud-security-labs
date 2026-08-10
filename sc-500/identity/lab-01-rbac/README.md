# Lab 01 – Azure RBAC & Least Privilege

## Overview

This lab demonstrates the implementation and validation of Azure Role-Based Access Control (RBAC) using the principle of least privilege.

A dedicated Microsoft Entra ID test user was created and assigned the built-in **Reader** role at the resource group scope. The account was then used to validate that read operations were permitted while deployment and write-related operations were denied.

---

## Objectives

- Create a dedicated Microsoft Entra ID test identity
- Implement Azure RBAC at the resource group scope
- Apply the principle of least privilege
- Assign the built-in Reader role
- Validate authorized read access
- Test an unauthorized deployment operation
- Verify Azure RBAC enforcement through an authorization failure

---

## Lab Environment

| Component | Configuration |
|---|---|
| Cloud Platform | Microsoft Azure |
| Identity Platform | Microsoft Entra ID |
| Subscription | SC-500 Security Labs |
| Resource Group | `rg-sc500-rbac-lab-01` |
| Test Identity | SC500 Lab Reader |
| Assigned Role | Reader |
| RBAC Scope | Resource Group |
| Test Resource | Azure Storage Account deployment |

---

## Architecture

The access model used in this lab was:

```text
Microsoft Entra ID
        |
        v
SC500 Lab Reader
        |
        v
Azure RBAC
        |
        |-- Role: Reader
        |-- Scope: Resource Group
        |
        v
rg-sc500-rbac-lab-01
        |
        |-- READ operations: ALLOWED
        |
        |-- WRITE/DEPLOY operations: DENIED
