# Question 4: File Access and I/O Investigation

This folder contains an investigation into an application experiencing logging issues, focusing on open files, file descriptors, and I/O redirection limits.

---

### Executed Commands and Observations

#### 1. Tracking Open Files by Process
```bash
lsof -c bash
Explanation: I executed the lsof (list open files) command with the process name flag to inspect all files currently held open by the active terminal subsystem. I observed critical shared system libraries, execution text mappings, and active working directory points handled by the operating system kernel.

2. Investigating Active File Descriptors
ls -l /proc/self/fd
Explanation: I checked the process file descriptor directory inside the pseudo-filesystem layer to map active channel bindings. I observed standard bindings mapping explicitly to Standard Input (0), Standard Output (1), and Standard Error (2) routing channels.

3. Standard Output Redirection (Overwriting)
echo "System Status Normal" > output.log
Explanation: I used the standard output redirection operator > to route string data away from the screen terminal directly into a file. I observed that the command silently overwrote or initialized output.log with the clean text input.

4. Standard Error Redirection Isolation
ls /nonexistent_folder 2> error.log
Explanation: I intentional triggered a terminal missing folder error and used the 2> operator to capture Standard Error channel output exclusively. I observed that the screen terminal output stayed entirely clear while the text error string was isolated into error.log.

5. Checking Maximum Open File Limits
ulimit -n
Explanation: I executed the user resource tracking utility with the -n flag to discover the system-wide threshold for maximum concurrently open file descriptors. The system returned a strict, low limit of 20, explaining the threshold ceilings blocking app log operations.

