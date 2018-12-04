# Project 8 - Pentesting Live Targets

Time spent: **X** hours spent in total

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
Blind SQLi gif: ![](https://github.com/cboyd0319/cpw8/blob/master/gifs/blue1_blind_sqli.gif)

Vulnerability #2: Session Hijacking
- I used the provided change_session_id.php file from the hacktools directory to capture the logged-in session id. I then opened the page in Chrome and used the same tool to change the ID to that, granting me access to the Admin section.
Change Session ID gif: ![](https://github.com/cboyd0319/cpw8/blob/master/gifs/blue2_Session_Hijacking.gif)


## Green

Vulnerability #1: Stored XSS
- Using the provided `<script>alert('Chad found the XSS!');</script>` example, I was able to create a comment in the feedback section that executed in the Admin feedback page.
Stored XSS gif: ![](https://github.com/cboyd0319/cpw8/blob/master/gifs/green1_stored_xss.gif)

Vulnerability #2: User Enumneration
- By testing a few logins, the site displayed existing users with incorrect credentials in bold. The developer used a different span class for incorrect `span class="failed"` vs existing `span class="failure"` accounts.
User Enumeration gif: ![](https://github.com/cboyd0319/cpw8/blob/master/gifs/green2_user_enumeration.gif)

## Red

Vulnerability #1: __________________

Vulnerability #2: __________________


## Notes

Describe any challenges encountered while doing the work
