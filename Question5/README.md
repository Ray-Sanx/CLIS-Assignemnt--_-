# Question 5: Storage Health Assessment and Documentation

This folder contains a comprehensive storage health assessment and resource documentation for a new application server deployment.

---

### Executed Commands and Observations

#### 1. Checking Disk Usage Statistics
```bash
df -h
Explanation: I executed the df -h command to analyze mounted file systems and display disk storage capacity in a human-readable format (Gigabytes/Megabytes). I observed active utilization percentages across standard root mount boundaries to ensure adequate workspace availability.

2. Analyzing Inode Utilization Metrics
df -i
Explanation: I ran df -i to audit index node (inode) consumption metrics across active file system mount points. I observed that inode capacity remains healthy with low overall allocation percentages, confirming that the system is not at risk of running out of file index pointers.

3. Listing Block Storage Devices
lsblk
Explanation: I used the lsblk command to view a structured tree list of all available block devices, partition bounds, and hardware storage assignments. This ensures the physical partition layouts align perfectly with organizational app server guidelines.

4. Verification of Document Creation via Vi
vi Storage_Assessment_Report.txt
Explanation: I utilized the native vi visual text editor interface to document and format our storage health assessment conclusions directly within the server instance.

