# Linux Traversing Notes (Basic to Advanced)

# 1. Introduction

Linux traversal means moving through the Linux filesystem, locating files, understanding directories, and efficiently navigating the system using commands.

Learning traversal is one of the most important Linux skills.

---

# 2. Understanding Linux Filesystem

Linux uses a tree-like structure.

Everything starts from the root directory:

```bash
/
```

Example structure:

```text
/
├── home
├── etc
├── var
├── usr
├── bin
├── tmp
└── root
```

---

# 3. Important Directories

| Directory | Purpose                |
| --------- | ---------------------- |
| /         | Root directory         |
| /home     | User files             |
| /root     | Root user home         |
| /etc      | Configuration files    |
| /var      | Logs and variable data |
| /tmp      | Temporary files        |
| /usr      | User programs          |
| /bin      | Essential commands     |
| /dev      | Devices                |
| /proc     | Process information    |

---

# 4. Current Working Directory

Command:

```bash
pwd
```

Meaning:

* Prints current location.

Example:

```bash
$ pwd
/home/user/Documents
```

---

# 5. Listing Files and Directories

## ls Command

Basic:

```bash
ls
```

Long listing:

```bash
ls -l
```

Show hidden files:

```bash
ls -a
```

Human-readable sizes:

```bash
ls -lh
```

Recursive listing:

```bash
ls -R
```

Useful combination:

```bash
ls -alh
```

---

# 6. Changing Directories

## cd Command

Go to home:

```bash
cd
```

Go to specific directory:

```bash
cd /home/user/Documents
```

Move one directory back:

```bash
cd ..
```

Move two directories back:

```bash
cd ../..
```

Go to previous directory:

```bash
cd -
```

Go to root:

```bash
cd /
```

---

# 7. Absolute vs Relative Paths

## Absolute Path

Starts from root `/`

Example:

```bash
/home/user/Desktop
```

## Relative Path

Starts from current directory.

Example:

```bash
Documents/project
```

---

# 8. Special Path Symbols

| Symbol | Meaning           |
| ------ | ----------------- |
| .      | Current directory |
| ..     | Parent directory  |
| ~      | Home directory    |
| /      | Root directory    |

Examples:

```bash
cd ~
cd .
cd ..
```

---

# 9. Creating Directories

## mkdir

Create directory:

```bash
mkdir test
```

Create multiple directories:

```bash
mkdir dir1 dir2 dir3
```

Create nested directories:

```bash
mkdir -p project/src/code
```

---

# 10. Removing Directories

Remove empty directory:

```bash
rmdir test
```

Remove directory with files:

```bash
rm -r test
```

Force remove:

```bash
rm -rf test
```

WARNING:

```bash
rm -rf /
```

Never run this.

---

# 11. Creating Files

## touch

```bash
touch file.txt
```

Create multiple files:

```bash
touch a.txt b.txt c.txt
```

---

# 12. Viewing Files

## cat

```bash
cat file.txt
```

## less

```bash
less file.txt
```

Navigation inside less:

| Key   | Action        |
| ----- | ------------- |
| q     | Quit          |
| Space | Next page     |
| b     | Previous page |
| /word | Search        |

## head

```bash
head file.txt
```

## tail

```bash
tail file.txt
```

Live monitoring:

```bash
tail -f logfile.log
```

---

# 13. Copying Files and Directories

## cp

Copy file:

```bash
cp file1.txt file2.txt
```

Copy directory:

```bash
cp -r folder backup
```

Interactive copy:

```bash
cp -i file1 file2
```

---

# 14. Moving and Renaming

## mv

Move file:

```bash
mv file.txt /home/user/
```

Rename file:

```bash
mv old.txt new.txt
```

---

# 15. Finding Files

## find Command

Find by name:

```bash
find /home -name notes.txt
```

Find directories:

```bash
find . -type d
```

Find files:

```bash
find . -type f
```

Find by size:

```bash
find . -size +100M
```

Find and delete:

```bash
find . -name "*.tmp" -delete
```

---

# 16. locate Command

Fast searching:

```bash
locate file.txt
```

Update database:

```bash
sudo updatedb
```

---

# 17. Searching Text Inside Files

## grep

Search word:

```bash
grep "error" logfile.txt
```

Case insensitive:

```bash
grep -i "error" logfile.txt
```

Recursive search:

```bash
grep -r "password" /etc
```

Show line numbers:

```bash
grep -n "main" app.py
```

---

# 18. Tree View Traversal

Install tree:

Ubuntu/Debian:

```bash
sudo apt install tree
```

Use:

```bash
tree
```

Depth limit:

```bash
tree -L 2
```

---

# 19. Wildcards in Traversal

| Wildcard | Meaning          |
| -------- | ---------------- |
| *        | Any characters   |
| ?        | Single character |
| []       | Range            |

Examples:

```bash
ls *.txt
ls file?
ls [ab]*
```

---

# 20. Hidden Files

Hidden files start with:

```text
.
```

Example:

```text
.bashrc
.gitconfig
```

Show hidden files:

```bash
ls -a
```

---

# 21. Permissions While Traversing

View permissions:

```bash
ls -l
```

Example:

```text
-rwxr-xr--
```

Permission types:

| Symbol | Meaning |
| ------ | ------- |
| r      | Read    |
| w      | Write   |
| x      | Execute |

Change permissions:

```bash
chmod 755 script.sh
```

Change ownership:

```bash
chown user:user file.txt
```

---

# 22. Traversing Large Systems Efficiently

Useful commands:

```bash
history
```

Reverse search:

```bash
CTRL + r
```

Auto completion:

```bash
TAB
```

Clear terminal:

```bash
clear
```

---

# 23. Environment Variables

View:

```bash
env
```

Important variable:

```bash
echo $PATH
```

Current user:

```bash
echo $USER
```

Home directory:

```bash
echo $HOME
```

---

# 24. Advanced Traversal Commands

## xargs

```bash
find . -name "*.log" | xargs rm
```

## awk

```bash
awk '{print $1}' file.txt
```

## sed

Replace text:

```bash
sed 's/old/new/g' file.txt
```

---

# 25. Symbolic Links

Create symlink:

```bash
ln -s original.txt shortcut.txt
```

View symlink:

```bash
ls -l
```

---

# 26. Mount Points

View mounted drives:

```bash
mount
```

Disk usage:

```bash
df -h
```

Directory sizes:

```bash
du -sh *
```

---

# 27. Process Traversal

View processes:

```bash
ps aux
```

Interactive monitor:

```bash
top
```

Search process:

```bash
ps aux | grep nginx
```

---

# 28. Log Traversal

Common logs:

```text
/var/log/
```

Examples:

```bash
cd /var/log
ls
```

Monitor logs:

```bash
tail -f syslog
```

---

# 29. SSH Traversal

Connect remote server:

```bash
ssh user@server_ip
```

Copy files:

```bash
scp file.txt user@server:/home/user/
```

---

# 30. Compression and Archives

Create tar:

```bash
tar -cvf archive.tar folder/
```

Extract:

```bash
tar -xvf archive.tar
```

Gzip:

```bash
gzip file.txt
```

---

# 31. Navigation Shortcuts

| Shortcut | Action               |
| -------- | -------------------- |
| CTRL + A | Start of line        |
| CTRL + E | End of line          |
| CTRL + U | Delete before cursor |
| CTRL + K | Delete after cursor  |
| CTRL + L | Clear screen         |

---

# 32. Real Practice Tasks

## Beginner

1. Create 5 folders.
2. Move between them.
3. Create files.
4. Rename files.
5. Delete directories.

## Intermediate

1. Find all .log files.
2. Search errors inside logs.
3. Create backups.
4. Create symbolic links.
5. Use tree command.

## Advanced

1. Traverse /proc.
2. Analyze /var/log.
3. Automate traversal using bash scripts.
4. Search and clean temporary files.
5. Build navigation aliases.

---

# 33. Useful Aliases

Add in ~/.bashrc

```bash
alias ll='ls -alh'
alias ..='cd ..'
alias ...='cd ../..'
alias cls='clear'
```

Apply:

```bash
source ~/.bashrc
```

---

# 34. Bash Traversal Script Example

```bash
#!/bin/bash

for file in *.txt
 do
   echo "Found: $file"
 done
```

Run:

```bash
chmod +x script.sh
./script.sh
```

---

# 35. Best Practices

* Use TAB completion.
* Avoid rm -rf unless necessary.
* Learn absolute and relative paths.
* Use aliases.
* Practice daily.
* Read man pages.
* Explore system directories carefully.

---

# 36. Important man Commands

Manual pages:

```bash
man ls
man cd
man find
man grep
```

Search manuals:

```bash
apropos search
```

---

# 37. Linux Traversal Learning Path

## Stage 1

* pwd
* ls
* cd
* mkdir
* rm

## Stage 2

* find
* grep
* tree
* cp
* mv

## Stage 3

* permissions
* symbolic links
* logs
* processes

## Stage 4

* shell scripting
* automation
* server navigation
* remote traversal

---

# 38. Final Advice

Linux traversal becomes easy only with practice.

Spend at least:

* 30 minutes daily
* Explore directories
* Read logs
* Create and delete test files
* Use terminal instead of GUI

The more you use Linux terminal, the more natural traversal becomes.

---

# 39. Quick Revision Commands

```bash
pwd
ls
ls -alh
cd
cd ..
mkdir
rm -r
cp
mv
find
grep
tree
cat
less
tail -f
chmod
chown
ps aux
top
df -h
du -sh
ssh
scp
```

---

# 40. Conclusion

Mastering Linux traversal gives you:

* Faster workflow
* Better troubleshooting skills
* Strong system administration abilities
* Confidence in Linux environments
* Foundation for DevOps and cybersecurity

Practice consistently and traversal will become second nature.
