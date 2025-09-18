# 📖 Security Standards & Frameworks

## Introduction
Hardening activities are not an isolated process, the key is to align and adhere to international **recognized security standards and frameworks** to ensure consistency, compliance, and industry acceptance.  
These frameworks provide structured guidance for configuration, auditing, and long-term security management.  
One of the advantages of using a recognized framework means its easy to achieve compatibility between different systems, allowing easier information exchange or interaction.

---

## Non-Governmental / Independent Frameworks

### CIS Benchmarks
- Published by the Center for Internet Security.  
- Provide detailed configuration recommendations for operating systems, applications, and cloud platforms.  
- Widely used as a baseline for compliance and technical audits.  

### ISO/IEC 27001 & 27002
- International standards for Information Security Management Systems (ISMS).  
- Provide guidelines for establishing, implementing, and continuously improving security controls.  
- Broad coverage: governance, risk management, and technical measures.  

### PCI DSS (Payment Card Industry Data Security Standard)
- Global standard for securing environments that handle credit card transactions.  
- Strong emphasis on hardening servers, encryption, and access control.  
- Widely adopted in the financial and e-commerce sectors.  

### OWASP (Open Web Application Security Project)
- Community-driven framework focused on application security.  
- Includes the OWASP Top 10, ASVS, and best practices for secure development.  
- Complements system-level hardening with application-layer controls.  

### MITRE ATT&CK
- Knowledge base of adversary tactics, techniques, and procedures (TTPs).  
- Used to assess security posture and validate hardening against real-world attack patterns.  
- Helps organizations prioritize defensive measures.  

### CSA (Cloud Security Alliance) Controls
- Best practices for cloud security across providers (AWS, Azure, GCP).  
- Includes Cloud Controls Matrix (CCM) and guidelines for SaaS, PaaS, and IaaS.  
- Helps organizations establish cloud-specific baselines.  

### PCI DSS (Payment Card Industry Data Security Standard)
- Global standard for securing environments that handle credit card transactions.  
- Strong emphasis on hardening servers, encryption, and access control.  
- Widely adopted in the financial and e-commerce sectors.  

---
## Governmental Frameworks

### STIG (Security Technical Implementation Guides) \[US]
- Developed by the U.S. Department of Defense (DoD).  
- Prescriptive hardening guides for operating systems, databases, and applications.  
- Mandatory in U.S. federal and military environments.  

### ANSSI Guidelines \[FRANCE]
- Released by the French National Cybersecurity Agency.  
- Provide security recommendations for operating systems, networks, and applications.  
- Focus on resilience and secure architecture in both public and private sectors.  

### CCN-STIC Guides \[SPAIN]
- Published by the Spanish National Cryptologic Center.  
- Security guidance for public administration and critical infrastructure in Spain.  
- Cover operating systems, networks, cryptography, and incident response.  

### NIST SP 800-Series \[US]
- Standards from the U.S. National Institute of Standards and Technology.  
- Provide frameworks for security controls, risk management, and compliance (e.g., SP 800-53, SP 800-171).  
- Often used in regulated industries such as finance, healthcare, and government.  

### IT-Grundschutz (BSI, Germany) \[GERMANY]
- Framework developed by the German Federal Office for Information Security.  
- Provides catalogs of security measures for IT systems, applications, and networks.  - Often used in European critical infrastructure.  

---

## Comparison and Usage
In practice, organizations rarely rely on a single framework, often they are combined to achieve higher levels of protection.
- **Governmental frameworks** → often mandatory in public sector, military, or regulated industries; provide strict and detailed requirements, its typical usages are:  
     - Defense projects → STIG.  
     - European public administration → ANSSI (France), CCN-STIC (Spain), IT-Grundschutz (Germany).  
     - U.S. government contractors → NIST SP 800-series.   
 - **Independent frameworks** → more flexible, widely adopted across private industries, and adaptable to multiple contexts.:
     - Enterprises adopting **CIS Benchmarks** as practical starting points.  
     - Financial institutions → **PCI DSS** for cardholder data.  
     - Cloud environments → **CSA CCM** for SaaS/PaaS/IaaS providers.  
     - Application development/security → **OWASP Top 10** and **ASVS**.  


---

## How to Apply Frameworks in Hardening
Applying security frameworks to hardening activities requires more than simply reading guidelines.  
It's a structured process that ensures configurations are **relevant, consistent, and sustainable** across the organization.  

### 1. Select the Relevant Framework
- Identify which frameworks apply to your **industry, geography, and regulatory requirements**.  
- *Consider organizational maturity: CIS Benchmarks are easier for quick implementation, while ISO/IEC 27001 or NIST SP 800-series require more governance and planning.*  

### 2. Map Controls to Your Environment
- Translate framework controls into **specific technical requirements** for your systems, the focus here is to match the framework requisite with an appropiate for or method to achieve the goal
  - Example: CIS Linux Benchmark specifies “disable unused services”, then we can disable `telnet`, `rsh`, etc, if they're not needed.
  - Example: PCI DSS specifies to “encrypt transmissions”, we can opt to enforce with TLS 1.2/1.3 for all interneet-based services.  
- Create a **control matrix** mapping framework requirements to infrastructure components, i'll be easier to create a proper documentation, allowing easy fixes in case of error, quicker policy updates, or fast new-employee integration (not requiring months to understand the methodology). 

### 3. Customize for Business Needs
- By selecting a framework ***doesn't mean to follow every recommendation**, not all of them may apply directly.  
- Adjust configurations to balance **security and functionality**: 
  - If appling a recommendation or policy ruins your core business there is no point in hardening it, rememeber it must maintain the performance.
  - Example: strict password policies in STIG may need relaxation for service accounts but not to an administrative level.
  - Example: disabling certain ports may break critical business workflows if not carefully validated.  
- Document accepted deviations with **risk justification**.  

### 4. Implement with Automation
- Use **configuration management and automation tools** to deploy controls consistently:  
  - Ansible, Puppet, Chef (Linux/Unix).  
  - Group Policy Objects (Windows or in Active Directoy).  
  - Terraform and CSPM tools for cloud platforms.  
- Store baseline configurations in version control (Git) to enable auditing and rollback.  

### 5. Validate & Audit WIP
- Perform regular compliance checks with automated tools:  
  - **SCAP** (Security Content Automation Protocol).  
  - **OpenSCAP**, **Lynis**, **Microsoft SCT**, or vendor-specific compliance scanners.  
- Conduct manual reviews for critical systems.  
- Document findings and track remediation.  

### 6. Maintain & Update WIP
- Frameworks evolve as threats and technologies change.  
- Establish a **review cycle** (quarterly, bi-annual) to update baselines with new framework versions.  
- Train administrators and security teams on updates to ensure adoption.  
- Monitor deviations with continuous compliance tools (e.g., CIS-CAT, cloud CSPM).  

## Summary
Security frameworks serve as **the foundation for hardening activities**.  
By aligning with recognized standards organizations ensure consistency, compliance, and long-term security maturity.

---
END OF THE FILE
---
[⬅️ Previous](principles_baselines.md) | [📚 Master Index](../MASTER.md) | [➡️ Next](principles_documentation.md)
