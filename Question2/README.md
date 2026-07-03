# Question 2: Secure Project Workspace Setup

This folder contains the setup and permissions configuration for a secure project team workspace.

---

### Executed Commands and Observations

#### 1. Umask Value Verification
```bash
umask
Explanation: I executed the umask command to check the default file creation permission mask for the system. The output showed 0022, which ensures that newly created directories default to 755 (read/execute for others) and files default to 644.

2. Workspace Directory Creation
mkdir -p project_workspace/docs project_workspace/src
Explanation: I used mkdir -p to build a structured project workspace directory with nested docs and src subfolders. This creates an isolated directory tree to organize project files and source documentation cleanly.

3. Initial Permissions and Ownership Verification
ls -ld project_workspace
Explanation: I ran ls -ld to audit the initial permissions and ownership details of the newly created directory before making security changes. The output showed standard ownership (Sanxxx) and default read-write-execute permissions for the owner.

4. Restricting File Permissions (Secure Lockdown)
chmod 770 project_workspace
Explanation: I executed chmod 770 to strictly lock down the directory so that only the owner and designated group members have full access (read, write, execute), while revoking all permissions from the public/others. This successfully prevents unauthorized users on the server from viewing or tampering with sensitive project data.

5. Verifying Final Security Settings
ls -ld project_workspace
Explanation: I ran ls -ld a second time to verify that the permission modifications were applied correctly. The updated output confirmed that public permissions were dropped entirely, ensuring a secure environment.

