Introduction
------------
These are a couple of shell tools to extract useful TCP/IP related information:
ipextract : extracts IP addresses from stdin
ipextractnet : extracts IP addresses with netmask from stdin
ipextracttcp : extracts tcp port (of form 123/tcp) from stdin
ipextractudp : extracts udp port (of form 123/udp) from stdin
ipextractsctp : extracts sctp port (of form 123/sctp) from stdin
ipextractfqdn : extracts FQDN (and IP addresses) from stdin


Usage
-----
Use by sourcing it from your shell:

. ipextract

Real world
----------
then run some of the scripts:

$ ipextract < /etc/hosts
127.0.0.1
255.255.255.255
$

For some example of real use:
ipextractfqdn < /var/log/snort/alert | sort -u
dmesg | ipextractudp
netstat -an | ipextractplusport

Automate usage:
---------------
Add it to your bashrc (or other RC file) for automatic inclusion
e.g.:
echo '. ~/bin/ipextract/ipextract' >> .bashrc
