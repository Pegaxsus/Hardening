# Linux

## 1. Using sudo Instead of Root on Ubuntu Server

### Steps to Use sudo Instead of Root

1. **Create a New User:**
   Create a non-root user account if you don’t already have one.

> sudo adduser newuser

2. Grant sudo Privileges: Add the new user to the sudo group so they can execute administrative commands.

> sudo usermod -aG sudo newuser

Alternatively, you can edit the sudoers file using visudo for more granular control.

3. Log in as the New User: Log out from the root account and log in with your new user. Use sudo for administrative tasks, for example:
   
   > sudo apt update

4. Disable Root SSH Login (Optional for Additional Hardening): To further harden your system, edit the SSH configuration file:
   
   > sudo nano /etc/ssh/sshd_config

Set:

> PermitRootLogin no
> Restart SSH:
> sudo systemctl restart ssh

### Why This is Important for Hardening

- Principle of Least Privilege:
  Using sudo minimizes risk by granting administrative privileges only when needed instead of operating as root all the time.

- Audit and Accountability:
  Commands executed with sudo are logged, providing an audit trail that helps track actions and detect misuse.

- Reduced Attack Surface:
  By not logging in as root, you lower the chances of an attacker gaining full system access if credentials are compromised.

- Enhanced Security Practices:
  Using sudo enforces best practices by separating daily user tasks from administrative duties, reducing the risk of accidental or malicious changes.

## 2. Implement AppArmor or SELinux (Default in Ubuntu)

Ubuntu uses **AppArmor** by default as its Mandatory Access Control (MAC) system to confine programs and restrict their capabilities based on defined profiles. While **SELinux** is an alternative MAC system (commonly used on Red Hat-based systems), this guide focuses on AppArmor since it's the default in Ubuntu. Both systems help harden the server by reducing the potential impact of a compromised application.

### Check AppArmor Status

To verify that AppArmor is active and view the loaded profiles, run:

> sudo apparmor_status

### Enforce an Existing Profile

AppArmor profiles are stored in /etc/apparmor.d/. To enforce a profile (i.e., set it to enforce mode), use:

> sudo aa-enforce /etc/apparmor.d/usr.bin.your_application


## 3. Blocking Execution of Unauthorized Binaries on Ubuntu Server

### Overview

Preventing unauthorized binaries from executing is a crucial security measure to protect your Ubuntu server from potential threats, such as malware or unauthorized software. While `/etc/security/limits.conf` is primarily used for defining resource limits (e.g., maximum number of open files, process limits) for users and groups, it is not designed to control the execution of binaries. Instead, other methods are more appropriate for restricting binary execution.

### Recommended Methods to Block Unauthorized Binaries

### 1. Remove Execute Permissions

By removing execute permissions from specific binaries, you can prevent users from running them:


sudo chmod -x /path/to/binary
Note: Ensure that removing execute permissions does not affect system functionality.

### 2. Use AppArmor or SELinux
Implement Mandatory Access Control (MAC) systems like AppArmor (default in Ubuntu) or SELinux to define and enforce security policies that restrict binary execution.

AppArmor Example:
Install AppArmor Utilities:
> sudo apt-get install apparmor-utils

Set a Binary to Complain Mode:
> sudo aa-complain /path/to/binary

Set a Binary to Enforce Mode:
> sudo aa-enforce /path/to/binary

Note: AppArmor profiles can be customized to allow or deny execution of specific binaries.

### 3. Mount Filesystems with noexec Option
Mounting filesystems with the noexec option prevents the execution of binaries from those filesystems:

Edit /etc/fstab:

Add or modify the entry for the target filesystem:

fstab
Copiar
Editar
/dev/sdX /mnt/point ext4 defaults,noexec 0 2
Remount the Filesystem:

bash
Copiar
Editar
sudo mount -o remount,noexec /mnt/point
Note: This method is effective for directories where users have write access, such as /tmp, to prevent execution of unauthorized scripts or binaries.

Why Blocking Unauthorized Binaries is Important for Hardening
Prevents Execution of Malicious Software:

Restricting binary execution reduces the risk of malware running on your system.

Enforces Administrative Control:

Ensures that only approved software is executed, maintaining system integrity.

Mitigates User Errors:

Prevents users from accidentally running harmful or untested programs.

Implementing these measures enhances the security posture of your Ubuntu server by controlling the execution of binaries and reducing potential attack vectors.

makefile
Copiar
Editar
::contentReference[oaicite:0]{index=0}








