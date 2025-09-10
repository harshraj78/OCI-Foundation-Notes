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

## 🖼️ Diagram (Text-based)

