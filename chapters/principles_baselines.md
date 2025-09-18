
# Security Baselines

## What is a Security Baseline?
A **security baseline** is a predefined set of security configurations and controls that establish the minimum required level of protection for a system, application, or environment; and acts as the foundation for secure deployments and ensures consistency across an organization’s infrastructure.

**· REMEMBER**: the baseline depends both on the project and the security level required for its operation, so each one will requiere special attention in orden to achieve better results.

---

## Purpose of Security Baselines
- **Consistency** – ensures that all systems follow the same security requirements. 
- **Compliance** – aligns with standards such as CIS, STIG, NIST, ANSSI or CCN-STIC or specific client requirements.
- **Efficiency** – provides a starting point for hardening activities, avoiding ad-hoc configurations.  
- **Scalability** – simplifies secure deployments in large infrastructures or cloud environments.  

---

## Characteristics of a Good Baseline
- **Auditability** – enables security teams to verify if systems are properly configured.  
- **Standardized** – based on recognized frameworks and adapted to organizational needs.  
- **Tested** – validated for compatibility with operational requirements.  
- **Documented** – includes clear instructions, references, and rationale for each control.  
- **Automated** – implemented with configuration management tools (e.g., Ansible, PowerShell DSC, Group Policy).  
- **Versioned** – tracked over time to reflect updates in technology and threat landscape.  

---

## Examples of Security Baselines
- **Operating Systems**:  
  - Disable unused services.  
  - Specific password complexity and lockout policies.  
  - Enable logging and auditing.  

- **Network Devices**:  
  - Default credentials removed.  
  - Specific ports available..
  - Strong encryption cyphers and protocols.
  
- **Physical security**:  
  - Role definition for personnel.
  - Restrict access to server rooms and rack locks.
  - Ensure redundant power via UPS/generators.

- **Applications**:  
  - Secure default configuration (no anonymous access, no debug endpoints exposed).  
  - Second Factor Authentication requirement.
  - Access control and Role-based access control (RBAC).  
  - Periodicity of patch management.  

---

## Baseline Development Process
1. **Identify Standards** – choose CIS, STIG, or industry-specific references. This may vary depending  on the country where the project its hosted.
2. **Customize Controls** – adapt to organizational context and operational needs.  
3. **Test in Non-Production** – validate against real workloads to ensure no disruptions.  
4. **Deploy at Scale** – enforce baseline across all relevant systems.  
5. **Monitor & Update** – continuously improve and patch deviations.  

---

## Tools for Managing Baselines
- **Microsoft Security Compliance Toolkit (SCT)** – Windows baselines.  
- **Ansible Playbooks / Puppet / Chef** – automation of Linux/Unix baselines.  
- **SCAP (Security Content Automation Protocol)** – standardized security configurations.  
- **Cloud Security Posture Management (CSPM)** – baseline validation in cloud environments.  

---

## Summary
Security baselines represent the **minimum security posture** an organization should enforce.  
They ensure consistency, reduce misconfigurations, and provide a repeatable foundation for hardening, auditing, and compliance activities.
















END OF THE FILE
---
| [📚 Master Index](../MASTER.md) | [➡️ Next](principles_baselines.md)