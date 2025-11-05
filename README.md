## **Project Summary: Legacy Application Cloud Migration**

### **1. Primary Objective**  
We needed to **move our suite of apps** from an **aging on-premise server** to a **modern, stable, secure AWS cloud**.  
The urgent trigger? **Decommission the old hardware** and build a **sustainable platform for the future**.

---

### **2. Phase 1 – Containerisation Investigation**  

**Goal:** Modernise the apps by **containerising them** → better portability, consistency, and faster deployments.  

**What we did:**  
- Built a **Linux container proof-of-concept** to test the workflow.  
- Focused on a **Windows container with IIS** to support **mixed .NET Framework & .NET Core runtimes**.  

**Result & Key Lesson:**  
→ **Not feasible for our tight timeline.**  
We hit **major blockers**:  
- **Complex Docker builds**  
- **Dependency conflicts**  
- **Regional settings breaking app functionality**  

*Valuable for future projects, but **not the right path for this urgent migration**.*

---

### **3. Phase 2 – Strategic Pivot to “Lift-and-Shift”**  

**New Goal:** **replicate the existing server in the cloud** (lift-and-shift).  
**Priority:** **Stability & speed** over immediate modernisation.

**What we did – four key workstreams:**

1. **Built the Foundation**  
   - Secure, scalable **AWS infrastructure from scratch**  
   - Best-practice structures  
   - **Single Sign-On (SSO)** for the team  
   - Brand-new **VPC network**

2. **Provisioned the Environment**  
   - **Windows EC2 server** to host the apps  
   - **Managed RDS SQL Server** for the databases

3. **Solved Connectivity**  
   - Set up **secure VPN** for the dev team  
   - Hit **network routing issues** → required **full VPC rebuild** to fix **IP conflict**

4. **Created Data Migration Process**  
   - Backup on-premise DBs → restore to RDS  
   - Fixed a **restore error** caused by **backup file format**

---

### **4. Current Status & Outcomes**  

**✓ A Viable Cloud Environment is LIVE**  
- Stable, secure **dev environment** in AWS that **mirrors the legacy setup**  
- **Foundational infrastructure = complete**

**✓ Applications Migrated**  
- **“PriceApp”** is **deployed, running**
- **“InternalAPI”** is **deployed, running**
- **Proof-of-concept success** for the new architecture

**✓ Clear Path Forward**  
- **Repeatable, validated process** for the remaining databases

**Project Status: In-Progress**  
- Ultimate goal not reached **yet**  
- **Many technical blockers solved**  
- **Straight runway** to migrate the rest and **decommission the old server**

[Mermaid link](https://simplemermaid.com/mermaid-tool.html#diagram=OYJwhgDgFgBAKgEQFA1TAzgVwEakrAIgAUQB7AKwFMBjAFxgGVawRaCU1OBBAbQB5sAPhIBLALYsAnjADy2KnREA3SnwD0QgSDWCAsiLy1KMADKVgYatK4QI6GADMyY2QDsAtCUpiR6Y7VIYLgB1BgBdDlRKVwATJEigmHd3QRgAIQBvIigwPxgARgAuGABhUldmEVdKEF8wWhFymABJVxV0BosG8oBfAG54zixccGgYYhy8ovgoY11SGJrXOu7XGCJ6qHZOIdpJABtjNMcRff3CgGIHGIcAGg6yAGtKS4Bmd-vaJ8p3AHcRGK0KCFABMEAAHglOMdkqkSjwuIpysUTFVMODSuVKtUQOtSCUIjs0DCUjAEAika5imlMKcYpixBBDhjglUYqRfug1M1mgxMRUwFUaoSiWSkqSAKIZNL7UjUZ4gewS1zUUiYCo1SgxHpQtAS8WpABiPAQlCUMGCpBAjwcst+LXQWEo6BFRMN4sYpH2mFWBpghvyPFESnqxjKAqFuIASuZfF9pBKSlGYFodCUQJRQ-SAowchn1hn3DTTvRmhJgM7XTtdah9bCYABxHjpkQNahgfYwGPARquDuMSi0BquYDpTDAF01mBTuukgASCNCMAAZLI+a1VYz6iJsKdW5Iq5w5x6GF6fb2-XPAwBVCB4Rb0uekDprmA5kEABhBIL6qcE4YcEQQDELUgiXX4rUeKpR3+IEYE-b8IinY962aDJTWoXxe2KU1vFAssIHARR232foEmiOIEmaP0ACkskmYwQWKJhwCMHtqHWZRSHoHMAHJUQcWh3DAWJ3AYKAREE3iyISYY8DGCZckY4o4FmGB9EMC8NiBbZRQ6A5jBok4zkuSgADYHFeBw7geUhnjeD5bOeP4ASBUEISnIz6wAaQpVZqVpfZ6RCPlDTVWJt3KP8ADUiBKW4gmoVV1VodAEoYBgZEPNAvNJEw-OwgtSCULCmmVEqyFcECKj-RMQQHEAVFxVcowQPkEHqMBsCU7LUCnOTRkIbzKGkEocjOaIK3sVdT29VZ0F00U0F0ZtxsOEcXi7bxuOMRFqGdF0TzPX1610XgZAgaJYoAOQapqyUoJlSEkUCHCtP9WqIBKEDSBKRPpQ1Tl2pKDrCP1rtWjt1orYprsHCDrRaIh+VtEQ6F6nZbuST05ovetrsDKNIABf1MDOGA4doBHHi27BApiP8mjh+1mmRomNpgEqwBaMACT9GQeBkH1N02pgusOGAbsS-bHQxzgp04IhIYmjacM67q8hjDorWMQ11UpDt9zB7HZvPJp6yIXhWvXVwOhE-aYFve8tT-JxSBcCVwUIg630CYJKGwGAJRiVte2N0kAEVlehzaNytDM6DJTqYCaLWAgzOW0Ajo7cfNyPA2ZxhoMOMTB3SSxHkwOxSgzLM-xzLWvRULbtfzGlgHD1Io0F4X3c2mNLvViW051oqZcnJb5cntAGGjybNpC-l0C9YwGAOi84HESg1VS8OcbNtZ6wYXgyhABP6CIGofEdC819oP9N5AneUYMTAM3pKpGEyzv4B72gReKARMgKh6SmnNJ7S6tRoj7QxhRQYopcqpF0J5P0RAUFH3IrEeBqAZAri7HguAfprzNjfhmCojBmC0EwNNWQvcQIugGLJHA8lCAkAoDQegYsqHoEAR4NhoADqLR2PpCW15jLnAuDcGyXw7IvAuO8V4nxvguUBMCMEkIlpiPrNFHg+QAB0ksRDizDLKTA9JypAXKNVegvhZCQMin2fYGMtGkmCDwEEBjAaKnoDYJkaMHEwF4qIfavjeLqQMKxUCDBMAg0dA4Mm+wDxThcakAAGjwV4BiuClEOCwdYmx-RWl+CwD+So7bYH2L4WYMQqwUSAA)

```mermaid
graph TD
    subgraph "Project Start"
        A[<b>Primary Objective</b><br/>Migrate Legacy Apps from On-Premise to AWS]
    end

    A --> B{Phase 1: Containerisation Investigation};

    subgraph "Phase 1: The Modernisation Path"
        style B fill:#fdf,stroke:#333,stroke-width:2px
        B --> C[Action: Linux Container PoC]
        B --> D[Action: Build Complex Windows/IIS Container]
        D --> E{Blockers Encountered}
        E --> F[Dev Workflow Issues]
        F -- Solution --> F1[Private Container Registry ECR <br/>Created to Share Pre-Built Images]
        
        E --> G[Critical Regional Setting Bugs]
        
        E --> H[AWS & OS Incompatibility]
        H -- Solution --> H1[Upgraded Host OS to 2022;<br/>Confirmed AWS working with 2022]

        H --> I{Decision: Deemed Impractical};
    end

    I --> J{Phase 2: Strategic Pivot to 'Lift-and-Shift'};

    subgraph "Phase 2: The Migration Path"
        style J fill:#e6f3ff,stroke:#333,stroke-width:2px
        J --> K[Action: Build AWS Foundation<br/>VPC, Accounts, SSO]
        J --> L[Action: Provision Environment<br/>EC2 Server & RDS Database]
        
        subgraph "Key Challenges & Solutions"
            M[Challenge: Remote Access] -- Solution --> MA[OpenVPN Server Deployed for<br/>RDP, DB, and File Access] --> N[Challenge: Network IP Conflict]
            N -- Solution --> N1[Rapid Full Network Rebuild<br/>on New IP Range via IaC] --> O[Outcome: Stable VPN Access]
            
            P[Challenge: Database Restore Functionality] -- Solution --> PA[RDS Instance Upgraded<br/>from Express to Web Edition] --> Q[Challenge: Incorrect Data on Restore]
            Q -- Solution --> Q1[New Single-Set Backups Created<br/>to Resolve Restore Bug] --> R[Outcome: Repeatable Restore Process]
            
            S[Challenge: AWS Console Session Timeouts] -- Solution --> SA[Correct Permission Set<br/>Timeout Configured in SSO] --> T[Outcome: Improved Dev Experience]
        end

        J --> M
        J --> P
        J --> S
    end

    O & R & T --> U[Current Status & Outcomes];

    subgraph "Project Status: In-Progress"
        style U fill:#dff,stroke:#333,stroke-width:2px
        U --> V[1. Viable Cloud Environment is Operational]
        U --> W[2. First Application 'PriceApp' Migrated Successfully]
        U --> X[3. A Clear Path Forward is Established]
    end
```
