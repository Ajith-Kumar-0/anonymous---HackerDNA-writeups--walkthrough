# anonymous---HackerDNA-writeups--walkthrough
Easy - HackerDNA - https://hackerdna.com/labs/anonymous
Overview

This repository contains a step-by-step walkthrough for the Anonymous CTF on HackerDNA (https://hackerdna.com/labs/anonymous
). The goal was to retrieve a flag from a vulnerable FTP service. This challenge demonstrates basic service enumeration, FTP misconfiguration exploitation, and ethical hacking methodology.

Tools Used

Nmap – For port scanning and service discovery

FTP client – For connecting and enumerating the FTP server

Terminal commands – ls, get, cat for file exploration

Steps Taken

Host Discovery
Ping was blocked, so the target was scanned directly with Nmap:

nmap -Pn -sV TARGET_IP

Scan results:

21/tcp   open   ftp    vsftpd 2.0.8 or later
80/tcp   open   http   Apache httpd 2.4.62 (Unix)
2121/tcp closed ccproxy-ftp

FTP Enumeration
Tested anonymous login:

ftp TARGET_IP
Username: anonymous
Password: (press Enter)

Login succeeded, giving access to FTP directories.

File Discovery
Listed files:

ls

Found flag.txt.

Downloading the Flag
Downloaded file:

get flag.txt
exit

Reading the Flag
Opened locally:

cat flag.txt

The file contained the challenge flag.

Lessons Learned

Misconfigured FTP servers allowing anonymous access can expose sensitive files.

Step-by-step enumeration is essential in ethical hacking.

Knowing service versions and common misconfigurations helps identify attack paths.

References

CTF Challenge: Anonymous CTF on HackerDNA

Full write-up: Accessible via the lab page (Medium style inbuilt).

Note: This repository is for educational purposes only. Do not use this knowledge for unauthorized access.
