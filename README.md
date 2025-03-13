
# Practical 2 – Managing Files in Linux System

**Course:** AMCS2093 Operating Systems  
**Username Example:** `tarumt`

---

## 📁 Section A – Basic Linux File Management Commands

1. Show the current path:
```bash
pwd
```

2. Create a directory “D2”:
```bash
mkdir D2
```

3. List all contents in the current directory:
```bash
ls -a
dir -a
```

4. Create directory “super” inside “D2”:
```bash
cd D2
mkdir super
```

5. Inside “super”, create files:
```bash
cd super
touch apple.doc april.doc box.txt ultra.txt
```

6. File filtering examples:
- Files starting with “ap”:
  ```bash
  ls ap*
  ```
- Files with 7-character names:
  ```bash
  ls ???????
  ```
- Files ending with `.txt`:
  ```bash
  ls *.txt
  ```
- Files where the 3rd character is `p`:
  ```bash
  ls ??p*
  ```

7. Go to root directory:
```bash
cd /
```

8. Search for directory named “super”:
```bash
find ~ -name super
```

9. Search for file “ultra.txt”:
```bash
find ~ -name ultra.txt
```

10. Rename `ultra.txt` to `mega.txt`:
```bash
cd /home/tarumt/D2/super
mv ultra.txt mega.txt
```

11. Copy `super` to home directory as `super2`:
```bash
cd ..
cp -r super ~/super2
```

12. Confirm `super2` exists:
```bash
ls ~
```

13. Remove `super` and its contents:
```bash
rm -r super
```

14. Create `sampleA.txt` using `vi`:
```bash
vi sampleA.txt
```

15. Add this content in `sampleA.txt`:
```
The shell is a program that takes keyboard commands and passes them to the operating system to carry out. Almost all Linux distributions supply a shell program from the GNU Project called bash.
```

16. Create `sampleB.txt` using `cat`:
```bash
cat > sampleB.txt
```

17. Content for `sampleB.txt`:
```
When using a graphical user interface, we need another program called a terminal emulator to interact with the shell.
```
(Press `Ctrl+D` to save)

18. Edit `sampleB.txt` and add:
```
It’s likely called simply “terminal”.
```

19. Show word count of `sampleB.txt`:
```bash
wc -w sampleB.txt
```

20. Combine files into `sampleC.txt`:
```bash
cat sampleA.txt sampleB.txt > sampleC.txt
```

21. Display contents of `sampleC.txt`:
```bash
cat sampleC.txt
```

22. Archive files:
```bash
tar -cf sampleC.tar sampleA.txt sampleB.txt
```

23. Overwrite `sampleB.txt` with `sampleA.txt`:
```bash
cat sampleA.txt > sampleB.txt
cat sampleA.txt sampleB.txt
```

24. Delete `sampleB.txt`:
```bash
rm sampleB.txt
```

25. Create `backup` directory:
```bash
cd /home
mkdir backup
```

26. Backup text files:
```bash
cp /home/tarumt/D2/*.txt backup
```

---

## ✅ Section B – True / False Statements

| Statement | True/False | Notes |
|----------|------------|-------|
| The structure of Linux filesystem is tree-based starting from `/` | ✅ True | |
| Relative path starts from current dir; absolute from root `/` | ✅ True | |
| Terminal starts in root `/` directory | ❌ False | It usually starts in the user's home directory (`~`) |
| `/etc` is like Control Panel in Windows | ❌ False | `/etc` stores config files, not UI settings |
| Windows uses `/`, Linux uses `\` | ❌ False | It's the other way around (Windows: `\`, Linux: `/`) |
| Linux is case-insensitive | ❌ False | Linux **is case-sensitive** |
| Windows has volume-based hierarchy, Linux has unified | ✅ True | |
| `.tar` is a text file extension | ❌ False | `.tar` is an archive, not a text file |
| Linux uses color for file types (e.g., Blue, Green) | ✅ True | |
| Lossless compression keeps all data | ✅ True | |

---

## ➕ Extra Exercises

1. Directory Navigation:
- **Absolute Path:** `/root/MyFiles/ProjectFolder/202305_Repository`
- **Relative Path:** `../../ProjectFolder/202305_Repository`
- List only `MyReport` and `MySaving`:
  ```bash
  ls *MyReport *MySaving
  ```
- List directories ending with `Repository` under `/MyReport`:
  ```bash
  ls /MyReport/*Repository/
  ```

2. Combine `/etc/passwd` and `/etc/group`:
```bash
cat /etc/passwd /etc/group > users_groups.txt
```

3. Create symbolic link:
```bash
ln -s doc1 ~/softlink
```

4. View `/var/log/messages` page-by-page:
```bash
less /var/log/messages
```

5. Sort file content in reverse order:
```bash
sort -r CourseListing
```

6. Move and rename `/tmp/file2`:
```bash
mv /tmp/file2 ~/my_file2
```

7. Compress files:
```bash
tar -czf MyArchive.tar.gz file1 file2
```

8. Find files with "AMCS2093" in name:
```bash
find /home -name "*AMCS2093*"
```

9. List directories under `/var`:
```bash
ls -d /var/*/
```
