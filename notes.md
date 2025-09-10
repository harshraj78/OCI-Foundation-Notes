
# MODULE 2 - INTRODUCTION

# 📝 OCI Introduction & Architecture 

## 🔑 What is OCI?
- **Oracle Cloud Infrastructure (OCI)** = Oracle’s cloud platform  
- Provides **IaaS, PaaS, SaaS, and DaaS**  
- Built for **high performance, security, and enterprise workloads**  

---

## 🏛️ OCI Global Architecture

### 1. Regions
- A **localized geographic area** (e.g., `ap-mumbai-1`, `us-ashburn-1`)  
- Each region contains **Availability Domains (ADs)**  
- You subscribe to a region to use OCI services  

---

### 2. Availability Domains (ADs)
- **Independent data centers** within a region  
- Each AD has **its own power, cooling, and network**  
- Failure in one AD **doesn’t affect others** → ensures **high availability**  

---

### 3. Fault Domains (FDs)
- **Logical grouping of hardware** inside an AD  
- Protects against **hardware failure within AD**  
- ✅ Best practice: distribute compute/DB across multiple FDs  

---

### 4. Region Pairs
- Regions paired for **disaster recovery & data sovereignty**  
- Example: `us-ashburn-1` ↔ `us-phoenix-1`  

---

### 5. Compartments
- **Logical partition** of resources in a tenancy  
- Used for **organization, access control, and billing separation**  

---

### 6. Tenancy
- **Root compartment** of OCI  
- Represents your **organization account** in OCI  
- All compartments, users, policies, resources exist **inside a tenancy**  

---

## ⚡ Core OCI Architecture Layers
1. **Identity & Security** → IAM, Compartments, Policies  
2. **Networking** → VCN, Subnets, Gateways, Load Balancers  
3. **Compute** → Bare metal, VMs, Containers, Functions  
4. **Storage & Databases** → Block, Object, File, Autonomous DB  
5. **Observability & Management** → Monitoring, Logging, Notifications  

---

## 📎 Exam Tips
> ⚡ **Region** = Geographical area  
> 🏛️ **AD** = Data center  
> 🖥️ **FD** = Hardware grouping  
> 🏠 **Tenancy** = Root container for everything  
> 📦 **Compartments** = Logical resource grouping (IAM + billing)  
> 🆔 **OCID** = Unique identifier for every resource  

---

## 🖼️ Diagram
Tenancy
 └── Region (Mumbai)
      ├── AD1
      │    ├── FD1
      │    ├── FD2
      │    └── FD3
      └── AD2
           ├── FD1
           ├── FD2
           └── FD3

---------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------

# MODULE 3 - IDENTITY & ACCESS MANAGEMENT

----------1.
# 📝 OCI IAM Introduction

## 🔑 What is IAM?
- **IAM (Identity and Access Management)** = Service in OCI to **control who can access which resources** and **what actions they can perform**  
- Ensures **security, governance, and compliance** in cloud environments  
- Works across the entire **tenancy**

---

## 📌 Key Components
1. **Users**  
   - Individual accounts for people or applications  
   - Each user has a **unique OCID** and login credentials  

2. **Groups**  
   - Logical collection of users  
   - Simplifies **policy assignment**  
   - Example: Admins, Developers, Finance  

3. **Policies**  
   - Define **permissions** for groups to access resources  
   - Written in **human-readable statements**  
   - Example:  
     ```
     Allow group Admins to manage all-resources in tenancy
     ```

4. **Compartments**  
   - Logical partition of resources  
   - Used for **access control, organization, and billing separation**  
   - Policies often applied **per compartment**  

5. **Identity Domains**  
   - **Authentication boundary** inside tenancy  
   - Manages users, groups, apps, and authentication settings  
   - Can be **federated** with external IdPs (AD, Azure AD, Okta)

---

## ⚡ IAM Workflow
1. Create **Users**  
2. Group users into **Groups**  
3. Define **Policies** granting groups access to **resources** in **Compartments**  
4. Use **Identity Domains** for authentication and SSO  

---

## 🔐 Best Practices
- Use **groups instead of assigning policies to individual users**  
- Separate resources into **compartments for dev/test/prod**  
- Enable **MFA (Multi-Factor Authentication)** for all users  
- Use **least privilege principle**: grant only required permissions  

---

## 📎 Exam Tips
- IAM = **who can do what, where** in OCI  
- Policies always apply to **groups, not users**  
- Compartments help in **organizing resources + applying policies**  
- **OCID** = unique identifier for all IAM entities  

---

# 📝 OCI Identity Concepts & Resource Identification

## 🔑 1. OCI Identity Concepts (Overview)
- OCI **Identity** defines **who you are and what you can access** in OCI  
- Enables **authentication, authorization, and governance**  
- Managed via **IAM (Identity and Access Management)**  
- Key entities:
  - **Tenancy** → Root container for all resources  
  - **Users** → Individual accounts  
  - **Groups** → Collection of users  
  - **Policies** → Permissions for groups  
  - **Compartments** → Logical partitions for resources  
  - **Identity Domains** → Authentication and login boundaries  

---

## 🏛️ 2. Identity Domains (Overview + Examples)
- **Definition:** Security and authentication boundary inside tenancy  
- **Purpose:** Manage users, groups, applications, login & authentication (SSO, MFA)  
- **Examples:**
  - Default domain → Created automatically in tenancy  
  - Custom domain → For separate business units, projects, or environments  
  - Federated domain → Integrated with external IdPs (AD, Okta, Azure AD)  

> Example scenario:  
> - **Company X** has:
>   - Identity Domain 1 → Development team  
>   - Identity Domain 2 → Production team  
> - Both under the same tenancy but isolated authentication

---

## 📦 3. Resource Cloud Objects (Overview + Examples)
- OCI resources are **cloud objects** (Compute, Storage, Database, Networking)  
- Examples:
  - **Compute Instance** → `ocid1.instance.oc1.phx.abc123uniqueid`  
  - **VCN (Virtual Cloud Network)** → `ocid1.vcn.oc1.iad.efg456uniqueid`  
  - **Object Storage Bucket** → `ocid1.bucket.oc1.ap-mumbai.xyz789uniqueid`  

---

## 🆔 4. How to Identify an OCI Resource (OCID)
- Every OCI resource has a **unique Oracle-assigned identifier (OCID)**  
- **Format of OCID:**  
ocid1.<resource-type>.<realm>.<region>.<future-use>.<unique-id>

---


### 🔹 Example OCIDs
| Resource Type          | Example OCID |
|------------------------|--------------|
| Compute Instance       | ocid1.instance.oc1.phx.abcd1234 |
| Virtual Cloud Network  | ocid1.vcn.oc1.iad.efgh5678      |
| Object Storage Bucket  | ocid1.bucket.oc1.ap-mumbai.xyza9876 |

- **Explanation of Parts:**
  1. `ocid1` → Prefix for all OCIDs  
  2. `<resource-type>` → Type of OCI resource (instance, vcn, bucket, etc.)  
  3. `<realm>` → OCI realm (oc1, oc2, etc.)  
  4. `<region>` → Region code (phx, iad, ap-mumbai, etc.)  
  5. `<future-use>` → Reserved for future use (currently mostly `-`)  
  6. `<unique-id>` → Globally unique identifier for the resource  

---

## ⚡ Key Takeaways
- **Identity concepts** = IAM entities controlling access  
- **Identity domains** = Authentication boundaries inside tenancy  
- **Resource cloud objects** = OCI services/resources (Compute, Storage, Networking, etc.)  
- **OCID** = Unique Oracle-assigned ID, used to identify resources programmatically and securely  

-----------2.

# 📝 OCI IAM – Compartments

## 🔑 Definition
- A **compartment** is a **logical container** used to **organize and isolate cloud resources**  
- Think of it like **folders for your cloud resources**  

---

## 📌 Key Points
- Resources (Compute, DB, VCN, Storage, etc.) are **created inside compartments**  
- Compartment = unit of **access control, organization, and billing**  
- A compartment can contain **nested compartments**  
- **Policies** define who can access resources in a compartment  
- Resources in a compartment can **interact across compartments** (if policy allows)  
- Compartments are **regional in scope** (resources exist in specific regions)  

---

## ⚡ Best Practices
- Create compartments for **projects, teams, or environments** (Dev, Test, Prod)  
- Use **least privilege policies** linked to compartments  
- Don’t put everything in the **root compartment** – use sub-compartments for organization  
- Use compartments to **separate billing and access clearly**  

---

## 📎 Exam Tips
- IAM **users, groups, policies** are global, but resources live in **compartments (regional)**  
- Policies always **mention a compartment (scope)**  
- **Root Compartment** = created by default for each tenancy  

## 🖼️ Example Policy
- Allow group DevOpsTeam to manage instance-family in compartment Dev-Compartment
