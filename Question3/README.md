# Question 3: File System and Link Analysis

This folder contains an investigation into the mechanics of Linux file system shortcuts, specifically comparing hard links and symbolic (soft) links.

---

### Executed Commands and Observations

#### 1. Creating the Original File
```bash
echo "Important Developer Data" > original.txt
Explanation: I used the echo command combined with a output redirection operator to create a fresh file named original.txt containing dummy developer data. This serves as our baseline file to test link behavior.

2. Creating a Hard Link
ln original.txt hardlink.txt
Explanation: I executed the ln command to establish a hard link pointing directly to the exact same underlying file data on the storage device. I observed that it creates a new directory entry pointing to the same data block, acting as an exact mirror clone of the original file.

3. Creating a Symbolic (Soft) Link
ln -s original.txt softlink.txt
Explanation: I ran the ln command with the -s flag to create a symbolic link, which functions like a standard desktop shortcut. I observed that unlike the hard link, this file merely stores a text string pointing to the pathname of original.txt.

4. Verifying Inode Numbers and Metadata
ls -li
Explanation: I executed ls -li to inspect the index node (inode) numbers and metadata for all three files. I observed that original.txt and hardlink.txt share the exact same inode number, while softlink.txt has a unique inode number and shows an arrow pointing to the original filename.

5. Testing the Effects of File Deletion
rm original.txt && cat hardlink.txt && cat softlink.txt
Explanation: I removed the original source file using rm to test link persistence. I observed that the hard link still successfully printed out the text because the underlying data is preserved as long as one pointer exists, whereas the symbolic link broke completely and threw a "No such file or directory" error because its target path disappeared.
