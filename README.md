# Linux Security Notes

Documenting my hands-on journey in Cloud Security & DevSecOps.

## OverTheWire Bandit Labs

### Level 0 -> Level 1
- Goal: Connect to the remote game server and retrieve the first password.
- Commands Learned:
  - ssh bandit0@bandit.labs.overthewire.org -p 2220 (Connect to remote server on port 2220)
  - ls (List files in current directory)
  - cat readme (Read contents of the file)

### Level 1 -> Level 2
- Goal: Read a file named - (dash).
- Issue: cat - standard input read karne lagta hai, file open nahi karta.
- Commands Learned:
  - cat ./- (Specify file path explicitly using ./)

### Level 2 -> Level 3
- Goal: Read a file with spaces in its name (spaces in this filename).
- Issue: Linux spaces ko alag arguments maanta hai.
- Commands Learned:
  - cat "spaces in this filename" (Use double quotes)
  - Alternatively: cat spaces\ in\ this\ filename (Use backslash \ to escape spaces)## Computer Networks

### Day 0 - What is a Network?
- Traffic Flow: Client -> Local Switch/Router -> Firewall -> Web Server.
- Key Concept: Internet par data packets ke roop me travel karta hai aur server tak pahunchne se pehle firewall security inspect karti hai.## Bandit Walkthrough (Levels 2 - 5)

- Level 2 -> 3 (Handling Spaces & Dashes): File names with dashes/spaces confuse terminal flags. Solved using cat ./* or cat ./"--filename--".
- Level 3 -> 4 (Hidden Files): Files starting with . are hidden from normal ls. Listed using ls -la and read via cat ./...Hiding-From-You.
- Level 4 -> 5 (Identifying File Types): Directory had multiple binary files and only one human-readable file. Inspected formats using file ./* and extracted password from the ASCII text file using cat ./-file07.