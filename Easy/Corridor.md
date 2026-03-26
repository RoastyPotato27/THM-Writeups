**Title:** Corridor

**Difficulty:** Easy

**Summary (TL;DR):**



**1. Scope & Setup**

**Target:** http://MACHINE_IP

**Environment:** Local System, THM Attackbox

**Tools used:** Terminal, Browser, crackstation, cyberchef

**2. Recon**  

This challenge also requires knowledge on IDOR.

**What is IDOR?**

>Insecure Direct Object Reference (IDOR) is a vulnerability where an attacker can manipulate identifiers (like IDs in URLs or APIs) to access or modify other users’ data without proper authorization checks.

**3. Exploit**

The website looks like this, and once you click on a door, you enter a new room, which is.... well, empty.

But the adress bar is not empty coz it contains a hash! If you pass it in crackstation.net, it will give you the value of that hash.

<img width="1029" height="320" alt="image" src="https://github.com/user-attachments/assets/e1bb201d-c901-4881-9128-cf6890571e2b" />
<br></br>

Now you can go through all rooms and crack their hashed values. 

But you will ask me, where is the IDOR? How do we crack it? Why did you add cyberchef in tools when we haven't even used it.

Well I got you, my friend. I used cybercef to create MD5 hash of number 14 (since last room is number 13) but it didnt give flag, 
and 15 and 16 don't exist. So lets try `0`.

<img width="1269" height="363" alt="image" src="https://github.com/user-attachments/assets/76f6778a-4659-4597-8e92-2fd5965f9060" />
<br></br>

Woah, that actually gave the flag. Seems like `0` was the one.
