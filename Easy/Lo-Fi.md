**Title:** Lo-Fi

**Difficulty:** Easy

**Summary (TL;DR):**
Exploiting LFI to access system files from the address bar.

**1. Scope & Setup**

**Target:** http://MACHINE_IP

**Environment:** Local System, THM Attackbox

**Tools used:** Terminal, Browser

**2. Recon**  

Reading the description tells us it is related to Local File Inclusion.

**What is Local File Inclusion(LFI)?**

>Local File Inclusion (LFI) is a web vulnerability that allows an attacker to trick an application into loading and executing or displaying files from the server’s local filesystem by manipulating input parameters (e.g., file paths) that are not properly sanitized.

**3. Exploitation**

After we visit the site we see this:

<img width="1162" height="583" alt="image" src="https://github.com/user-attachments/assets/b22e463c-a767-430c-af8b-15fdcbb5443d" />

 lets forget about the ctf and just vibe to the Lo-Fi, kay??

Okay lets not get distracted here...

I tried the other lofi beats in the "Discography" section and looks like we can just directly interact with the address bar and exploit LFI (coz we already know its there lol)

<img width="801" height="47" alt="image" src="https://github.com/user-attachments/assets/eaeb74bb-fb99-41d5-973e-3c7a6d03e343" />
<br></br>

The challenge description said that the flag is in the root directory. So all we need to do is traverse upwards into the root and just access flag.

<img width="709" height="51" alt="image" src="https://github.com/user-attachments/assets/bdcbc506-a94c-425d-8cf8-9eb6864b83e3" />
<br></br>

Congratulations, we have our flag!
