### Week 6 – Performance Evaluation

This week focused on testing how the server performs under different workloads and checking how stable the system is when under load.

### Testing Method
All tests were run using command-line tools on the server. A baseline test was done first, then load tests for CPU, memory, disk, and network. The results were then compared.

### Performance Overview TABLE:

<img width="515" height="180" alt="Screenshot 2025-12-14 at 20 43 22" src="https://github.com/user-attachments/assets/b64a20de-423a-4662-9b6b-c0e19b7457e5" />

### CPU Load test:
stress-ng --cpu 2 --timeout 30s:

<img width="459" height="59" alt="Screenshot 2025-12-14 at 20 11 19" src="https://github.com/user-attachments/assets/316891d7-843c-44c5-abe2-6254da519786" />

"top" - NO LOAD:

<img width="764" height="351" alt="Screenshot 2025-12-14 at 19 03 02" src="https://github.com/user-attachments/assets/2bd1fce2-b61f-4751-b13e-176e07a5f215" />


"top" - UNDER LOAD:

<img width="764" height="127" alt="Screenshot 2025-12-14 at 20 11 55" src="https://github.com/user-attachments/assets/a10502d5-13d2-4a01-b309-fe9dd8f4c867" />

### Memory Load test:
"free -h" - NO LOAD:

<img width="572" height="59" alt="Screenshot 2025-12-14 at 20 12 45" src="https://github.com/user-attachments/assets/7811bc4d-2580-424d-9e56-861ceb34fe7f" />

stress-ng --vm 1 --vm-bytes 512M --timeout 30s  

<img width="489" height="64" alt="Screenshot 2025-12-14 at 20 13 42" src="https://github.com/user-attachments/assets/acffd5f5-ac26-4227-ad9e-5fb0a712d88e" />

"free -h" - UNDER LOAD:

<img width="573" height="57" alt="Screenshot 2025-12-14 at 20 14 25" src="https://github.com/user-attachments/assets/35e5dd76-35ac-4398-8890-15ed44cb18a7" />

### Disk stress test:
stress-ng --hdd 1 --hdd-bytes 1G --timeout 30s: 

<img width="486" height="62" alt="Screenshot 2025-12-14 at 20 15 56" src="https://github.com/user-attachments/assets/72643a2e-33af-4155-9d3f-b1618892e2a8" />

### Network speed test:
iperf3 -s:

<img width="430" height="59" alt="Screenshot 2025-12-14 at 20 19 23" src="https://github.com/user-attachments/assets/dfe0e1b6-154a-4a9d-b4ff-4326df8cdb63" />

iperf3 -c localhost -t 30:

<img width="509" height="243" alt="Screenshot 2025-12-14 at 20 19 41" src="https://github.com/user-attachments/assets/a8837f74-6caf-4b3c-94be-b3cd97fa4e3d" />

ping -c 10 192.168.64.2:  

<img width="462" height="225" alt="Screenshot 2025-12-14 at 20 20 36" src="https://github.com/user-attachments/assets/1b49f3d0-908f-4c7e-8707-2788eecb75f4" />

### Optimisation Testing

Reduced system swappiness  
cat /proc/sys/vm/swappiness  
sudo sysctl vm.swappiness=10  
cat /proc/sys/vm/swappiness  

Before:

<img width="366" height="28" alt="Screenshot 2025-12-14 at 20 28 12" src="https://github.com/user-attachments/assets/a9180faf-cfe3-468d-bcf4-1dc4a3dc00b7" />

Process:

<img width="362" height="33" alt="Screenshot 2025-12-14 at 20 28 23" src="https://github.com/user-attachments/assets/0487403d-2800-4470-a039-41f7c9a6a74f" />

After:

<img width="357" height="33" alt="Screenshot 2025-12-14 at 20 28 37" src="https://github.com/user-attachments/assets/14013276-03bf-4eca-b97a-750f9dc68fdb" />

### Outcome
The server remained stable during all tests. Resource usage increased under load and returned to normal after my tests were complete.

### Graphical Techniques:











