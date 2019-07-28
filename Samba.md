## Samba
### General
* List shares:
  *  `smbmap -H <TARGETIP>`
  *  `smbclient -L //<TARGETIP>/`
* Recursively show content of a share - `smbmap -H <TARGETIP> -R <SHARE>`
* Connect
  * `smbclient //<TARGETIP>/<SHARE>`
  * `smbclient //<TARGETIP>/<SHARE> -U <USERNAME>%<PASS>`
* Mount share
  * Tools - `apt-get install libguestfs-tools cifs-utils`
  1. `mkdir /mnt/remote`
  2. `mount -t cifs //<TARGETIP>/<SHARE> /mnt/remote -o -rw`


### SMB commands
* List files - `ls`, `dir`
* Download single file - `get <FILE>`
* Download all files 
  * One-liner - `smbclient '\\<TARGETIP>\<SHARE>' -N -c 'prompt OFF;recurse ON;cd 'path\to\directory\';lcd '~/path/to/download/to/';mget *'`
  * Full code
    ``` 
    mask ""
    recurse ON
    prompt OFF
    cd 'path\to\remote\dir'
    lcd '~/path/to/download/to/'
    mget *
    ````