### Week 5 – Advanced Security and Monitoring

This week focused on adding advanced security controls and monitoring to the server.

### Access Control
AppArmor was checked and confirmed to be enabled.

sudo aa-status : 

<img width="260" height="48" alt="Screenshot 2025-12-13 at 21 54 27" src="https://github.com/user-attachments/assets/aa32dd43-4c56-4df7-bbda-e570108e8376" />


### Automatic Security Updates
Automatic security updates were enabled so the server installs security patches automatically.
cat /etc/apt/apt.conf.d/20auto-upgrades :

<img width="438" height="43" alt="Screenshot 2025-12-13 at 21 56 51" src="https://github.com/user-attachments/assets/0c1e4fdc-f22d-4a52-a739-803756b58d41" />


### Intrusion Detection
fail2ban was installed and enabled to protect the server from repeated failed login attempts.

Installed fail2ban and ran successfully

sudo systemctl status fail2ban :

<img width="642" height="198" alt="Screenshot 2025-12-13 at 21 59 08" src="https://github.com/user-attachments/assets/3521f3e3-8992-4921-a05e-ec71b01fce77" />


### Security Baseline Script
A security baseline script was created and executed to verify security settings.

sudo ./security-baseline.sh :

<img width="660" height="379" alt="Screenshot 2025-12-13 at 22 00 52" src="https://github.com/user-attachments/assets/582d52b4-a05b-431a-bddc-ac21cb70c0af" />


### Remote Monitoring Script
A monitoring script was created on the workstation to collect system metrics from the server.

./monitor-server.sh : 

<img width="573" height="235" alt="Screenshot 2025-12-13 at 22 02 31" src="https://github.com/user-attachments/assets/cd7c4a44-d023-4e18-9e2d-2782d4280d50" />


### Outcome
The server is secured with access control, automatic updates, intrusion detection, and monitoring, all managed remotely via SSH.
