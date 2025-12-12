Week 1 – System Setup & Planning

This week focused on setting up the Linux server, configuring the workstation–server structure, and collecting basic system information using command-line tools.

** My Overall Setup**

Workstation (client machine)
• MacBook Air M3 (macOS)
• Used to remotely manage the server via SSH
• Tools: macOS Terminal and GitHub Pages

Server (target system)
• UTM virtual machine running Ubuntu Server 22.04.5 LTS
• 4 GB RAM, 30 GB disk, multi-core CPU
• Command-line only; accessed directly via terminal or remotely via SSH

Network
• Interface: enp0s1
• Server IP: 192.168.64.2/24
• UTM virtual network

Why I Chose Ubuntu Server 22.04.5 LTS
• Stable LTS release
• Works smoothly with SSH, ufw, AppArmor
• Lightweight and suitable for headless use

Why My MacBook Is the Workstation
• Built-in SSH client
• No need for a second VM
• Mirrors real remote administration workflow

To connect from the Mac to the server I use:
ssh sameer@192.168.64.2

System Information (CLI Evidence)

Below are the required commands for Week 1 with placeholders for screenshots.

Kernel & architecture (uname -a)
<img width="915" height="36" alt="Screenshot 2025-12-11 at 15 46 30" src="https://github.com/user-attachments/assets/e1ae7310-998e-4dd9-9bc2-a9ef11c8f4de" />

Memory usage (free -h)
<img width="664" height="64" alt="Screenshot 2025-12-11 at 15 46 40" src="https://github.com/user-attachments/assets/23c44d32-ba59-4f6c-bbe4-138381efb8d3" />

Disk usage (df -h)
<img width="581" height="146" alt="Screenshot 2025-12-11 at 15 46 53" src="https://github.com/user-attachments/assets/f568d5f6-1d94-452c-86db-15e072333ec1" />


Network configuration (ip addr)
<img width="823" height="241" alt="Screenshot 2025-12-11 at 15 47 06" src="https://github.com/user-attachments/assets/8f69bd54-25ac-410d-89c1-f2bb30591af0" />


Distribution details (lsb_release -a)
<img width="339" height="100" alt="Screenshot 2025-12-11 at 15 47 27" src="https://github.com/user-attachments/assets/543ed71d-9078-44cf-b8c9-8de66ee7bec4" />


SSH & Firewall Evidence

SSH service running (systemctl status ssh)
<img width="1022" height="806" alt="Screenshot 2025-12-11 at 18 57 41" src="https://github.com/user-attachments/assets/b64584e2-e323-4c02-b49f-797e12ab3e34" />


Firewall enabled (sudo ufw status)
<img width="382" height="180" alt="Screenshot 2025-12-11 at 19 58 07" src="https://github.com/user-attachments/assets/afdfbb16-3d26-4027-b7fc-8b4fedfb5ca5" />
