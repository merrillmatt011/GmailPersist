# Gmail Persist
<h2>Gmail Knocker inspired by <a href="https://twitter.com/enigma0x3" target="_blank">@enigma0x3</a> <a href="https://github.com/enigma0x3/OutlookPersistence" target="_blank">OutlookPersistence</a></h2>

<h4>SYNOPSIS</h4>
Uses a designated Gmail Email account as the middle man for persistence. 

[!] Needs to be placed on target to persist i.e. (registry, run key, schtask, etc..)<br>
[!] The script includes username and password for the email so ensure a burnable email is used<br>
[!] The script doesn't delete emails because it is only getting the feed ,so after every call-in it will execute the URL until the email is deleted.

<h4>DESCRIPTION</h4>
This script uses the provided Gmail Address and Password to retrieve a feed of the gmail inbox. The feed is only the first ~20 emails and only includes <strong>~200 characters</strong> of the body.
After it retrieves the feed it looks for the "Trigger word" which is the email subject and also the attacker email which could be the same Gmail email address. Once there is a match it takes the body which should look like:<br />
http://172.16.0.1/powershell-oneliner.txt

<h4>EXAMPLE</h4>
```
PS> ./GmailPersist.ps1
```
Now send and email with the following information:<ul>

<li>FROM: (ATTACKER EMAIL)</li>
<li>TO: (GMAIL ACCOUNT)</li>
<li>SUBJECT: (Trigger Word)</li>
<li>BODY:<br />
http://172.16.0.1/powershell.exe-oneliner.txt</li></ul>

<h4>Main Usage</h4>
This is a knocker so a persisted call-back can easily be changed to call-back to a new C2 infrastructure.
Leave an email in the inbox so once the script is kicked off it will kick off and a call-back will be recieved.
