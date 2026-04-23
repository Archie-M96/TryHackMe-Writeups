# Linux Fundamentals Part 1 - Write-Up

**Author:** Archie 
**Platform:** TryHackMe  
**Room Difficulty:** Easy  

# TryHackMe: Linux Fundamentals Part 1

## 🎯 Objective
To establish a foundational understanding of the Linux Command Line Interface (CLI), focusing on file system navigation, file manipulation, and basic search operators. This module serves as the prerequisite for Linux system administration and security operations.

## 🛠️ Tools Used
* Linux CLI
* TryHackMe Browser-based AttackBox

## 🗺️ Methodology & Command Reference

### 1. System Interaction & Basic Commands
Before navigating, I needed to establish who I was logged in as and how to interact with the terminal output.
* whoami: Displays the current user logged into the session (Output: tryhackme).
* echo: Prints text to the terminal screen.

### 2. File System Navigation
Navigating the Linux directory structure without a Graphical User Interface (GUI). 
* ls: Lists the contents of the current directory.
* cd [directory]: Changes the current directory (e.g., moving into `folder4`).
* pwd: Prints the current working directory, providing the absolute path (e.g., `/home/tryhackme/folder4`).
* cat [file]: Reads and outputs the contents of a file to the screen.

*[Insert your screenshot of finding and reading the hidden note.txt file here]*

### 3. Log Searching and Data Extraction
Used command-line utilities to parse through log files and extract specific, relevant data.
* grep: Searches for a specific string of text within a file. 
    * *Execution:* "grep "THM" access.log" successfully isolated the hidden flag within a crowded log file.

*[Insert your screenshot of the grep access.log command here]*

### 4. Shell Operators & Redirection
Learned how to chain commands and manipulate file outputs directly from the command line, bypassing the need for text editors.
* &: Runs a command in the background, freeing up the terminal.
* &&: Chains two commands together; the second runs only if the first succeeds.
* >: Redirects output to a file, **overwriting** existing contents (e.g., "echo password123 > passwords").
* >>: Redirects output to a file, **appending** to existing contents without deleting data (e.g., "echo tryhackme >> passwords").

## 💡 The "Aha!" Moment
Realizing the distinction between > and >> was a major highlight. Understanding that >> appends data makes it clear how attackers might silently add malicious SSH keys to a server's authorized keys file without disrupting the existing legitimate keys. 

## 🛡️ Key Takeaways for Security
You cannot protect (or test) a system you cannot navigate. Mastering these basic CLI commands—especially grep for log analysis and the redirect operators for file manipulation—is a non-negotiable first step for navigating enterprise infrastructure environments securely.


