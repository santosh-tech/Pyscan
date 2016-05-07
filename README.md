```
_____________  ____________________ _______
___  __ \_  / / /_  ___/  ___/  __ `/_  __ \
__  /_/ /  /_/ /_(__  )/ /__ / /_/ /_  / / /
_  .___/_\__, / /____/ \___/ \__,_/ /_/ /_/
/_/     /____/
```


# Pyscan
Pyscan - A fast malware scanner using ShellScannerPatterns.

==

### Version
* 1.12

### Supported Platforms

* _CentOS 5/6/7_
* _CloudLinux 5/6/7_
* _Redhat 5/6/7_
* _Ubuntu and Debian - All versions._
* _Windows with https://msys2.github.io_
* cPanel - Plesk - Directadmin (other control panels not tested.)
* Any cms.
* 


### Detection Example

https://raw.githubusercontent.com/bashcode/Pyscan/master/scan_example.png

### Usage Linux
Add these to your BASH functions. 'sf' will filter out just the filenames from a piped input or argument of the logfile. 'tsf' will filter the filename and timestamps
which can then be piped into a 'sort' to get the earliest 'ctime'.:
```
alias pyscan='bash <(curl -ks https://raw.githubusercontent.com/bashcode/Pyscan/master/run-pyscan.sh) "$@"'

# pyscan filters
alias sf='awk -F"::" '\''{ print $4 }'\'''
alias tsf='awk -F"::" '\''{ print $3"::"$4; }'\'''

Options..
* -c for current directory
* -u for scan username
* -p for custom path
* --exclude for exclude custom dir
* -D for debug mode

* DETECT ONLY

```sh
python <(curl -ks https://raw.githubusercontent.com/bashcode/Pyscan/master/pyscan.py)
```

* CLEAN MALWARE

```sh
python <(curl -ks https://raw.githubusercontent.com/bashcode/Pyscan/master/removeinjections.py)
```

### Usage Windows
```sh
Download, install, and run MSYS2
Run update-core to update the core packages.
Run pacman -S python2 python2-setuptools
For significantly faster scans, compile and install re2. Install the Pyton module with easy_install2.7 re2.
Use the function pyscan provided above.
```


