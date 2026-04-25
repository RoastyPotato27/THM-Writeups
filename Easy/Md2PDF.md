**Title:** MD2PDF

**Difficulty:** Easy

**Summary (TL;DR):** 

Using HTML injection to perform SSRF.

**1. Scope & Setup**

**Target:** http://MACHINE_IP

**Environment:** Local System, THM Attackbox

**Tools used:** Terminal, Browser, Gobuster

**2. Recon**  

well goind about the usual, we do nmap scans, directory bruteforces and fild out theres another service running, @ port 5000. 
What could it be?? Find out in the next episode of TryHackMe!

LOL, anyways, from the directory bruteforce we learn that /admin exists and if we try to access it, we get a 403 status code
saying that it can only be accesssed internally, which is localhost.

Well? remember the port 5000? 

since we cant access it, we can try to force out md2pdf converter to do it for us, and pottentially perform an SSRF (thankyou 
o great being with the writeup who helped me when i got stuck)

We can use HTML, because if we use html in a markdown, when we convert it to pdf (using a tool such as this site) it will
render the html before showing it in pdf. (Note that it will only work if the tool supports raw html to pdf)

**3. Exploit**

We can use the <iframe> HTML element to create a window in the "html page" to render whatever webpage we want to show. (/admin in our case)

We will use the following command:

`<iframe src="http://localhost:5000/admin"></frame>`

once we convert it, we will ahve our flag!

**4. References/Credits**

`https://medium.com/@janijay007/md2pdf-tryhackme-walkthrough-73d612b907b3`

