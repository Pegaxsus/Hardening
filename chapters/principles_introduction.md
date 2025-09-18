# Introduction to Hardening

## What is Hardening?
Hardening refers to the process of securing a system by reducing its attack surface, eliminating unnecessary components, and enforcing security best practices.  

** · TARGET**: minimize vulnerabilities that could be exploited by malicious actors, while maintaining operational efficiency.  

**· REMEMBER**: attackers only need one opportunity, defensers must be always on guard, the required effort is asymetric.

---

## Why is Hardening Important?
- **Attack Surface Reduction**: fewer services, ports, and features available for exploitation.  
- **Defense in Depth**: hardening process complements other security layers such as monitoring, intrusion detection, and patching. All of them work together to increase protection.  
- **Compliance**: there are many regulatory frameworks (ISO 27001, NIST, PCI-DSS, GDPR) require or recommend baseline security hardening.  
- **Resilience**: hardened systems are more resistant to both external and insider threats.  
- **Performance**: take into account that cybersecurity tries to protect a system, but its measures must not left the system unusable or unstable.

---

## Key Principles
1. **Least Privilege Principle:** users, applications, and processes should run with the minimum rights necessary for its function.
2. **Disable Unnecessary Components:** remove or disable services, accounts, or features not required.  
3. **Secure Defaults:** configurations should start from a secure baseline instead of permissive settings.  
4. **Regular Updates:** apply patches and updates to reduce known vulnerabilities by keeping systems and software up-to-date.
5. **Audit & Logging:** enable monitoring to detect misconfigurations or malicious activity.  
6. **Consistency:** apply the same hardening policies across environments for uniform protection.  

---

## Scope of Hardening
Hardening applies to multiple layers of technology:
- **Infrastucture and hardware** – Securing and protecting physical assets and their access.  
- **Operating Systems** – Linux, Windows, macOS.  
- **Networks** – routers, firewalls, switches.  
- **Applications** – databases, web servers, SAP, mail systems.  
- **Cloud & Virtualization** – cloud platforms, containers, hypervisors.  
- **Endpoints & IoT** – desktops, mobile devices, IoT/OT environments.  

---

## Relation to Standards
Hardening is commonly guided by established standards and best practices:
-  **NIST SP 800-series** – U.S. security standards and recommendations.  
- **STIGs** – Security Technical Implementation Guides (DoD).  
- **CIS Benchmarks** – secure configuration guidelines.  
- **ANSSI Guidelines** – French National Cybersecurity Agency.  
- **CCN-STIC Guides** – Spanish National Cryptologic Center.  

---

## Summary
Hardening is the fundamental step in defensive cybersecurity and must be applied from the conception of the system, however, sometimes it must be applied to existing systems, this requires prior recognition before applying the necessary measures to reduce the impact of its application.
By systematically reducing unnecessary exposure, enforcing secure configurations, and validating against recognized standards, organizations can significantly reduce their risk posture and increase system resilience.

Think of hardening as a permanent invisible shield.

END OF THE FILE
---
| [📚 Master Index](../MASTER.md) | [➡️ Next](principles_baselines.md)
