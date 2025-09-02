# OSINT METHODS AND TOOLS

[DNS enumeration]:
	
	RECORD TYPES: A, AAAA, MX, TXT, CNAME, SOA

	nslookup :
		nslookup OPTIONS DOMAIN_NAME SERVER  (command format)
		# nslookup -type=SOA example.com   (to get authoritative name server)
		# nslookup -type=A example.com  8.8.8.8  (DNS query for A record from 8.8.8.8 server)
		# nslookup -type=mx example.com  authoritative.name.server  (DNS query for mx record associated with DOMAIN_NAME)
		# nslookup -type=txt example.com

	dig :
		dig @SERVER DOMAIN_NAME TYPE  (command format)
		# dig @name.server.com  example.com  txt
		# dig @8.8.8.8  example.com  A
		# dig example.com  CNAME

	DNSDumpster : https://dnsdumpster.com/

	Shodan : https://www.shodan.io/



[ SubDomain Enumeration]:
	
	SSL/TLS Certificates: https://crt.sh 

	Sublister tool in kali
	https://www.kali.org/tools/sublist3r/