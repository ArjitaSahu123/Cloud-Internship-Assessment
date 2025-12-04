# Cloud Engineer Internship - Technical Assessment
**Candidate:** Arjita Sahu
**Assessment Status:** In Progress

---

## 🔹 Task 1: Networking & Subnetting (AWS VPC Setup)

### **1. Approach & Design**
I designed a custom VPC with a CIDR block of `10.0.0.0/16` to allow for high scalability (65,000+ IPs). The network is segmented into two **Public Subnets** for ingress resources (like Load Balancers) and two **Private Subnets** for secure application workloads. An **Internet Gateway** was attached for public connectivity, while a **NAT Gateway** was deployed in the public subnet to allow private instances to initiate outbound connections for updates without being exposed to the internet. Route tables were explicitly configured to manage traffic flow between these components.

### **2. CIDR Ranges & Reasoning**
| Resource | CIDR Range | Reasoning |
|----------|------------|-----------|
| **VPC** | `10.0.0.0/16` | I chose this range because it provides over 65,000 IP addresses, which is standard industry practice for ensuring future scalability and avoiding IP exhaustion. |
| **Public Subnets** | `10.0.1.0/24` & `10.0.2.0/24` | I used `/24` blocks (256 IPs) because they are easy to manage and provide ample space for typical ingress layers without wasting IP space. |
| **Private Subnets** | `10.0.3.0/24` & `10.0.4.0/24` | Separate `/24` blocks allow for logical segmentation of application tiers and databases, keeping them isolated from direct internet access. |

### **3. AWS Screenshots**

**a) VPC Resource Map**
<img width="1919" height="822" alt="Task1_VPC" src="https://github.com/user-attachments/assets/7688446f-f877-443d-96dd-2e8431850bc6" />


**b) Subnets Configuration**
<img width="1919" height="820" alt="Task1_Subnets" src="https://github.com/user-attachments/assets/6818c87d-5096-4c1e-97fa-1c266e29282f" />

**c) Route Tables**
<img width="1919" height="813" alt="Task1_RouteTables" src="https://github.com/user-attachments/assets/fae2baf3-b5eb-475a-bbe9-7f9aa76b48d3" />


**d) NAT Gateway**
<img width="1919" height="838" alt="Task1_NAT" src="https://github.com/user-attachments/assets/c47f3cae-9139-414e-af8e-4d572124d856" />
