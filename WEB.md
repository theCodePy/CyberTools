# WEB APPLICATION PENETRATION TESTING.

- ffuf (Fuzz Faster U Fool)
	-- # ffuf -u https://example.com/FUZZ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -mc 200,204,301,302,403 -t 100 -r
		-mc (match only responses with status code.)
		-u (target url where FUZZ keyword will be replaced with by each word)
		-w (path to wordlist)
		-t (increase thread default is 40)
		-r (follow redirects)

	-- # ffuf -u https://example.com/DIR -w /usr/share/wordlists/dirb/common.txt -mc 200 -p DIR
		-p (use this keyword to replace p for placeholder)


	-- # ffuf -u https://example.com/login.php?user=USER&pass=PASS -w users.txt:USER -w passwords.txt:PASS
		if wants to use multiple placeholders they can be used like this.
		to detect a valid username and password. we can use filters in this command.
		| Flag  | Purpose                                                                |
		| ----- | ---------------------------------------------------------------------- |
		| `-fc` | **Filter by status code** (e.g., ignore 401 Unauthorized)              |
		| `-fs` | **Filter by response size** (e.g., ignore if response is same length)  |
		| `-fw` | **Filter by number of words**                                          |
		| `-fl` | **Filter by number of lines**                                          |
		| `-mr` | **Match regex or string in body** (e.g., "Welcome", "Dashboard", etc.) |


favicon database to check frameworks:

    https://wiki.owasp.org/index.php/OWASP_favicon_database

Wappalyzer:

	Wappalyzer (https://www.wappalyzer.com/) is an online tool and browser extension that helps identify what technologies a website uses, such as frameworks, Content Management Systems (CMS), payment processors and much more, and it can even find version numbers as well.

S3 Buckets:

	The format of the S3 buckets is http(s)://{name}.s3.amazonaws.com where {name} is decided by the owner, such as tryhackme-assets.s3.amazonaws.com. S3 buckets can be discovered in many ways, such as finding the URLs in the website's page source, GitHub repositories, or even automating the process. One common automation method is by using the company name followed by common terms such as {name}-assets, {name}-www, {name}-public, {name}-private, etc.

Subdomain Enumeration:

	1. https://crt.sh offer a searchable database of certificates that shows current and historical results.
	2. site:*.tryhackme.com -site:www.tryhackme.com -site:help.tryhackme.com -site:business.tryhackme.com
	
	DNS Bruteforce with dnsrecon:
	3. dnsrecon -t brt -d acmeitsupport.thm -D wordlist.txt
		-t std → Standard enumeration (basic DNS records like A, NS, MX, etc.)
		-t brt → Bruteforce subdomains using a wordlist.
		-t zonewalk → Zone transfer if the DNS server allows AXFR.
		-t rvl → Reverse lookup of IP ranges.
		-t axfr → Test for DNS zone transfer directly.
		
	OSINT - Sublister
	4. ./sublist3r.py -d acmeitsupport.thm -o file.txt
 