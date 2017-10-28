Install HoneyBOT (file akan disediakan di scele)
Install nmap/Zenmap di Windows

Download dan install VirtualBox 
(untuk yang pake windows 10, WAJIB download VirtualBox versi 5.x)

Download
HoneyDrive di : http://sourceforge.net/projects/honeydrive/
atau minta sama teman2 yang sudah punya filenya.

Kemudian import file .ovf (double click saja) ke dalam
VirtualBox anda. Jika HoneyDrive minta update, abaikan saja.
Install nmap di HoneyDrive (jalankan Terminator (terminalnya HoneyDrive), kemudian
jalankan perintah "sudo apt-get update" diikuti "sudo apt-get install nmap")

PERHATIKAN KONEKSI INTERNET ANDA, JIKA BUTUH PROXY, SETTING SENDIRI
(setting proxy dapat dilakukan dengan mengedit file /etc/environment di linuxnya)

Setting Default Network Adapter:
Bridged Network -> pilih network card anda yang terkoneksi


Informasi yang dibutuhkan untuk HOneyDrive tersebut (password2 dan spec):
[Specs]
OS: 			Xubuntu Desktop 12.04.4 LTS i386
HDD: 			80GB VMDK (dynamically allocated)
Localization: 		English (United States)
Keyboard layout: 	English (United States)
Timezone: 		UTC (Coordinated Universal Time)

[System]
Connectivity: 		DHCP
Hostname: 		honeydrive
User: 			HoneyDrive
Username/password: 	honeydrive/honeydrive
Sudo password:		honeydrive
Log in automatically:	enabled

[Virtualization]
VBox Guest additions: 	installed
Shared Clipboard:	bidirectional
Drag’n’Drop:		disabled

[LAMP]
Apache 2 support:	PHP, Perl, Python, Ruby/Rails
Document root:		/var/www/
Apache 2 changes:	AllowOverride All (/var/www/), ServerTokens Minimal, ServerSignature Off
Apache php.ini changes:	max_execution_time = 300
			max_input_time = 180
			memory_limit = 256M
			post_max_size = 256M
			upload_max_filesize = 256M
			max_file_uploads = 40
MySQL root password: 	honeydrive

[Kippo]
Location:		/honeydrive/kippo/
Start script: 		/honeydrive/kippo/start.sh
Stop script:		/honeydrive/kippo/stop.sh
Downloads: 		/honeydrive/kippo/dl/
TTY logs: 		/honeydrive/kippo/log/tty/
Credentials: 		/honeydrive/kippo/data/userdb.txt
MySQL database: 	kippo
MySQL user/password: 	root/honeydrive

[Kippo-Graph]
Location: 		/var/www/kippo-graph/
Configuration: 		/var/www/kippo-graph/config.php
URL: 			http://local-or-remote-address/kippo-graph/
MySQL database: 	kippo
MySQL user/password: 	root/honeydrive

[Kippo-Malware]
Location:		/honeydrive/kippo-malware/

[Kippo2MySQL]
Location: 		/honeydrive/kippo2mysql/
MySQL database: 	kippo2mysql
MySQL user/password: 	root/honeydrive

[Kippo2ElasticSearch]
Location:		/honeydrive/kippo2elasticsearch/
MySQL database:		kippo
MySQL user/password:	root/honeydrive
ElasticSearch index:	kippo
ElasticSearch type:	auth
Kibana dashboard:	http://localhost/kibana/#/dashboard/elasticsearch/Kippo2ElasticSearch

[Kippo-Scripts]
Location: 		/honeydrive/kippo-scripts/
Scripts:		+ kippo-sessions
			+ kippo-stats
			+ kippo2wordlist

[Dionaea]
Location: 		/opt/dionaea/
Start script:		/honeydrive/dionaea-vagrant/runDionaea.sh
Binary: 		/opt/dionaea/bin/dionaea
Configuration: 		/opt/dionaea/etc/dionaea/dionaea.conf
Logs: 			/opt/dionaea/var/log/
SQLite database: 	/opt/dionaea/var/dionaea/logsql.sqlite
Malware samples: 	/opt/dionaea/var/dionaea/binaries/
Log rotation:		enabled
phpLiteAdmin: 		/var/www/phpliteadmin/
+ password: 		honeydrive
+ allow only localhost:	enabled
+ URL: 			http://localhost/phpliteadmin/phpliteadmin.php

[DionaeaFR]
Location: 		/honeydrive/DionaeaFR/
Script: 		/honeydrive/DionaeaFR/manage.py

[Dionaea-Scripts]
Location: 		/honeydrive/dionaea-scripts/
Scripts:		+ mimic-nepstats
			+ dionaea-sqlquery

[Honeyd]
Binaries: 		+ /usr/bin/honeyd
			+ /usr/bin/honeydstats
Init file: 		/etc/default/honeyd
Configuration: 		/etc/honeypot/honeyd.conf
Scripts: 		/usr/share/honeyd/scripts/
Logs: 			/var/log/honeypot/honeyd.log

[Honeyd2MySQL]
Location: 		/honeydrive/honeyd2mysql/
MySQL database: 	honeyd2mysql
MySQL user/password: 	root/honeydrive

[Honeyd-Viz]
Location: 		/var/www/honeyd-viz/
Configuration: 		/var/www/honeyd-viz/config.php
URL: 			http://local-or-remote-address/honeyd-viz/
MySQL database: 	honeyd2mysql
MySQL user/password: 	root/honeydrive

[Honeyd-Scripts]
Location: 		/honeydrive/honeyd-scripts/
Scripts:		+ honeyd-geoip
			+ honeyd-geoip-cymru

[Amun]
Location: 		/honeydrive/amun/
Start script: 		/honeydrive/amun/amun_server.py
Configuration: 		/honeydrive/amun/conf/amun.conf
Malware samples: 	/honeydrive/amun/malware/
Logs: 			/honeydrive/amun/logs/
MySQL database: 	amun_db
MySQL root/password: 	root/honeydrive

[Amun-Scripts]
Location: 		/honeydrive/amun-scripts/
			+ amun_statistics

[Glastopf]
Location: 		/honeydrive/glastopf/
Honeypot location:	/honeydrive/glastopf-honeypot/
Configuration: 		/honeydrive/glastopf-honeypot/glastopf.cfg
Start script: 		/usr/local/bin/glastopf-runner
Logs: 			/honeydrive/glastopf-honeypot/log/glastopf.log
SQLite database:	/honeydrive/glastopf-honeypot/db/glastopf.db
phpLiteAdmin: 		/var/www/phpliteadmin/
+ password: 		honeydrive
+ allow only localhost:	enabled
+ URL: 			http://localhost/phpliteadmin/phpliteadmin.php

[Conpot]
Location:		/honeydrive/conpot/
Configuration:		/honeydrive/conpot/conpot/conpot.cfg
Start script:		/honeydrive/conpot/bin/conpot
Logs:			/honeydrive/conpot/conpot.log
SQLite database:	/honeydrive/conpot/logs/conpot.db
phpLiteAdmin:		/var/www/phpliteadmin/
+ password:		honeydrive
+ allow only localhost:	enabled
+ URL:			http://localhost/phpliteadmin/phpliteadmin.php

[Wordpot]
Location: 		/honeydrive/wordpot/
Configuration: 		/honeydrive/wordpot/wordpot.conf
Start script: 		/honeydrive/wordpot/wordpot.py
Logs: 			/honeydrive/wordpot/logs/

[Thug]
Location: 		/honeydrive/thug/
Start script: 		/honeydrive/thug/src/thug.py
Logs: 			/honeydrive/thug/logs/
Malware samples:	/honeydrive/thug/samples/

[PhoneyC]
Location:		/honeydrive/phoneyc
Start script:		/honeydrive/phoneyc/phoneyc.py
Logs:			/honeydrive/phoneyc/log/
Downloads:		/honeydrive/phoneyc/log/downloads/
Malware samples:	/honeydrive/phoneyc/samples/

[LaBrea]
Binary: 		/usr/sbin/labrea
Configuration: 		/etc/labrea/labrea.conf

[Tiny Honeypot]
Location:		/usr/share/thpot/
Binary: 		/usr/sbin/thpot
Configuration: 		/etc/thpot/thp.conf
Examples: 		/usr/share/doc/tinyhoneypot/examples/
Logs: 			/var/log/thpot/

[IIS Emulator]
Location:		/usr/share/iisemulator/
Honeyd example: 	/usr/share/doc/iisemulator/examples/honeyd.conf

[INetSim]
Location:		/usr/share/inetsim/
Binary:			/usr/bin/inetsim
Configuration: 		/etc/inetsim/inetsim.conf
Logs: 			/var/log/inetsim/

[Maltrieve]
Location: 		/opt/maltrieve/
Script: 		/opt/maltrieve/maltrieve.py
Configuration:		/opt/maltrieve/maltrieve.cfg
Logs:			/opt/maltrieve/maltrieve.log
Malware samples:	/opt/maltrieve/archive/
Malware categorizer:	/opt/maltrieve/maltrievecategorizer.sh

[ELK::ElasticSearch]
Location:		/usr/share/elasticsearch/
Start script:		/etc/init.d/elasticsearch
Configuration:		+ /etc/elasticsearch/
			+ /etc/defaults/elasticsearch
Logs:			/var/log/elasticsearch/

[ELK::Logstash]
Location:		/opt/logstash/
Start script:		/opt/logstash/bin/logstash
Configuration:		/etc/logstash/conf.d/
Patterns:		/opt/logstash/patterns/
Logs:			/var/log/logstash/
Logstash contrib:	installed

[ELK::Kibana]
Location:		/var/www/kibana/
Configuration:		/var/www/config.js
Allow only localhost:	enabled
URL:			http://localhost/kibana/


[Security/Forensics/Malware Tools]
EtherApe
nmap + Zenmap + Umit Network Scanner
Wireshark + tshark
dnstop
MINI DNS Server
dnschef
ClamAV + ClamTk
ettercap (graphical)
The Sleuth Kit + Autopsy
htop
ntop (admin credentials: admin/honeydrive)
ngrep
p0f
Flawfinder
Automater
TekCollect
hashMonitor
corkscrew
cryptcat
netcat
socat
hsim
VBinDiff
hexdiff
UPX
ssdeep
md5deep
pdftk
Flasm
dex2jar
DFF (Digital Forensics Framework)
pdf-parser
pdfid
disitool
NASM
Dissy
HT Editor
exiftool
shellcode2exe
Radare2 + Bokken
Pyew + Bokken
Pipal
John the Ripper
Origami
chaosreader
dsniff
hping3
Scapy
netexpect
Tcpreplay
tcptrace
tcpslice
sslstrip
mitmproxy
mitmdump
libemu
Yara
Recon-ng
SET (Social-Engineer Toolkit)
MASTIFF + MASTIFF2HTML
Viper
Minibis
Nebula
Burp Suite
xxxswf
extract_swf
Java Decompiler (JD-GUI)
JSDetox
extractscripts
AnalyzePDF
peepdf
officeparser
DensityScout
YaraGenerator
IOCExtractor
sysdig
Bytehist
PackerID
RATDecoders
androwarn
passivedns
BPF Tools
SpiderFoot
hashdata
LORG

[Firefox Add-ons]
Firebug
NoScript
Adblock Plus
Disconnect
JavaScript Deobfuscator
Undo Closed Tabs Button
PassiveRecon

[Extra Software]
phpMyAdmin
phpLiteAdmin
Adminer
PuTTY SSH Client
7zip
Furius ISO Mount
GParted
gedit
Terminator
VYM - View Your Mind
WebHTTrack Website Copier
UNetbootin
RecordMyDesktop
Shutter
gURLChecker
Xpdf
Sagasu

[Removed] 
Kojoney
mwcrawler
Vidalia
ircd-hybrid
DNS Query Tool
DNSpenTest
VLC
Parcellite
Open Penetration Testing Bookmarks Collection (Firefox)
