## BCA Year 1 Cybersecurity Journey

---

## Level 0 → 1
Challenge: Find password in readme file
Command used:
ls
cat readme
Password: [REDACTED]
What I learned: Basic SSH, listing files, and reading a file using cat.

---

## Level 1 → 2
Challenge: Password is inside a file named -
Command used:
ls
cat ./-
Password: [REDACTED]
What I learned: Use ./ before special filenames so Linux understands it as a file.

---

## Level 2 → 3
Challenge: Password is inside a file with spaces in its name
Command used:
ls
cat "spaces in this filename"
Password: [REDACTED]
What I learned: Use quotes " " when a filename has spaces.

---

## Level 3 → 4
Challenge: Password is inside a hidden file in the inhere directory
Command used:
ls
cd inhere
ls -la
cat .hidden
Password: [REDACTED]
What I learned: Hidden files start with . and can be seen using ls -la.

---

## Level 4 → 5
Challenge: Find the human-readable file inside inhere
Command used:
cd inhere
ls -la
file ./*
cat ./-file07
Password: [REDACTED]
What I learned: The file command tells the type of file. Human-readable means normal text.

---

## Level 5 → 6
Challenge: Find a file that is human-readable, 1033 bytes, and not executable
Command used:
find inhere -type f -size 1033c ! -executable
cat <filename>

Better command:
find inhere -type f -size 1033c ! -executable -exec cat {} \\;
Password: [REDACTED]
What I learned: find helps search files by size, type, and permissions.

---

## Level 6 → 7
Challenge: Find a file somewhere on the server with specific owner, group, and size
Command used:
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat <found-file-path>
Password: [REDACTED]
What I learned: 2>/dev/null hides permission denied errors.

---

## Level 7 → 8
Challenge: Password is next to the word millionth in data.txt
Command used:
grep millionth data.txt
Password: [REDACTED]
What I learned: grep searches for a word inside a file.

---

## Level 8 → 9
Challenge: Password is the only line that appears once in data.txt
Command used:
sort data.txt | uniq -u
Password: [REDACTED]
What I learned: sort arranges lines, and uniq -u shows only unique lines.

---

## Level 9 → 10
Challenge: Password is in a human-readable string after many = signs
Command used:
strings data.txt | grep =
Password: [REDACTED]
What I learned: strings extracts readable text from a file that looks unreadable.

---

## Level 10 → 11
Challenge: Password is stored in Base64 encoded form
Command used:
base64 -d data.txt
Password: [REDACTED]
What I learned: Base64 is an encoding method, not encryption. It can be decoded easily.

---

# Quick Revision Checklist

[ ] Use cat to read normal files.
[ ] Use ./- for filenames starting with dash.
[ ] Use quotes for filenames with spaces.
[ ] Use ls -la to see hidden files.
[ ] Use file to check file type.
[ ] Use find to search by size, owner, group, or permission.
[ ] Use 2>/dev/null to hide error messages.
[ ] Use grep to search inside files.
[ ] Use sort | uniq -u to find unique lines.
[ ] Use strings and base64 -d when files look encoded or unreadable.
