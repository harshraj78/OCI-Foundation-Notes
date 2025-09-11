
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

-----

# 📝 Principals in OCI IAM

## 🔑 What are Principals?
- A **principal** is an **IAM entity** that can be **authenticated (AUTHn)** and then **authorized (AUTHz)** to access OCI resources.  
- Simply put: **Who can make API calls to OCI services?**  
- Principals can be **users** (human or system) or **resources** (like compute instances, functions).  

---

## 📌 Types of Principals in OCI

### 1. **Users**
- Human or system accounts created in **Identity Domains**  
- Need to **authenticate** with:
  - Username + Password (Console)
  - API Keys (CLI/SDK/Terraform)
  - Auth Tokens (3rd party tools like Docker, DB CLI)

---

### 2. **Instance Principals**
- Allows a **Compute instance** (VM or Bare Metal) to directly call OCI services **without storing credentials**  
- Instance authenticates itself to OCI IAM using its **dynamic identity**  
- Example: A compute VM writes backups directly to **Object Storage**

---

### 3. **Resource Principals**
- Allows **OCI services** (like Functions, OKE, Data Flow) to access other OCI resources  
- Service authenticates using its own principal identity  
- Example: OCI Function writes data to **Autonomous DB** using its resource principal  

---

## 🆔 Lifecycle of a Principal
1. **Principal authenticates (AUTHn)** → proves identity  
2. **Authorization (AUTHz)** → IAM policies decide what actions principal can perform  
3. **Resource Access** → Actions are granted or denied  

---

## 📎 Exam Tips
- **Principal = any entity that can be authenticated in OCI**  
- **Users** are human/system accounts  
- **Instance Principals** = Compute instance → OCI services  
- **Resource Principals** = OCI services → OCI services  
- Always combine with **policies** to allow/deny access  

---

# 📝 Authentication (AUTHn) in OCI

## 🔑 What is Authentication?
- **Authentication (AUTHn)** = Verifying **who you are** before granting access.  
- Ensures that the person or system trying to access OCI is **legitimate**.  
- First step in IAM → *“Are you really who you claim to be?”*  

---



## 📌 Authentication Methods in OCI
1. **Username & Password**
   - Standard login for **OCI Console** access  

2. **Multi-Factor Authentication (MFA)**
   - Extra security layer  
   - User must provide **OTP / mobile app token** along with password  

3. **API Keys**
   - Required for **programmatic access** (CLI / SDK / Terraform)  
   - Users generate public-private key pairs  
   - Public key uploaded to OCI → used for authentication  

4. **Auth Tokens**
   - Used for **3rd party tools (Docker, Terraform, Oracle Database CLI, etc.)**  
   - Generated per user  

5. **Instance Principal**
   - An OCI **Compute instance authenticates directly** to OCI without user credentials  
   - Useful for automation (apps on VM accessing Object Storage, DB, etc.)  

6. **Resource Principal**
   - A **service resource** (like Functions, OKE) authenticates to OCI services  

7. **Federated Authentication**
   - Integrates OCI with external **Identity Providers (IdPs)**  
   - Examples: Microsoft Active Directory, Okta, Azure AD, etc.  

---

## 🏛️ Identity Domains and AUTHn
- Identity Domains manage:
  - **Users and credentials**  
  - **Authentication policies** (SSO, MFA, OAuth, SAML)  
- You can have multiple domains for **different business units/projects**  

---

## ⚡ Exam Tips
- **AUTHn = Who you are** (vs **AUTHz = What you can do**)  
- API keys are for **programmatic access**  
- Instance principals & resource principals → **no need to store credentials**  
- Always enable **MFA** for better security  

---


# 📝 Authorization (AUTHz) in OCI

## 🔑 What is Authorization?
- **Authorization (AUTHz)** = Deciding **what you can do** after you are authenticated  
- Defines **permissions & actions** a user/application can perform on OCI resources  
- Second step in IAM → *“Now that I know who you are, what are you allowed to do?”*  

---

## 📌 How Authorization Works in OCI
1. **Users authenticate (AUTHn)** → Verified identity  
2. **Authorization checks (AUTHz)** → Apply IAM **policies** to decide what actions are allowed  
3. Access is **granted or denied**  

---

## 🏛️ Key Components of AUTHz in OCI
1. **Groups**
   - Users are placed into groups  
   - Policies are assigned to groups (not individual users)  

2. **Policies**
   - Written in **human-readable statements**  
   - Define permissions for groups to access resources in compartments  

   Example:

3. **Compartments**
- Authorization scope → policies always mention a **compartment** (or tenancy root)  
- Organize resources for **access control and billing**  

4. **Actions**
- OCI defines **verbs** in policies:  
  - **Inspect** → view metadata (but not the resource itself)  
  - **Read** → view resource content + metadata  
  - **Use** → read + use resources (but not manage lifecycle)  
  - **Manage** → full control of resource  

---

## ⚡ Exam Tips
- **AUTHn = Who you are**, **AUTHz = What you can do**  
- Policies apply to **groups of users, not individuals**  
- Always mention a **compartment (scope)** in policies  
- **Actions (Inspect, Read, Use, Manage)** are key to understanding OCI policy permissions  

---

# 📝 OCI Authorization – Syntax, Verbs & Aggregated Resource Types

## 🔑 IAM Policy Syntax
OCI **policies** are written in a **human-readable language**.  
**General Syntax:**
Allow <group-name> to <verb> <resource-type> in <location>


- **group-name** → IAM group (e.g., Developers, Admins)  
- **verb** → Level of access (Inspect, Read, Use, Manage)  
- **resource-type** → OCI service or aggregated type (e.g., instance-family, virtual-network-family)  
- **location** → Compartment or tenancy (scope of policy)  

---

## 📌 IAM Verbs (Actions)
Verbs define the **level of access**:

| Verb      | Meaning                                                                 | Example |
|-----------|-------------------------------------------------------------------------|---------|
| **Inspect** | View metadata only (no actual resource details)                        | List instances |
| **Read**    | Inspect + view details (read-only)                                     | View VCN config |
| **Use**     | Read + use the resource (cannot create/delete/manage)                  | Start/stop an instance |
| **Manage**  | Full control (create, update, delete)                                  | Create new instances |

> **Tip:** Always assign the **least privilege** verb needed for a task.

---

## 🏛️ Aggregated Resource Types
Instead of writing a policy for every single resource type, OCI allows **aggregated resource types** to simplify policies.  

### 🔹 Examples
- **`all-resources`** → All OCI resources in the tenancy/compartment  
- **`instance-family`** → All Compute instance-related resources  
- **`virtual-network-family`** → All networking resources (VCN, subnets, gateways, etc.)  
- **`object-family`** → All Object Storage resources  
- **`database-family`** → All Database-related resources  

---

## 🖊️ Example Policies

1. Allow Admins full control on all resources in tenancy:
Allow group Admins to manage all-resources in tenancy

2. Allow Developers to use compute instances in a Dev compartment:
Allow group Developers to use instance-family in compartment Dev


3. Allow NetworkTeam to manage networking resources:
Allow group NetworkTeam to manage virtual-network-family in compartment Network-Comp


---

## ⚡ Exam Tips
- **Policy = group + verb + resource-type + scope**  
- **Verbs (Inspect, Read, Use, Manage)** = permissions hierarchy  
- **Aggregated resource types** save time in writing policies  
- Policies always apply to **groups, not individual users**  
- Scope = **compartment or tenancy**  

---

Policy = Who (Group) + Can Do What (Verb) + On What (Resource Type) + Where (Compartment/Tenancy)

Example:
Allow group DevOpsTeam to manage instance-family in compartment Dev-Comp




---

## 🛠️ **Step-by-Step Creation**

### 1️⃣ Create User
- In Console → **Identity & Security → Identity Domains → Users → Create User**
- Enter:
  - Name (e.g., `alice.john`)
  - Email
  - Assign credentials (console password, API key)

### 2️⃣ Create Group
- **Identity & Security → Groups → Create Group**
- Name it (e.g., `Developers`)
- Add users to the group

### 3️⃣ Create Policy
- **Identity & Security → Policies → Create Policy**
- Example policy to allow Developers to use compute:
Allow group Developers to use instance-family in compartment Dev-Comp


---

## 🖊️ **Example Policies**

1. Allow `Admins` group to manage all resources in tenancy:


Allow group Admins to manage all-resources in tenancy


2. Allow `Developers` group to use instances in `Dev-Compartment`:


Allow group Developers to use instance-family in compartment Dev-Compartment


3. Allow `NetworkTeam` group to manage networking resources:


Allow group NetworkTeam to manage virtual-network-family in compartment Network-Comp


---

## ⚡ **Exam Tips**
- Users = individual identities  
- Groups = collections of users  
- Policies = rules written for groups  
- Always apply **least privilege** principle  
- Users **without groups/policies** have **no access**  
- Policies are **global (tenancy-wide)**, but resources are **regional**

---


# 🏛️ OCI Tenancy, Best Practices & Policies (Foundation Notes)

---

## 🔑 Tenancy Setup
- **Tenancy = Root Compartment** created when you sign up for OCI.
- Represents your **organization’s account** in Oracle Cloud.
- Oracle automatically creates:
  - **Tenancy OCID** (unique identifier)
  - **Root Compartment**
  - **Default Administrator User**
  - **Default Identity Domain** (for managing users/groups)

### ✅ First Steps in Tenancy
1. **Create compartments** for projects, teams, or environments.  
   (e.g., Dev, Test, Prod, Networking, Database)
2. **Create groups** (Admins, Developers, NetworkTeam, DBAdmins).
3. **Add users** in Identity Domain and assign them to groups.
4. **Write IAM policies** to control who can access what.
5. **Set up budgets, cost tracking, tags, and audit logging**.
6. **Create networking (VCN & subnets)** for regions where you’ll run workloads.

---

## 📌 Best Practices
- Don’t put everything in the **Root Compartment** → use sub-compartments.
- Organize compartments by **project, team, or environment**.
- Follow **least privilege** → grant only required permissions.
- Use **naming standards** for compartments, groups, and policies.
- Apply **MFA for users** and enable **federation** if using external IdPs.
- Use **tags** to track billing and ownership of resources.

---

## 📜 Policies
- A **policy** = rule that defines **who can access what** in tenancy/compartments.
- Written in simple **English-like syntax**:
Allow <group-name> to <verb> <resource-type> in <scope>

markdown
Copy code

### 🔑 Verbs
- **inspect** → list only  
- **read** → list + view details  
- **use** → read + work with resources (no delete)  
- **manage** → full access (create, update, delete)  

### 📦 Resource Types (common)
- `all-resources` → all services  
- `instance-family` → compute instances  
- `object-family` → object storage  
- `virtual-network-family` → networking  
- `database-family` → databases  

### 🖊️ Example Policies
1. Admins can manage everything in tenancy:
Allow group Admins to manage all-resources in tenancy

markdown
Copy code
2. Developers can use instances in Dev compartment:
Allow group Developers to use instance-family in compartment Dev-Comp

markdown
Copy code
3. Network team can manage networking in Net-Comp:
Allow group NetworkTeam to manage virtual-network-family in compartment Net-Comp

markdown
Copy code

---

## 📎 Exam Tips
- **Tenancy = Root Compartment** (created at signup).  
- **Users → Groups → Policies → Resources** (flow of access).  
- Policies are **always written for groups**, not individual users.  
- Policies can be scoped to **tenancy or specific compartments**.  
- Always follow **least privilege**.  
