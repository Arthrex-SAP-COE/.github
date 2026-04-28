# Arthrex SAP COE – GitHub Organization

Welcome to the **Arthrex SAP COE GitHub Organization**.

This space supports application lifecycle management (ALM), automation, and cloud-native development across SAP and non-SAP solutions, aligned with **ALM Engineering (Release Management)** governance.

---

## CI/CD Workflow (Visual)

```mermaid
flowchart LR
    A[Developer - BTP Dev Space] -->|cf push| B[Prototype / Test in Dev]
    B --> C{Ready for Promotion?}
    C -->|No| A
    C -->|Yes| D[Push Code to GitHub Repo]
    D --> E[Create Feature in SAP Cloud ALM]
    E --> F[ALM Engineering Review]
    F --> G[Deploy to Test Space]
    G --> H[Validation / Testing]
    H --> I{Approved?}
    I -->|No| A
    I -->|Yes| J[Deploy to Production]
```

---

## Repository Overview

### BTP_CloudFoundry_Dev
Primary repository for Cloud Foundry applications.

### ABAPGit_Backups
Used for ABAPGit version control and backups.

### GRM-Python_Projects
Internal Python tools and automation apps (non-SAP).

---

## gCTS Flow

```mermaid
flowchart LR
    A[ABAP Dev] --> B[gCTS Commit]
    B --> C[GitHub Repo]
    C --> D[Transport Trigger]
    D --> E[Import Target System]
    E --> F[Validation]
```

---

## Workflow Summary

1. Develop in Dev Space  
2. Push to GitHub  
3. Create Feature in cALM  
4. ALM Engineering promotes  

---

## Notes

If it needs to move forward → it belongs in GitHub.
