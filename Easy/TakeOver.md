**Title:** TakeOver

**Difficulty:** Easy

**Summary (TL;DR):**

Using website certificates to find hidden subdomains.

**1. Scope & Setup**

**Target:** http://futurevera.thm

**Environment:** Local System, THM Attackbox

**Tools used:** Terminal, Browser, Gobuster

**2. Recon**  

I started by adding futurevera into the `/etc/hosts` file like so:

<img width="722" height="115" alt="image" src="https://github.com/user-attachments/assets/b2096f4c-6def-4066-a8b1-4107184295de" />
<br></br>

I then entered the url `http://futurevera.thm` into the address bar and was presented with this page. Viewing the certificate
did not help as there was nothing noteworthy.

<img width="1307" height="626" alt="image" src="https://github.com/user-attachments/assets/b46287cd-065a-40dd-ac1f-c3f476ff6395" />
<br></br>

**3. Exploit**

After running a Gobuster scan, I found `support.futurevera.thm`

<img width="727" height="356" alt="image" src="https://github.com/user-attachments/assets/45273db4-0cef-42ec-8d2b-a06170731bb3" />
<br></br>

- Now Once again we are presented with the same warning, but this time if we look at the certificate - we see a column called
`Subject Alt Names` with an secret subdomain of the website.

<img width="850" height="552" alt="image" src="https://github.com/user-attachments/assets/ff38f639-09d8-4b71-bb40-24a01f5d0d1a" />
<br></br>

Once we visit this domain (make sure to add it in /etc/hosts first) you will find the flag in the address bar.
