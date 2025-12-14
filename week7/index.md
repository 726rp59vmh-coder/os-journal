### Week 7 – Security Audit and System Evaluation

This week focused on reviewing the overall security of the server and checking for any remaining risks.
A full security audit was carried out using scanning tools and manual checks.

### Security Audit with Lynis
Lynis was used to perform a full system security audit on the server.

Command used:
sudo lynis audit system:

<img width="568" height="487" alt="Screenshot 2025-12-14 at 21 34 11" src="https://github.com/user-attachments/assets/eea8ef5d-64bb-4c3b-ae83-44ce7b6b8852" />

The scan completed successfully and provided a security hardening score and recommendations.

### Network Security Scan
An external network scan was run from the workstation to check which ports and services are accessible.

Command used:
sudo nmap -sS -p 1-1000 192.168.64.2:

<img width="524" height="156" alt="Screenshot 2025-12-14 at 21 40 30" src="https://github.com/user-attachments/assets/f8626f8e-ca73-41a7-a5d3-3f599561fa44" />

The scan showed that only SSH was accessible, confirming that firewall rules were working as intended.

### SSH Security Verification
The SSH configuration was checked to confirm that insecure access methods were disabled.

Command used:
sudo sshd -T | grep -iE 'permitrootlogin|passwordauthentication':

<img width="608" height="58" alt="Screenshot 2025-12-14 at 21 41 58" src="https://github.com/user-attachments/assets/28c6f7bf-e578-465e-bdf0-78ce581b8dd9" />

Both root login/password-based authentication were disabled.

### Service Audit
Enabled services were reviewed to make sure only required services were running.

Command used:
systemctl list-unit-files --type=service | grep enabled:

<img width="555" height="186" alt="Screenshot 2025-12-14 at 21 42 16" src="https://github.com/user-attachments/assets/e072af89-79c7-4e7f-bb11-fb60e931d85d" />

Only SSH and security tools were enabled.

### Outcome
The system is securely configured with restricted network access, hardened SSH settings, and a minimal set of active services. 
The audit confirmed that the server meets the security requirements of the coursework we were assigned.



















