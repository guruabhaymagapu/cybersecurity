### Linux Fundamentals using OverTheWire Bandit (Level 0–6)



### 🎯 Objective

### Develop foundational Linux command-line proficiency relevant to SOC Analyst tasks such as:

- Secure remote access (SSH)
- File system navigation
- Hidden file detection
- File type identification
- Permission-based file discovery
- Basic text extraction


### 🧪 Lab Tasks Completed

### 🔹 Bandit Level 0 → 1

- Established SSH connection to remote Linux server
- Navigated home directory
- Retrieved password using:

- ls
- cat


### 🔹 Bandit Level 1 → 2

- Accessed file with special filename (-)
- Used:

- cat ./-

### 🔹 Bandit Level 2 → 3

- Accessed file with spaces in name
- Used:

- cat ./--spaces\ in\ this\ filename--


### 🔹 Bandit Level 3 → 4

- Located hidden file within directory
- Used:

- ls 
- cd
- ls -al
- cat .hidden


### 🔹 Bandit Level 4 → 5

- Identified human-readable file among multiple files
- Used:

- ls
- cd
- find . type f | xargs file
- cat ./filename


### 🔹 Bandit Level 5 → 6

- Located file based on:
- Size
- Permissions
- Ownership
- Used:

- ls
- cd
- find . -type f -size 1033c ! -executable
- cat ./path/to/file


### 🔹 Bandit Level 6 → 7

- Searched entire system for file with:
- Specific user
- Specific group
- Specific size
- Used:

- find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
- cat /path/to/file




### 🔍 SOC Relevance

- The commands practiced in this lab are used in:
- Investigating unauthorized file access
- Locating suspicious binaries
- Reviewing authentication artifacts
- Detecting persistence mechanisms
- Supporting host-based forensic analysis


### 📁 Evidence Collected

- All screenshots related to Level 0–6 execution are stored under:
- soc-labs/os-basics/screenshots/