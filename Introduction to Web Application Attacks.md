To start, we will rely on nmap service scanning (-sV) to capture the web server banner (-p80).

    kali@kali:~$ sudo nmap -p80 -sV 192.168.50.20

To take our enumeration further, we use service-specific Nmap NSE scripts, like http-enum, which
performs an initial fingerprinting of the web server.

    kali@kali:~$ sudo nmap -p80 --script=http-enum 192.168.50.20

Gobuster supports different enumeration modes, including fuzzing and dns, but for now, we’ll only
rely on the dir mode, which enumerates files and directories. We need to specify the target IP
using the -u parameter and a wordlist with -w. The default running threads are 10; we can reduce
the amount of traffic by setting a lower number via the -t parameter.

    kali@kali:~$ gobuster dir -u 192.168.50.20 -w /usr/share/wordlists/dirb/common.txt -t5

