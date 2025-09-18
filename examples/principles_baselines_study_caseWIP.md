---

## Case Study for Baseline: Ubuntu Server 24.04 LTS Baseline

**Context**: An organization is deploying multiple Ubuntu Server 24.04 LTS instances for internal applications. A security baseline is required to ensure consistent hardening across all systems.  

### Step 1 – Identify Standards
- CIS Ubuntu Linux 24.04 LTS Benchmark.  
- ANSSI Linux Recommendations.  

### Step 2 – Define Baseline Controls
- **Accounts & Authentication**:  
  - Enforce password complexity (min length, history, lockout).  
  - Disable root login via SSH.  
  - Enforce key-based authentication.  

- **System Services**:  
  - Remove unused packages (e.g., telnet, rsh, ftp).  
  - Disable unnecessary daemons (cups, avahi, etc.).  

- **Logging & Auditing**:  
  - Enable `auditd` and configure log rotation.  
  - Forward logs to a central SIEM.  

- **Updates & Patch Management**:  
  - Enable unattended-upgrades.  
  - Schedule weekly patch verification.  

- **Network Security**:  
  - Configure `ufw` (deny by default, allow required ports).  
  - Enable SSH rate limiting with `fail2ban`.  

### Step 3 – Test in Non-Production
Deploy the baseline on a staging server and validate application compatibility (e.g., web app, DB service).  

### Step 4 – Deployment
Automate baseline with **Ansible playbooks** for consistent rollout across all Ubuntu servers.  

### Step 5 – Monitoring & Maintenance
- Monthly baseline compliance check with **OpenSCAP**.  
- Regular review against updated CIS benchmark releases.  

**Outcome**: All Ubuntu 24.04 servers start from a uniform security posture, aligned with recognized benchmarks, and deviations are continuously monitored.  
