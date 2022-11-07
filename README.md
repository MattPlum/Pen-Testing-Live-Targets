# Pen Testing Live Targets

Time spent: **X** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:

* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each color is vulnerable to only 2 of the 6 possible exploits. First discover which color has the specific vulnerability, then write a short description of how to exploit it, and finally demonstrate it using screenshots compiled into a GIF.

## Blue

Vulnerability #1: SQLi

Description:
In the Salesperson page it gets each salesperson with an id number. Using the sql escape character you can perform sql injection on the database query.
<img src="https://github.com/MattPlum/Pen-Testing-Live-Targets/blob/0969dbe80990137e128199aab230a01e4f340388/blue1.gif">


## Green

Vulnerability #1: XSS

Description:
In the Contact Us page you can leave a comment which displays on the page that is vulnerable to an XSS attack

<img src="https://github.com/MattPlum/Pen-Testing-Live-Targets/blob/6f22c2f329186e468fa68ff2accfba8dfbb800a3/green1.gif">

Vulnerability #2: User Enumeration

Description:
Entering a username in that exists in database should return the same response as one that does not exist in the database. In the gif below I use Burp Suite to compare the responses of a username i know exists pperson, and one i made up. When login fails with valid username "pperson" it returns a span class "failiure", but when the login fails with an invalid username it returns span class "failed". This User Enumeration attack can be used to determine valid usernames in the database just based on the the response.

<img src="https://github.com/MattPlum/Pen-Testing-Live-Targets/blob/b4e5c19f4a87b7a7cb05977f0e7d23b2ce746938/green2.gif">

## Red

Vulnerability #1: IDOR

Description:
The object reference is not secured, as you can change the id attribute in the URL to view users who are not secured for an IDOR attack.

<img src="https://github.com/MattPlum/Pen-Testing-Live-Targets/blob/42759d65ae8f5025868025053eaf4725032cedab/red1.gif">

Vulnerability #2: CSRF

Description:
Using burp suite you can view the post requests from editing a user. I was able to edit the sales person's name by editing the post request and sending it to the server. An attacker can use this CSRF attack to change the victims information on the server

<img src="https://github.com/MattPlum/Pen-Testing-Live-Targets/blob/ee282eb8f2760d0f386aef458160b05092b55503/red2.gif">

## Notes

No challenges

