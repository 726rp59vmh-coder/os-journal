###Week 2 - User Admin and SSH Hardening

###Admin User
-Created 'admin' user and added to the sudo group
-Verified SSH login as the admin
-Verified admin can use sudo

###Evidence
-Shows Successful login as the admin user
<img width="985" height="789" alt="Screenshot 2025-12-12 at 16 22 15" src="https://github.com/user-attachments/assets/bb7a4fc4-1327-4f3c-b63a-eb33c4257d2b" />

###File Permissions (chmod)
-Created a test directory and file  
-Checked default file permissions  
-Restricted file access so only the owner can read and write the file  

Commands I used:
mkdir -p week2-perms
cd week2-perms
echo "test" > file.txt
ls -l
chmod 600 file.txt
ls -l

Expected result:
- Before: `-rw-rw-r--`
- After: `-rw-------`

### Evidence
- Shows permissions before and after applying `chmod 600`
<img width="629" height="222" alt="Screenshot 2025-12-12 at 16 59 27" src="https://github.com/user-attachments/assets/c9fc1745-f7ec-40dd-a494-e0c741184135" />

### Security Configuration Checklist
- Use a non-root admin user with sudo
- SSH used for remote access
- Firewall enabled
- File permissions restricted

### Threat Model
- SSH password guessing → limited by user access
- Excessive privileges → controlled with sudo
- Unauthorised file access → restricted using chmod

### Performance Testing Plan
- Monitor CPU, memory, disk, and network usage
- Record results for comparison later
