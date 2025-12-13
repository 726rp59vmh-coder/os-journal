### Week 4 – System Security Configuration

This week focused on securing the server using SSH hardening, firewall rules, and proper user privileges. All tasks were completed remotely via SSH from the workstation.


### Administrative User
A non-root administrative user was created and given sudo privileges.

Commands used:
- sudo adduser admin  
- sudo usermod -aG sudo admin

<img width="493" height="487" alt="Screenshot 2025-12-13 at 20 14 16" src="https://github.com/user-attachments/assets/fb69b64b-27f0-4a7e-a8bc-7c69e2b19f5d" />


### SSH Hardening
SSH key-based authentication was enabled. Root login and password based authentication was disabled.

Commands used:
- sudo nano /etc/ssh/sshd_config  
- sudo systemctl restart ssh  
- ssh admin@192.168.64.2

SSH login using key-based authentication


### Firewall Configuration
The firewall was enabled with a default deny policy. SSH access was restricted to the workstation network only.

Command used:
sudo ufw status verbose:
<img width="436" height="131" alt="Screenshot 2025-12-13 at 20 27 40" src="https://github.com/user-attachments/assets/6fb33323-bc99-4ae8-866f-e0de90fd027a" />


### SSH Configuration File Changes (Before and After)

The SSH configuration file was modified to harden remote access.

File edited:
/etc/ssh/sshd_config

Before:
- PermitRootLogin : yes
- PasswordAuthenitcation: yes

After:
- These changes disable root login and password based authentication, allowing only SSH key-based access.
Screenshot taken after editing - sudo nano /etc/ssh/sshd_config and with this the SSH configuration was updated and the SSH service was restarted to apply these changes.



### Outcome
The server now allows secure remote administration via SSH only from the workstation network.
