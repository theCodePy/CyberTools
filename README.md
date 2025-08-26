# CyberTools, CTF tools list



[ Cyptography ]:
	
	-- substitution cipher solver : https://www.guballa.de/substitution-solver
		this website is awsome crack substitution in seconds.
    

    -- john :
        $ john hashfile --mask=?1?1?1?1 --1=abcdef12345
            using custom caracterset to bruteforce with john
        $ john --incremental=Digits hash
            to bruteforce with only numbers

    -- crackstation to crack hash: https://crackstation.net/
    -- Hashes.com to crack hash: https://hashes.com/en/decrypt/hash
    -- hashcat wiki: https://hashcat.net/wiki/doku.php?id=example_hashes

    -- encrypted zip file:
        brutefore with fcrackzip
            $ fcrackzip -b -u -v encrypted.zip
        or using john:
            $ zip2john encrypted.zip > hash


[ Forensics ]:

    -- dd image file forensics:
        mmls file.dd (to check partitions info)
        fdisk -l file.dd  (to check partions info)
        dd if=disko-2.dd of=disk1.img bs=512 skip=2048 count=51200 (to create disk image that can be mounted)
         

[ Networking ]:

    -- smbclient 
        # smbclient -L ip_address (to list)
        # smblient -L ip_address -N  (list with no password prompt login with guest or anonymous)
        # smbclient //ip_address/shareName -N  (anonymous login to access pulic share)

    -- ssh
        # hydra -L user.txt -P rockyou.txt ssh://10.10.131.81
        # hydra -l username -P rockyou.txt ssh://ip_address


    -- nmap
        # nmap <ip_address> -oA <basename>  [saves the output in three major format at once]
        # nmap <ip_address> -v[level]        [to select verbosity level for example: `-v`,  `-vv`,  `-v3`]
        # nmap <ip_address> -oN  <name>       [save output in normal format]
        # nmap <ip_address> -oG  <name>       [grepable format]
        # nmap <ip_address> -T5              [scan time level to 5]
        TCP Null Scans (-sN)  [no flag is set]
        TCP FIN Scans (-sF)    [only FIN flag is set]
        TCP Xmas Scans (-sX)   [ FIN + PSH + URG flags are set]
        TCP stealth scan or "half-open" scan (-sS)  [doesn't complete 3 way handshake and send RST packet to the server]
        # nmap -sU --top-ports 20 <target_ip>    [send a top 20 most commonly used ports]
        # nmap -sn 192.168.0.1-254
            or
        # nmap -sn 192.168.0.0/24   [nmap "ping sweep" -- send ICMP packets to each possible ip-address, -sn tell not to scan any ports--forcing it to rely on ICMP echo packets]
        NSE (Nmap Scripting Engine) scripts:
        safe:- Won't affect the target
        intrusive:- Not safe: likely to affect the target
        vuln:- Scan for vulnerabilities
        exploit:- Attempt to exploit a vulnerability
        auth:- Attempt to bypass authentication for running services (e.g. Log into an FTP server anonymously)
        brute:- Attempt to bruteforce credentials for running services
        discovery:- Attempt to query running services for further information about the network (e.g. query an SNMP server).
        for more on nse see this link --> https://nmap.org/book/nse-usage.html
        # nmap -p 80 --script http-put --script-args http-put.url='/dav/shell.php',http-put.file='./shell.php'
        #nmap --script-help <script-name> [script help]
        -f:- Used to fragment the packets (i.e. split them into smaller pieces) 
        --badsum:- this is used to generate in invalid checksum for packets.
        --scan-delay <time>ms:- used to add a delay between packets sent.
        --mtu <number>, accepts a maximum transmission unit size to use for the packets sent. This must be a multiple of 8.
        --data-length <num>: Append random data to sent packets
    