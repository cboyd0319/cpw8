# Project 8 - Pentesting Live Targets

Time spent: **4** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are: 
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: Blind SQLi
- Using the provided `' OR SLEEP(5)=0--'` sql statement, I was able to reproduce a blind SQLi attack
- ![](https://github.com/cboyd0319/cpw8/blob/master/gifs/blue1_blind_sqli.gif)

Vulnerability #2: Session Hijacking
- I used the provided change_session_id.php file from the hacktools directory to capture the logged-in session id. I then opened the page in Chrome and used the same tool to change the ID to that, granting me access to the Admin section.
- ![](https://github.com/cboyd0319/cpw8/blob/master/gifs/blue2_Session_Hijacking.gif)


## Green

Vulnerability #1: Stored XSS
- Using the provided `<script>alert('Chad found the XSS!');</script>` example, I was able to create a comment in the feedback section that executed in the Admin feedback page.
- ![](https://github.com/cboyd0319/cpw8/blob/master/gifs/green1_stored_xss.gif)

Vulnerability #2: User Enumneration
- By testing a few logins, the site displayed existing users with incorrect credentials in bold. The developer used a different span class for incorrect `span class="failed"` vs existing `span class="failure"` accounts.
- ![](https://github.com/cboyd0319/cpw8/blob/master/gifs/green2_user_enumeration.gif)

## Red

Vulnerability #1: IDOR
- The salespeople pages are just sequential ID numbers, making it easy to gather information on information that the developer/admin _attempted_ (poorly) to hide by using Intruder to cycle through the numbers.
- ![](https://github.com/cboyd0319/cpw8/blob/master/gifs/red1_idor.gif)

Vulnerability #2: CSRF
By submitted a link in the comments section and tricking the admin (or through phishing), you're able to create a new user on the site.
- ![](https://github.com/cboyd0319/cpw8/blob/master/gifs/red2_csrf.gif)


## Notes

Describe any challenges encountered while doing the work
