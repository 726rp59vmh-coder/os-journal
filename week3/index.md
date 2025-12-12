### Week 3 – Performance Testing

This week focused on testing how the server performs under load using command-line tools.

### CPU, Memory and Disk Testing
- stress-ng was used to apply load to the CPU, memory, and disk
- All tests completed successfully without crashes or errors

Commands used:
- stress-ng --version
- iperf3 --version
- stress-ng --cpu 2 --timeout 30s  
- stress-ng --vm 1 --vm-bytes 512M --timeout 30s  
- stress-ng --hdd 1 --hdd-bytes 1G --timeout 30s  

### Evidence:

Stress-ng Version check:
<img width="569" height="34" alt="Screenshot 2025-12-12 at 17 24 43" src="https://github.com/user-attachments/assets/9efcba20-1b69-4c4e-8cb9-6d39877cf0e0" />

iperf3 version check:
<img width="997" height="74" alt="Screenshot 2025-12-12 at 17 25 36" src="https://github.com/user-attachments/assets/c35a9b2c-b511-4319-a72d-f893be450387" />

CPU stress test output: 
<img width="466" height="66" alt="Screenshot 2025-12-12 at 17 28 03" src="https://github.com/user-attachments/assets/7f8eef2a-636e-4b8e-956c-553e7beccef3" />

Memory stress test output: 
<img width="570" height="63" alt="Screenshot 2025-12-12 at 17 31 57" src="https://github.com/user-attachments/assets/38b23714-9ea5-4145-8e69-f897ad62035d" />

Disk stress test output:
<img width="572" height="61" alt="Screenshot 2025-12-12 at 17 34 13" src="https://github.com/user-attachments/assets/dca12efa-9e9b-4d3b-bd57-7b7d5967aa9c" />


### Network Testing
- iperf3 was used to measure network throughput
- The server achieved stable high bandwidth during the test

Command used: iperf3 -c localhost -t 30

iperf3 network test output : 
<img width="560" height="576" alt="Screenshot 2025-12-12 at 17 39 02" src="https://github.com/user-attachments/assets/e6dceee0-7d7a-4473-903a-a55898455548" />


### Outcome
- The server remained stable during all tests which I ran
- CPU, memory, disk, and network performance were successfully verified
