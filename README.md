#CyberTools, CTF tools list



[ Cyptography ]:
	
	-- substitution cipher solver : https://www.guballa.de/substitution-solver
		this website is awsome crack substitution in seconds.
    

    -- john :
        $ john hashfile --mask=?1?1?1?1 --1=abcdef12345
            using custom caracterset to bruteforce with john

    -- encrypted zip file:
        brutefore with fcrackzip
            $ fcrackzip -b -u -v encrypted.zip
        or using john:
            $ zip2john encrypted.zip > hash

---------
[ Forensics ] :
    
    -- dd image file forensics:
        mmls file.dd (to check partitions info)
        fdisk -l file.dd  (to check partions info)
        dd if=disko-2.dd of=disk1.img bs=512 skip=2048 count=51200 (to create disk image that can be mounted)
         
