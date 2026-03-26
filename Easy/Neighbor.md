**Title:** Neighbor

**Difficulty:** Easy

**Summary (TL;DR):**



**1. Scope & Setup**

**Target:** http://MACHINE_IP

**Environment:** Local System, THM Attackbox

**Tools used:** Terminal, Browser

**2. Recon** 

As the challenge says, it's an IDOR vulnerability.

**What is IDOR??**

>Insecure Direct Object Reference (IDOR) is a vulnerability where an attacker can manipulate identifiers (like IDs in URLs or APIs) to access or modify other users’ data without proper authorization checks.

**3. Exploit**

Once you visit the site, you know its a login form, but wait, theres an extra line here...

"Don't have an account? Use the guest account! (Ctrl+U)"

Hey, good for us! Now if we press `Ctrl+U`, it takes us to the Page Source. Here we can see a comment with the guest credentials.

<img width="700" height="125" alt="image" src="https://github.com/user-attachments/assets/8b45d37e-fdbf-49c2-8eae-488b43ce00e6" />
<br></br>

Once we login with `guest:guest` , we are logged in and we some a very funny looking address bar :>

<img width="1299" height="362" alt="image" src="https://github.com/user-attachments/assets/79d2f60f-6246-413a-adce-ea2f67b95cfc" />
<br></br>

Sureeeeelyyyyy nothing will happen if we change that "guest" to "admin", right? right?

Well we have our flag!
