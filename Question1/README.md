# Question 1: Linux Environment Verification

This folder contains the verification of the Linux support engineer environment, user account details, and network connectivity.

---

### Executed Commands and Observations

#### 1. Account and Group Verification
```bash
id
Explanation: I executed the id command to retrieve the current user's UID (User ID), GID (Group ID), and all secondary groups associated with the account. I observed that my user account belongs to the standard user groups assigned by the Webminal system.

2. Current Shell Verification
echo $SHELL
Explanation: I used echo $SHELL to print the environment variable that stores the active command-line interpreter. The system returned /bin/bash, confirming that I am using the standard Bash shell for this session.

3. Current Working Directory
pwd
Explanation: I ran the pwd (print working directory) command to check my absolute location within the Linux file system hierarchy. The output confirmed that my current working directory is my user home directory (/home/Sanxxx).

4. Workspace Contents Listing
ls -la
Explanation: I executed ls -la to list all files and directories in my current workspace, including hidden files starting with a dot. I observed standard configuration files like .bashrc along with the report files created during this lab session.

5. Network Connectivity Verification
ping -c 4 google.com
Explanation: I ran the ping command with a count flag of -c 4 to transmit network packets to an external server. The output showed a 0% packet loss, verifying that the application server has active internet and network connectivity.

